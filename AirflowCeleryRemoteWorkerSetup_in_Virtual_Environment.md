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
- Find `[core]` section and choose `dags_folder` same as master worker, change timezone, choose CeleryExecutor and make load_examples `false` like below-
```bash
[core]
# All workers should have access to the same DAG folder
dags_folder = /opt/airflow/dags
default_timezone = utc
executor = CeleryExecutor
load_examples = False
```
- Find `[database]` section and choose appropriate database connection but make sure you choose `postgresql`
```bash
[database]
sql_alchemy_conn = postgresql://user:password@hostIP/db
```
- Find `[celery]` and choose `broker_url`-
[celery]
# This is url of RabbitMQ for communication between Scheduler and Celery Worker
broker_url = pyamqp://user:password@host:port/
```
### Note: If any section is missing you can create them by yourself just like above
## Now you need to init your db again:
```bash
airflow db init
```
## Start CeleryWorker by using below command:
```bash
airflow celery worker
```
