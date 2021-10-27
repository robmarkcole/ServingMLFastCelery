# ServingMLFastCelery
Working example for serving a ML model using FastAPI and Celery, from [this article](https://towardsdatascience.com/deploying-ml-models-in-production-with-fastapi-and-celery-7063e539a5db). This fork includes a `docker-compose` taken from [here](https://github.com/RTae/yolor_trt) and modified to use only Redis and drops RabbitMQ used in the original example.

## Docker
Run `docker-compose build` then `docker-compose up` then navigate to [http://localhost:8000/docs](http://localhost:8000/docs). Example data for inferencing is in `test_client.py`

Build the app seperately:
```
docker build -t ml-app .
```
Note there are many requirements, so I had to unpin a bunch of these to successfully build.

## Model
This model is trained on data on [kaggle](https://www.kaggle.com/sakshigoyal7/credit-card-customers). I also had to upate the training notebook since there are some bad columns on the dataset on Kaggle.

<p align="center">
<img src="https://github.com/robmarkcole/ServingMLFastCelery/blob/master/images/predict.png" width="1100">
</p>

<p align="center">
<img src="https://github.com/robmarkcole/ServingMLFastCelery/blob/master/images/response.png" width=1100">
</p>