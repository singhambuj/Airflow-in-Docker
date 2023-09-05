# To START/STOP  or to check STATUS of AIRFLOW SERVICES

## To START
```bash
sudo systemctl start airflow-webserver.service
sudo systemctl start airflow-scheduler.service
sudo systemctl start airflow-worker.service
```

## To STOP
```bash
sudo systemctl stop airflow-webserver.service
sudo systemctl stop airflow-scheduler.service
sudo systemctl stop airflow-worker.service
```

## To get STATUS
```bash
sudo systemctl status airflow-webserver.service
sudo systemctl status airflow-scheduler.service
sudo systemctl status airflow-worker.service
```
