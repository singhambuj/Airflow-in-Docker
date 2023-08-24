## Remote Worker Setup Overview is below:-
**Note:** Make sure you have RabbitMQ installed and running for broker_url. 

Apache Airflow can be configured to run on multiple workers to distribute the task execution load. However, it's important to clarify that when we talk about "workers" in the context of Airflow, we are usually referring to the processes responsible for executing tasks within a single Airflow deployment, rather than separate physical machines.

In Airflow, a typical setup involves the following components:

1. **Airflow Web Server**:
   This component provides the web-based user interface for managing and monitoring Airflow tasks, DAGs, and executions. It's responsible for handling user interactions and displaying task and DAG status.

2. **Airflow Scheduler**:
   The scheduler component is responsible for determining when and how to execute tasks based on their dependencies and the configured schedule. It schedules tasks to be executed by workers.

3. **Database Backend**:
   Airflow uses a database backend to store metadata related to tasks, DAGs, execution history, and other information.

4. **Airflow Workers**:
   Workers are processes responsible for executing the actual tasks within DAGs. They receive tasks from the scheduler and execute them based on dependencies and task definitions.

You can indeed configure multiple workers to work in tandem with a single Airflow web server and scheduler. This setup is known as a distributed or multi-worker setup and allows you to handle larger task loads and distribute the processing power.

To set up multiple workers:

1. **Install Dependencies**:
   Install Apache Airflow on all the machines that will act as workers. You'll need to ensure that the workers have access to the same DAG code and dependencies.

2. **Configure CeleryExecutor**:
   Use the CeleryExecutor in your Airflow configuration (`airflow.cfg`) to configure the execution of tasks by Celery workers. This involves specifying the Celery broker URL (RabbitMQ, Redis, etc.) and other relevant settings.

3. **Start Workers**:
   Start Celery worker processes on each worker machine using the following command:

   ```
   airflow celery worker
   ```

   The workers will connect to the same message broker and listen for task execution instructions from the scheduler.

4. **Start Airflow Web Server and Scheduler**:
   Start the Airflow web server and scheduler on a designated machine. The scheduler will distribute tasks to the available workers based on the configured execution parameters, task dependencies, and task affinity.

5. **Trigger DAGs**:
   Trigger DAGs through the Airflow web UI as usual. The scheduler will distribute tasks among the available workers, ensuring efficient task execution.

Remember that in a distributed setup, all workers should have access to the same DAG definitions and dependencies to ensure consistent execution. Also, appropriate network and firewall configurations must be in place to allow communication between the components.

## Celery Overview is Below:-
Celery is an open-source distributed task queue system for executing tasks asynchronously in a distributed manner. It is designed to handle tasks that are time-consuming, can be parallelized, or need to be executed in the background, separate from the main application flow. Celery allows you to offload tasks from the main application, freeing it to handle other important functions.

Key features of Celery include:

1. **Distributed Execution**: Celery enables you to distribute tasks across multiple worker processes or machines, making it suitable for handling heavy workloads and improving performance.

2. **Task Scheduling**: You can schedule tasks to be executed at specific times or intervals, making it useful for recurring tasks or periodic data processing.

3. **Asynchronous Execution**: Celery tasks run asynchronously, meaning that they don't block the main application's execution. This is especially useful for tasks that might take a long time to complete.

4. **Parallel Processing**: Celery supports parallel processing, allowing you to divide tasks into smaller units that can be processed concurrently, improving overall task execution speed.

5. **Message Brokers**: Celery uses a message broker (e.g., RabbitMQ, Redis) to handle the communication between the main application and worker processes. This allows tasks to be queued, routed, and executed across different components.

6. **Result Backend**: Celery provides a result backend where the results of completed tasks can be stored. This is useful for tasks that produce output or results that need to be accessed later.

7. **Fault Tolerance**: Celery handles task failures gracefully by providing mechanisms for retrying failed tasks, setting task timeouts, and managing task states.

8. **Scalability**: With Celery, you can easily scale your application by adding more worker processes or machines as needed to handle increased workloads.

Celery is often used in conjunction with other technologies and frameworks to build complex, distributed systems. It's commonly used in web applications, data processing pipelines, and any scenario where tasks need to be executed asynchronously and efficiently. In the context of Apache Airflow, Celery is used as one of the available executors to distribute and manage the execution of tasks defined in Airflow DAGs.


## Commands Execution is below:-

### Changes to be made in `/root/airflow/airflow.cfg` file
#### Those IP Addresses of Host Names are that IP of container in which they running everytime you restart it will change so make sure you write exact one you can get those IP of any container using this command `docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container name>`
```cfg
[core]
dags_folder = /opt/airflow/dags
default_timezone = utc
executor = CeleryExecutor
load_examples = False

[database]
sql_alchemy_conn = postgres://postgres:postgres@172.17.0.3:5432/postgres

[celery]
# This is url of RabbitMQ for communication between Scheduler and Celery Worker
broker_url = pyamqp://guest:guest@172.17.0.4:5672/
```
## Commands Execution Starting Now...
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











