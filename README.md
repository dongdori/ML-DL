# Solar-Power-Generation-quantile-forecasting-using-CNN-GRU-model
Machine Learning and Deep Learning projects

1. Problem Statement
Task is to forecast solar power generation of 2 days at intervals of 30 minutes, given weather data of previous 7 days at intervals of 30 minutes. 
* I had to forecast not only single prediction, but also 0.1 ~ 0.9 quantiles of power generation.
Weather data is composed of 6 features,  'DHI', 'DNI', 'Humidity', 'Windspeed', 'Temperature' and 'Solar power generation'. 
Data contains 55620 rows * 6 features

2. Approach
I tried to improve the model by ensembling 3 models. I had to make 9 models per each approach because it is 'quantile forecasting task'! 
  
  #model 1. linear model
    very simple model. Basic assumption of this model is that power generation of each timestep has linear relation with each feature value of each time steps.  
  #model 2. LGBM model
    Basic assumption of this model is that power generation of each timestep has complicated(not linear) relation with each feature value of each time steps.
    Used lgbm instead of Linear weights.
  #model 3. CNN+GRU model
    It is Encoder-Decoder based model. Using Conv1D kernel, input multivariate sequence is encoded into a vector and it is decoded by GRU,
    therefore output sequence length of 96(solar power generation value of 2 days at intervals of 30 minutes)

You can check my notebook for detailed implementation! 
