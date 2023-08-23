### Changes to be made in `/root/airflow/airflow.cfg` file
```cfg
[core]
dags_folder = /opt/airflow/dags
default_timezone = utc
executor = CeleryExecutor
load_examples = False

[database]
sql_alchemy_conn = postgres://postgres:postgres@172.17.0.3:5432/postgres

[celery]
\# This is url of RabbitMQ for communication between Scheduler and Celery Worker
broker_url = pyamqp://guest:guest@172.17.0.4:5672/
```

Last login: Thu Aug 24 00:12:33 on ttys010
env /usr/bin/arch -x86_64 /bin/zsh --login
singh@HAT ~ % env /usr/bin/arch -x86_64 /bin/zsh --login
### singh@HAT ~ % docker run -it --name airflow_v1 -v /Users/singh/Documents/Airflow/dags:/opt/airflow/dags -e TZ=UTC ubuntu:latest /bin/bash 
### root@2a:/# apt-get update
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy InRelease [270 kB]
root@2a:/# 
### root@2a:/# apt-get install -y python3-pip
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
root@2a:/# 
### root@2a:/# pip3 install psycopg2-binary
Collecting psycopg2-binary
root@2a:/# 
### root@2a:/# pip3 install apache-airflow
Collecting apache-airflow
  Downloading apache_airflow-2.7.0-py3-none-any.whl (12.9 MB)
root@2a:/# 
### root@2a:/# airflow db init
WARNI [airflow.models.crypto] empty cryptography key - values will not be stored encrypted.
Initialization done
root@2a:/# 
### root@2a:/# cd /root/airflow/ 
### root@2a:~/airflow# ls
airflow.cfg  airflow.db  logs
root@2a:~/airflow# 
### root@2a:~/airflow# apt-get install nano
Reading package lists... Done
root@2a:~/airflow# 
### root@2a:~/airflow# nano airflow.cfg
root@2a:~/airflow# 
### root@2a:~/airflow# airflow db init
/usr/local/lib/python3.10/dist-packages/airflow/configuration.py:799 FutureWarning: Bad scheme in Airflow configuration core > sql_alchemy_conn: `postgres`. As of SQLAlchemy 1.4 (adopted in Airflow 2.3) this is no longer supported.  You must change to `postgresql` before the next Airflow release.
[2023-08-23T19:15:12.087+0000] {cli_parser.py:56} ERROR - Failed to load CLI commands from executor: CeleryExecutor
Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/airflow/cli/cli_parser.py", line 52, in <module>
    executor, _ = ExecutorLoader.import_default_executor_cls(validate=False)
root@2a:~/airflow# 
### root@2a:~/airflow# pip3 install celery
Collecting celery
  Downloading celery-5.3.1-py3-none-any.whl (420 kB)
root@2a:~/airflow# 
### root@2a:~/airflow# pip3 install apache-airflow-providers-sftp
Collecting apache-airflow-providers-sftp
  Downloading apache_airflow_providers_sftp-4.5.0-py3-none-any.whl (24 kB)
root@2a:~/airflow# 
### root@2a:~/airflow# pip3 install --upgrade apache-airflow-providers-celery
Collecting apache-airflow-providers-celery
  Downloading apache_airflow_providers_celery-3.3.2-py3-none-any.whl (31 kB)
Requirement already satisfied: celery<6,>=5.2.3 in /usr/local/lib/python3.10/dist-packages (from apache-airflow-providers-celery) (5.3.1)
root@2a:~/airflow# 
### root@2a:~/airflow# airflow celery worker
/usr/local/lib/python3.10/dist-packages/airflow/configuration.py:799 FutureWarning: Bad scheme in Airflow configuration core > sql_alchemy_conn: `postgres`. As of SQLAlchemy 1.4 (adopted in Airflow 2.3) this is no longer supported.  You must change to `postgresql` before the next Airflow release.
[2023-08-23T19:16:59.164+0000] {configuration.py:2053} INFO - Creating new FAB webserver config file in: /root/airflow/webserver_config.py
[2023-08-23 19:16:59 +0000] [4292] [INFO] Starting gunicorn 21.2.0
[2023-08-23 19:16:59 +0000] [4292] [INFO] Listening at: http://[::]:8793 (4292)
[2023-08-23 19:16:59 +0000] [4292] [INFO] Using worker: sync
[2023-08-23 19:16:59 +0000] [4293] [INFO] Booting worker with pid: 4293
[2023-08-23 19:16:59 +0000] [4294] [INFO] Booting worker with pid: 4294
/usr/local/lib/python3.10/dist-packages/celery/platforms.py:829 SecurityWarning: You're running the worker with superuser privileges: this is
absolutely not recommended!

Please specify a different user using the --uid option.

User information: uid=0 euid=0 gid=0 egid=0

 
 -------------- celery@2a v5.3.1 (emerald-rush)
--- ***** ----- 
-- ******* ---- Linux-5.15.49-linuxkit-pr-aarch64-with-glibc2.35 2023-08-23 19:16:59
- *** --- * --- 
- ** ---------- [config]
- ** ---------- .> app:         airflow.providers.celery.executors.celery_executor:0xffff92f1ef50
- ** ---------- .> transport:   amqp://guest:**@172.17.0.4:5672//
- ** ---------- .> results:     postgresql://postgres:**@172.17.0.3:5432/postgres
- *** --- * --- .> concurrency: 16 (prefork)
-- ******* ---- .> task events: OFF (enable -E to monitor tasks in this worker)
--- ***** ----- 
 -------------- [queues]
                .> default          exchange=default(direct) key=default
                

[tasks]
  . airflow.providers.celery.executors.celery_executor_utils.execute_command

[2023-08-23 19:17:00,742: WARNING/MainProcess] /usr/local/lib/python3.10/dist-packages/celery/worker/consumer/consumer.py:498: CPendingDeprecationWarning: The broker_connection_retry configuration setting will no longer determine
whether broker connection retries are made during startup in Celery 6.0 and above.
If you wish to retain the existing behavior for retrying connections on startup,
you should set broker_connection_retry_on_startup to True.
  warnings.warn(

[2023-08-23 19:17:00,751: INFO/MainProcess] Connected to amqp://guest:**@172.17.0.4:5672//
[2023-08-23 19:17:00,751: WARNING/MainProcess] /usr/local/lib/python3.10/dist-packages/celery/worker/consumer/consumer.py:498: CPendingDeprecationWarning: The broker_connection_retry configuration setting will no longer determine
whether broker connection retries are made during startup in Celery 6.0 and above.
If you wish to retain the existing behavior for retrying connections on startup,
you should set broker_connection_retry_on_startup to True.
  warnings.warn(

[2023-08-23 19:17:00,753: INFO/MainProcess] mingle: searching for neighbors
[2023-08-23 19:17:01,789: INFO/MainProcess] mingle: sync with 1 nodes
[2023-08-23 19:17:01,791: INFO/MainProcess] mingle: sync complete
[2023-08-23 19:17:01,814: INFO/MainProcess] celery@2a ready.

[2023-08-23 19:21:37,194: INFO/MainProcess] sync with celery@9d00e02b0952
[2023-08-23 19:21:46,177: INFO/MainProcess] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[2e88f910-8f83-4c1b-ba29-236857213c28] received
[2023-08-23 19:21:46,182: INFO/ForkPoolWorker-16] [2e88f910-8f83-4c1b-ba29-236857213c28] Executing command in Celery: ['airflow', 'tasks', 'run', 'hello_dag', 'test1', 'manual__2023-08-23T19:21:45.011362+00:00', '--local', '--subdir', 'DAGS_FOLDER/hello.py']
[2023-08-23 19:21:46,214: INFO/ForkPoolWorker-16] Filling up the DagBag from /opt/airflow/dags/hello.py
[2023-08-23 19:21:46,327: WARNING/ForkPoolWorker-16] Changing /root/airflow/logs/dag_id=hello_dag/run_id=manual__2023-08-23T19:21:45.011362+00:00/task_id=test1 permission to 509
[2023-08-23 19:21:46,328: INFO/ForkPoolWorker-16] Running <TaskInstance: hello_dag.test1 manual__2023-08-23T19:21:45.011362+00:00 [queued]> on host 2a
[2023-08-23 19:21:46,570: INFO/ForkPoolWorker-16] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[2e88f910-8f83-4c1b-ba29-236857213c28] succeeded in 0.3918085830000564s: None











