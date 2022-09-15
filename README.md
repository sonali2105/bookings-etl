# Hotel Data Transformation PySpark

To run this application in standalone mode on your local system there are few pre-requisite for it.

## Pre-requisite

- Install Homebrew
- Install Java
- Install Python
- Install PySpark

## Installation for Mac

### 1. Install Homebrew 

Homebrew is the package manager for mac users which will be useful to install third party packages like java, PySpark.
```sh
# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
This will ask for your root password.

### 2. Install Java
Spark requires java to run the application.Spark specifically uses Py4J for passing the python application code to run on the JVM.
```sh
# Install OpenJDK 11
brew install openjdk@11
```
and download jre from here  - [Download JRE](https://www.java.com/en/download/)



### 3. Install Python
PySpark is used to run Spark jobs in Python hence you also need Python to install on Mac OS.
```sh
# Install Python
brew install python
```

### 4. Install PySpark
PySpark is a Spark library written in Python to run Python applications using Apache Spark capabilities. Spark was basically written in Scala and later on due to its industry adaptation its API PySpark was released for Python using Py4J. Py4J is a Java library that is integrated within PySpark and allows python to dynamically interface with JVM objects, hence to run PySpark you also need Java to be installed along with Python, and Apache Spark. So to use PySpark.
```sh
# Install Apache Spark
brew install apache-spark
```
This installs the latest version of Apache Spark which ideally includes PySpark.
After successful installation of Apache Spark run pyspark from the command line to launch PySpark shell.

# Running the Job
If the pre-requisite already installed then you can directly clone this repository.

```sh
# clone the repository
git clone https://github.com/sonali2105/bookings-etl.git
cd bookings-etl
```
after cloning this repository run the follwoing command to run the script :

```sh
# Stand-alone mode
spark-submit --deploy-mode client ./hotel.py
# Cluster mode
spark-submit --deploy-mode cluster ./hotel.py
```

> cluster mode will not run on your local system for that you'll require a multi machine cluster.


After this this script it'll create the output folder in the current directory with the name of <i>final_hotel_df</i> which will contains the all the output files in the parquet format.
