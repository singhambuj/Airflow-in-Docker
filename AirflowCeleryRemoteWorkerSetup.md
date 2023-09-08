## Install Python if you don't have:
```bash
apt-get install -y python3-pip
```
## Install psycopg2 library for database conection:
```bash
pip3 install psycopg2-binary
```
## Install Apache Airflow:
```bash
pip3 install apache-airflow
```
## Install Celery by using below command:
```bash
pip3 install celery
```
## Install SFTP provider by using below command:
```bash
pip3 install apache-airflow-providers-sftp
```
## Upgrade Celery Providers by using below command: 
```bash
pip3 install --upgrade apache-airflow-providers-celery
```

## Initialise database for metadata:
```bash
airflow db init
```
## After that you need to modify `airflow.cfg` file to use this system as remote worker:
### To locate airflow.cfg please change your current working dir to `/root/airflow/` dir
## Use below command to list all the files:
```bash
ls
```
## Open this `airflow.cfg` file using `nano` or any other text editor like below: 
```
nano airflow.cfg
```

## You need to make following changes in `/root/airflow/airflow.cfg` file
```cfg
[core]
# All workers should have access to the same DAG folder
dags_folder = /opt/airflow/dags
default_timezone = utc
executor = CeleryExecutor
load_examples = False

[database]
sql_alchemy_conn = postgresql://user:password@hostIP/db

[celery]
# This is url of RabbitMQ for communication between Scheduler and Celery Worker
broker_url = pyamqp://user:password@host:port/
```
## Now you need to init your db again:
```bash
airflow db init
```
## Start CeleryWorker by using below command:
```bash
airflow celery worker
```
