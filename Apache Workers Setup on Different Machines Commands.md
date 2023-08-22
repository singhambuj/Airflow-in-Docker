## This is a command history text file which i have executed to create workers make it look good when you are free. i have deleted those long installation info after each task-
### Keep in mind while running this and trying to trigger the DAG in main it was throwing error which you can see after starting `airflow celery worker` that is last command in this file. If you fix it try to update that command here too-
in `airflow.cfg` i have used broker_url of that main container rabbitmq which will use it as a worker 
`broker_url = pyamqp://guest:guest@172.17.0.2:5672/`
that IP address is of that container ip in which that rabbitmq is running


Last login: Tue Aug 22 18:46:33 on ttys011
env /usr/bin/arch -x86_64 /bin/zsh --login
ambujsingh@HAT-IN-LAP-080 ~ % env /usr/bin/arch -x86_64 /bin/zsh --login
### docker run -it --name airflow_worker2 -v /Users/ambujsingh/Documents/Airflow/dags:/opt/airflow/dags -e TZ=UTC ubuntu:latest /bin/bash
### root@c7:/# apt-get update
### apt-get install -y python3-pip
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy InRelease [270 kB]
Get:2 http://ports.ubuntu.com/ubuntu-ports jammy-updates InRelease [119 kB]
root@c7:/# 
root@c7:/# 
### root@c7:/# pip3 install psycopg2-binary
Collecting psycopg2-binary
root@c7:/# 
### root@c7:/# pip3 install apache-airflow
Collecting apache-airflow
  Downloading apache_airflow-2.7.0-py3-none-any.whl (12.9 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 12.9/12.9 MB 32.7 MB/s eta 0:00:00
Successfully installed Babel-2.12.1 Flask-Babel-2.0.0 Flask-JWT-Extended-4.5.2 Flask-Limiter-3.3.1 Flask-SQLAlchemy-2.5.1 Mako-1.2.4 PyYAML-6.0.1 WTForms-3.0.1 WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
root@c7:/# 
### root@c7:/# airflow db migrate
DB: sqlite:////root/airflow/airflow.db
Performing upgrade to the metadata database sqlite:////root/airflow/airflow.db
Database migrating done! 
### root@c7:/# ls /root/airflow/
airflow.cfg  airflow.db  logs
### root@c7:/# apt-get install nano
Reading package lists... Done
root@c7:/# 
### root@c7:/# nano /root/airflow/airflow.cfg
root@c7:/# 
### root@c7:/# airflow db migrate
[2023-08-22T13:56:41.503+0000] {cli_parser.py:56} ERROR - Failed to load CLI commands from executor: CeleryExecutor
Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/airflow/cli/cli_parser.py", line 52, in <module>
    executor, _ = ExecutorLoader.import_default_executor_cls(validate=False)
  File "/usr/local/lib/python3.10/dist-packages/airflow/executors/executor_loader.py", line 169, in import_default_executor_cls
    executor, source = cls.import_executor_cls(executor_name, validate=validate)
  File "/usr/local/lib/python3.10/dist-packages/airflow/executors/executor_loader.py", line 143, in import_executor_cls
    return _import_and_validate(cls.executors[executor_name]), ConnectorSource.CORE
  File "/usr/local/lib/python3.10/dist-packages/airflow/executors/executor_loader.py", line 137, in _import_and_validate
    executor = import_string(path)
  File "/usr/local/lib/python3.10/dist-packages/airflow/utils/module_loading.py", line 37, in import_string
    module = import_module(module_path)
  File "/usr/lib/python3.10/importlib/__init__.py", line 126, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
  File "<frozen importlib._bootstrap>", line 1050, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1027, in _find_and_load
  File "<frozen importlib._bootstrap>", line 992, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 241, in _call_with_frames_removed
  File "<frozen importlib._bootstrap>", line 1050, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1027, in _find_and_load
  File "<frozen importlib._bootstrap>", line 992, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 241, in _call_with_frames_removed
  File "<frozen importlib._bootstrap>", line 1050, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1027, in _find_and_load
  File "<frozen importlib._bootstrap>", line 1004, in _find_and_load_unlocked
ModuleNotFoundError: No module named 'airflow.providers.celery'
[2023-08-22T13:56:41.503+0000] {cli_parser.py:57} ERROR - Ensure all dependencies are met and try again. If using a Celery based executor install a 3.3.0+ version of the Celery provider. If using a Kubernetes executor, install a 7.4.0+ version of the CNCF provider
DB: sqlite:////root/airflow/airflow.db
Performing upgrade to the metadata database sqlite:////root/airflow/airflow.db
[2023-08-22T13:56:41.895+0000] {migration.py:213} INFO - Context impl SQLiteImpl.
[2023-08-22T13:56:41.896+0000] {migration.py:216} INFO - Will assume non-transactional DDL.
[2023-08-22T13:56:41.896+0000] {db.py:1633} INFO - Creating tables
INFO  [alembic.runtime.migration] Context impl SQLiteImpl.
INFO  [alembic.runtime.migration] Will assume non-transactional DDL.
WARNI [unusual_prefix_13903d1433e73a905598409829be4c61c9cdea5f_example_kubernetes_executor] The example_kubernetes_executor example DAG requires the kubernetes provider. Please install it with: pip install apache-airflow[cncf.kubernetes]
WARNI [unusual_prefix_de310399792f7c66d0607289cf7f70223c00f7ca_example_python_operator] The virtalenv_python example task requires virtualenv, please install it.
WARNI [unusual_prefix_e1e1e746b8b87627f53519aca03f086299788fc2_tutorial_taskflow_api_virtualenv] The tutorial_taskflow_api_virtualenv example DAG requires virtualenv, please install it.
WARNI [unusual_prefix_4c1c0063a36d033a56d4343efc723c3a45c1bd59_example_local_kubernetes_executor] Could not import DAGs in example_local_kubernetes_executor.py
Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/airflow/example_dags/example_local_kubernetes_executor.py", line 37, in <module>
    from kubernetes.client import models as k8s
ModuleNotFoundError: No module named 'kubernetes'
WARNI [unusual_prefix_4c1c0063a36d033a56d4343efc723c3a45c1bd59_example_local_kubernetes_executor] Install Kubernetes dependencies with: pip install apache-airflow[cncf.kubernetes]
WARNI [unusual_prefix_45fb6c494355141389b80b1d50f93a2d0d272ee8_workday] Could not import pandas. Holidays will not be considered.
Database migrating done!
root@c7:/# 
### root@c7:/# pip install apache-airflow[celery]
Requirement already satisfied: apache-airflow[celery] in /usr/local/lib/python3.10/dist-packages (2.7.0)
root@c7:/# 
### root@c7:/# airflow db migrate
DB: sqlite:////root/airflow/airflow.db
Performing upgrade to the metadata database sqlite:////root/airflow/airflow.db
[2023-08-22T13:57:48.572+0000] {migration.py:213} INFO - Context impl SQLiteImpl.
Database migrating done!
root@c7:/# 
### root@c7:/# airflow celery worker
[2023-08-22T13:58:15.303+0000] {configuration.py:2053} INFO - Creating new FAB webserver config file in: /root/airflow/webserver_config.py
[2023-08-22 13:58:15 +0000] [4284] [INFO] Starting gunicorn 21.2.0
[2023-08-22 13:58:15 +0000] [4284] [INFO] Listening at: http://[::]:8793 (4284)
[2023-08-22 13:58:15 +0000] [4284] [INFO] Using worker: sync
[2023-08-22 13:58:15 +0000] [4285] [INFO] Booting worker with pid: 4285
[2023-08-22 13:58:15 +0000] [4286] [INFO] Booting worker with pid: 4286
/usr/local/lib/python3.10/dist-packages/celery/platforms.py:829 SecurityWarning: You're running the worker with superuser privileges: this is
absolutely not recommended!

Please specify a different user using the --uid option.

User information: uid=0 euid=0 gid=0 egid=0

 
 -------------- celery@29970dff84c7 v5.3.1 (emerald-rush)
--- ***** ----- 
-- ******* ---- Linux-5.15.49-linuxkit-pr-aarch64-with-glibc2.35 2023-08-22 13:58:15
- *** --- * --- 
- ** ---------- [config]
- ** ---------- .> app:         airflow.providers.celery.executors.celery_executor:0xffffb2b16fb0
- ** ---------- .> transport:   amqp://guest:**@172.17.0.2:5672//
- ** ---------- .> results:     sqlite:////root/airflow/airflow.db
- *** --- * --- .> concurrency: 16 (prefork)
-- ******* ---- .> task events: OFF (enable -E to monitor tasks in this worker)
--- ***** ----- 
 -------------- [queues]
                .> default          exchange=default(direct) key=default
                

[tasks]
  . airflow.providers.celery.executors.celery_executor_utils.execute_command

[2023-08-22 13:58:17,059: WARNING/MainProcess] /usr/local/lib/python3.10/dist-packages/celery/worker/consumer/consumer.py:498: CPendingDeprecationWarning: The broker_connection_retry configuration setting will no longer determine
whether broker connection retries are made during startup in Celery 6.0 and above.
If you wish to retain the existing behavior for retrying connections on startup,
you should set broker_connection_retry_on_startup to True.
  warnings.warn(

[2023-08-22 13:58:17,065: INFO/MainProcess] Connected to amqp://guest:**@172.17.0.2:5672//
[2023-08-22 13:58:17,065: WARNING/MainProcess] /usr/local/lib/python3.10/dist-packages/celery/worker/consumer/consumer.py:498: CPendingDeprecationWarning: The broker_connection_retry configuration setting will no longer determine
whether broker connection retries are made during startup in Celery 6.0 and above.
If you wish to retain the existing behavior for retrying connections on startup,
you should set broker_connection_retry_on_startup to True.
  warnings.warn(

[2023-08-22 13:58:17,066: INFO/MainProcess] mingle: searching for neighbors
[2023-08-22 13:58:18,079: INFO/MainProcess] mingle: sync with 1 nodes
[2023-08-22 13:58:18,081: INFO/MainProcess] mingle: sync complete
[2023-08-22 13:58:18,091: INFO/MainProcess] celery@29970dff84c7 ready.
[2023-08-22 13:58:31,945: INFO/MainProcess] sync with celery@e5d1b0a3bb35
[2023-08-22 13:58:50,381: ERROR/MainProcess] Received unregistered task of type 'airflow.executors.celery_executor.execute_command'.
The message has been ignored and discarded.

Did you remember to import the module containing this task?
Or maybe you're using relative imports?

Please see
https://docs.celeryq.dev/en/latest/internals/protocol.html
for more information.

The full contents of the message body was:
'[[["airflow", "tasks", "run", "hello_worker", "task_1", "manual__2023-08-22T13:58:50.199718+00:00", "--local", "--subdir", "DAGS_FOLDER/17_remote_hello_two_task.py"]], {}, {"callbacks": null, "errbacks": null, "chain": null, "chord": null}]' (240b)

The full contents of the message headers:
{'lang': 'py', 'task': 'airflow.executors.celery_executor.execute_command', 'id': '4990deec-158a-4aab-b028-ecec42d15ba9', 'shadow': None, 'eta': None, 'expires': None, 'group': None, 'group_index': None, 'retries': 0, 'timelimit': [None, None], 'root_id': '4990deec-158a-4aab-b028-ecec42d15ba9', 'parent_id': None, 'argsrepr': "[['airflow', 'tasks', 'run', 'hello_worker', 'task_1', 'manual__2023-08-22T13:58:50.199718+00:00', '--local', '--subdir', 'DAGS_FOLDER/17_remote_hello_two_task.py']]", 'kwargsrepr': '{}', 'origin': 'gen5988@2a8a3823f3e0', 'ignore_result': False, 'stamped_headers': None, 'stamps': {}}

The delivery info for this task is:
{'consumer_tag': 'None4', 'delivery_tag': 2, 'redelivered': False, 'exchange': '', 'routing_key': 'default'}
Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/celery/worker/consumer/consumer.py", line 642, in on_task_received
    strategy = strategies[type_]
KeyError: 'airflow.executors.celery_executor.execute_command'

