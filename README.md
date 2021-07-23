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
