# Purpose
- Use some open datasets to train deep learning models(CNN, RNN, LSTM, GRU) for industrial predictive maintenance

# Dataset Source
## training_model_ai4i.ipynb
- from [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/AI4I+2020+Predictive+Maintenance+Dataset) 
- reference: Stephan Matzka, School of Engineering - Technology and Life, Hochschule fÃ¼r Technik und Wirtschaft Berlin, 12459 Berlin, Germany, stephan.matzka '@' htw-berlin.de

## training_model_FordA.ipynb
- from [Korea AI Manufacturing Platform(KAMP)](https://www.kamp-ai.kr/front/dataset/AiDataDetail.jsp?AI_SEARCH=&page=1&DATASET_SEQ=2&EQUIP_SEL=&FILE_TYPE_SEL=&GUBUN_SEL=&WDATE_SEL=)
- reference: 중소벤처기업부, Korea AI Manufacturing Platform(KAMP), Ford 엔진 진동 AI 데이터셋, Ford (http://www.timeseriesclassification.com), 04, Dec, 2020, https://www.kamp-ai.kr/front/dataset/AiDataDetail.jsp?AI_SEARCH=&page=1&DATASET_SEQ=2&EQUIP_SEL=&FILE_TYPE_SEL=&GUBUN_SEL=&WDATE_SEL=

# Dataset Features
## ai4i2020
- total 10,000 data as rows
- 14 columns
  - binary classification
    - feature: 'Air temperature [K]', 'Process temperature [K]', 'Rotational speed [rpm]', 'Torque [Nm]', 'Tool wear [min]' 
    - class: 'Machine failure'
  - Multi-class classificatioin
    - feature: 'Air temperature [K]', 'Process temperature [K]', 'Rotational speed [rpm]', 'Torque [Nm]', 'Tool wear [min]' 
    - class: 'TWF', 'HDF', 'PWF', 'OSF', 'RNF' 
- in csv format, with header

## FordA
- total 3,601 data as rows
- 501 columns
- binary classification
  - feature: sensor's value (there are 500 sensors)
  - class: failure
    - -1: failure
    - 1: normal
- in tsv format, no header 

# Operating Environment
- Google Colaboratory (using TPU, on July.23rd.2021)

# Result
## taining_model_ai4i2020.ipynb
- create tsv file that contains accuracy information
- detailed results included in ipynb file

|accuracy|CNN|LSTM|GRU|
|:--------:|------:|-----:|-----:|
|binary classify|
|train|0.970|0.957|0.965|0.964|
|validation|0.972|0.958|0.966|0.966|
|test|0.972|0.971|0.966|0.971| 
|multiclass classify|
|train|0.971|0.937|0.958|0.958|
|validation|0.970|0.942|0.966|0.971|
|test|0.978|0.967|0.967|0.969| 

- results seem proper
## training_model_FordA.ipynb
- create tsv file that contains accuracy information
- detailed results included in ipynb file

|accuracy|CNN|RNN|LSTM|GRU|Logistic Regression|XGBoost|
|:--------:|------:|-----:|-----:|-----:|-----:|---:|
|train|0.835|0.503|0.539|0.511|0.589|1|
|validation|0.83|0.517|0.536|0.506|0.513|0.718|
|test|0.872|0.473|0.577|0.513| 

- except CNN, dataset seems not enough for other deep learning models(RNN, LSTM, GRU)
- for Logistic Regression, underfitting occured(dataset seems not enough in size)
- for XGBoost, overfitting occured(even though using early stopping)

# Conclusion
- using ai4i2020 dataset, predicting failure situations and failure reasons are possible.
- using FordA dataset, since the dataset is too small for deep learning, cannot get proper result from it.
- using FordA dataset for Machine Learning, preventing overfitting and underfitting should be done by modifying hyperparameters.
  - not easy because of lack of proficiency.
