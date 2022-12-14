# Big-Data-Project
<img src="img/logo-ray.png" width="150">  <img src="img/Apache_Spark_logo.svg.png" width="105">

A spark and ray application, developed in a Google Cloud Platform (GCP) environment, to compare and analyze these two popular parallel computing frameworks for a machine learning task. 

## Project Goals
The 'Rain in Australia' dataset, downloaded from [Kaggle](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package), is a dataset containing approximately 10 years of daily weather observations recorded from many locations in Australia. The 23 features, in fact, tell the meteorological characteristics of a typical Australian day: humidity percentage, wind direction, wind speed, daily temperature at different times of the day, etc…
The purpose of the dataset is to make binary classification on the 'Rain_Tomorrow' label, i.e. being able to predict whether, on the day following the one for which the features were collected, it will rain or not, therefore RainTomorrow=1 (it will rain), or RainTomorrow =0 (it will not rain).

A total of five scripts were made, the first two relating to the part in Ray, the last three relating to Spark. Each script represents a different configuration with which they were developed. We wanted to implement horizontal scalability for Spark, thus adding more nodes to the cluster, while we used a vertical approach for Ray, building a very powerful machine in terms of calculation:

[1. Ray Script](/src/ray/RayOnGCP.ipynb): Local development on VM, with data loading done via HDFS.

[2. Ray Script](/src/ray/RayOnLocalMachine.ipynb): Development on GCP, with a VM consisting of 16 vCPUs and 60 GB of RAM.

<!-- -->

[1. Spark Script](src/spark/SparkClassification.ipynb): Local development via VM, with data load done via HDFS.

[2. Spark Script](src/spark/SparkClassificationOnCluster.ipynb): Developing on GCP, with a cluster consisting of 1 master and 3 workers, each having 2 vCPUs and 7.5GB of RAM.

[3. Spark Script](src/spark/SparkClassificationOnCluster2.ipynb): Development on GCP, with a cluster composed by 1 master and 3 workers, each of them having 4 vCPUs and 15 GB of RAM.



## Prerequisites
- Ubuntu (22.04.1)
- Python (3.10.6)
- Hadoop (3.3.4)
- Spark (3.3.0)
- Ray (2.1.0)
- Jupyter notebook
- Google Cloud Platform




## Usage
As for the locally executed scripts, they can be tested simply by loading the dataset into your VM, via HDFS. Once Jupyter is started, the above scripts can be run (1.Ray Script, 1.Spark Script). To test the version on gcp, you need to register at https://cloud.google.com/ with your Google account(you can activate a free trial period, with $300 to spend to try out the service), then you need to create a new project with a connected vm, load the dataset into a new bucket and finally create a cluster with the configurations you prefer. You can now test the other scripts on your cluster via the jupyter notebook interface.
