
# For RabbitMQ Server:-
### To `start` RabbitMQ Server Execute below command:
```bash
sudo systemctl start rabbitmq-server
```
### To `stop` RabbitMQ Server Execute below command:
```bash
sudo systemctl stop rabbitmq-server
```
### To get `status` of RabbitMQ Server Execute below command:
```bash
sudo systemctl status rabbitmq-server
```

# For Apache Airflow:-
- First you need to activate the virtual environment as our virtual environment is present at `/home/airflow/airflow_venv` location so to start that execute below command:
```bash
cd airflow
source airflow_venv/bin/activate
```

- Now you can start airflow webserver, scheduler and main celery worker:-

### To start scheduler in background execute below command:
```bash
airflow scheduler -D
```

### To start webserver in background execute below command:
```bash
airflow webserver -D
```

### To start celery worker in background execute below command:
```bash
airflow celery worker -D
```


Note: The -D flag is used to daemonize the worker process, which means it will run in the background as a separate process.

## To STOP them follow below instructions: 
- Change to this dir: `/home/airflow/airflow`
- There you may find these files: 
```bash
airflow-worker.pid
airflow-scheduler.pid
airflow-webserver.pid
```
- When the services are running then these files will have those process ID
- You can you `cat` command to find those process ID and kill them, like below:

   - To stop webserver execute this command: 
   ```bash
   cat airflow-webserver.pid | xargs kill -SIGTERM
   ```

   - To stop scheduler execute this command: 
   ```bash
   cat airflow-scheduler.pid | xargs kill -SIGTERM
   ```

   - To stop celery worker execute this command: 
   ```bash
   cat airflow-worker.pid | xargs kill -SIGTERM
   ```
