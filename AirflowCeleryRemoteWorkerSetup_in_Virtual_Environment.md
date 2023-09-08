## Setup Airflow Remote Worker

### Install Python if you don't have by using below command:
```bash
apt-get install -y python3-pip
```

### Install python venv package by using below command:
```bash
apt install python3.10-venv
```

### Create virtual environment by using below command:
```bash
python3 -m venv airflow_env
```

### Activate virtual environment by using below command:
```bash
source airflow_env/bin/activate
```

### Install psycopg2 library for database connection by using below command:
```bash
pip3 install psycopg2-binary
```

### Install Apache Airflow by using below command:
```bash
pip3 install apache-airflow
```

### Install Celery by using below command:
```bash
pip3 install celery
```

### Install SFTP provider by using below command:
```bash
pip3 install apache-airflow-providers-sftp
```

### Upgrade Celery Providers by using below command: 
```bash
pip3 install --upgrade apache-airflow-providers-celery
```

### Initialise database for metadata by using below command:
```bash
airflow db init
```

### After that you need to modify `airflow.cfg` file to use this system as a remote worker:

### To locate airflow.cfg please change your current working dir to `/root/airflow/` dir

### Use below command to list all the files :
```bash
ls
```
### Open this `airflow.cfg` file using `nano` or any other text editor like below: 
```
- Install `nano` by using `apt-get install nano` command then execute below command.
nano airflow.cfg
```

### You need to make following changes in `/root/airflow/airflow.cfg` file:
- *Find `[core]` section and choose `dags_folder` same as master worker, change `default_timezone`, choose `executor` as `CeleryExecutor` and make `load_examples` `false` like below-*
```bash
[core]
# All workers should have access to the same DAG folder
dags_folder = /opt/airflow/dags
default_timezone = utc
executor = CeleryExecutor
load_examples = False
```

- *Find `[database]` section and choose appropriate database connection but make sure you choose `postgresql`-*
```bash
[database]
sql_alchemy_conn = postgresql://user:password@hostIP/db
```

- *Find `[celery]` section and choose `broker_url`-*
```bash
[celery]
# This is url of RabbitMQ for communication between Scheduler and Celery Worker
broker_url = pyamqp://user:password@host:port/
```
#### Save above file by pressing `ctrl+o` and press `return` then `ctrl+x` to exit from the file.

#### Note: If any section is missing you can create them by yourself just like above
### Now you need to migrate your db by using below command:
```bash
airflow db migrate
```
- Note: If you see any error message while migrating it means you have some missing libraries in your remote worker so you can just install them and then use `airflow db migrate` command again.

### Start CeleryWorker by using below command:
```bash
airflow celery worker
```

## To add `airflow celery worker` as a service please follow below instructions:

### Install `sudo` if you don't have by following below command:
```bash
apt-get install sudo
```

### Create a `airflow-worker.service` file by using below command:
```bash
sudo nano /etc/systemd/system/airflow-worker.service
```

### Add below contents in airflow-worker.service` file:

#### Note: make you sure you follow your `path/to/dir` where each appropriate file is present.
```bash
[Unit]
Description=Airflow worker daemon
After=network.target mysql.service
Wants=mysql.service

[Service]
User=airflow
Group=airflow
Type=simple
#Environment="PATH=/home/airflow/airflow_venv/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ExecStart=/usr/bin/bash -c 'source /home/airflow/airflow_venv/bin/activate ; airflow celery worker --pid /home/airflow/airflow/airflow-worker.pid'
Restart=on-failure
RestartSec=5s
PrivateTmp=true

[Install]
WantedBy=multi-user.target

```
#### Save above file by pressing `ctrl+o` and press `return` then `ctrl+x` to exit from the file.

###  Load Enable and Start the Service
```bash
sudo systemctl daemon-reload
```

### Now enable the service `airflow-worker.service` by executing below command
```bash
sudo systemctl enable airflow-worker.service
```

### To start the service execute below command:
```bash
sudo systemctl start airflow-worker.service
```

### To get status of the service execute below command:
```bash
sudo systemctl status airflow-worker.service
```

### To stop the service execute below command:
```bash
sudo systemctl stop airflow-worker.service
```
