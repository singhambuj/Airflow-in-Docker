ambujsingh@HAT-IN-LAP-080 ~ % docker run -it --name airflow_worker -v /Users/ambujsingh/Documents/Airflow/dags:/root/airflow/dags -v /Users/ambujsingh/Documents/Airflow/logs:/root/airflow/logs -e TZ=UTC ubuntu:latest /bin/bash

root@0571ae8e7cd2:/# apt-get update

root@0571ae8e7cd2:/# apt-get install -y python3-pip

root@0571ae8e7cd2:/# pip3 install psycopg2-binary

root@0571ae8e7cd2:/# pip3 install apache-airflow

root@0571ae8e7cd2:/# pip3 install celery

root@0571ae8e7cd2:/# pip3 install --upgrade apache-airflow-providers-celery

root@0571ae8e7cd2:/# airflow db init

root@0571ae8e7cd2:/# apt-get install nano

root@0571ae8e7cd2:/# nano root/airflow/airflow.cfg 

root@0571ae8e7cd2:/# airflow db migrate

root@0571ae8e7cd2:/# airflow celery worker
