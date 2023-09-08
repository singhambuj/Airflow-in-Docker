## Step 1
```bash
docker run -it --name airflow_worker_in_venv_test -v /Users/ambujsingh/Documents/Airflow/dags:/opt/airflow/dags -e TZ=UTC ubuntu:latest /bin/bash
```
## Step 2
```bash
apt-get update
```
## Step 3
```bash
apt-get install -y python3-pip
```
## Step 4
```bash
pip3 install psycopg2-binary
```
## Step 5
```bash
pip3 install apache-airflow
```
## Step 6
```bash
pip3 install celery
```
## Step 7
```bash
pip3 install apache-airflow-providers-sftp
```
## Step 8
```bash
pip3 install --upgrade apache-airflow-providers-celery
```
## Step 9
```bash
airflow db init
```
## Step 10
```bash
apt-get install nano
```
## Step 11
```bash
ls
```
## Step 12
```bash
nano /root/airflow/airflow.cfg
```
## Step 13
```bash
# changes in airflow.cfg
```
## Step 14
```bash
airflow db init
```
## `OR` 
```bash
airflow db migrate
```
## Step 15
```bash
airflow celery worker
```
