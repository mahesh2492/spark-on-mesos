# spark-on-mesos wordcount-example

Simple word count example using spark and running it on mesos.

# Clone the repo

```
git clone https://github.com/mahesh2492/spark-on-mesos.git
cd spark-on-mesos
```
# Build the code

If this is your first time running SBT, you have to download the used dependencies.
```
cd spark-on-mesos
sbt clean compile
```
# To run application locally, do following things:

First change the spark master in application.conf and run following command
```
sbt run
```
To run it on mesos, first create the jar to deploy. For that run following command

```
sbt assembly
 ```
 It will create the fat jar of wordcount application.
 
 Deploy the jar using spark-submit
 
 ```
 cd spark-2.2.0-bin-hadoop2.7
 ./bin/spark-submit --class "rdd.WordCount" --master mesos://127.0.0.1:5050 file://path/target/scala-2.11/spark-on-mesos-assembly-1.0.jar
```




