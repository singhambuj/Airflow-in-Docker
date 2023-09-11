// Will beautify it later


ambujsingh@HAT-IN-LAP-080 ~ % docker run -it --name airflow_log -p 8080:8080 -v /Users/ambujsingh/Documents/Airflow/dags:/root/airflow/dags -v /Users/ambujsingh/Documents/Airflow/logs:/root/airflow/logs -e TZ=UTC ubuntu:latest /bin/bash

root@be3af0a84263:/# apt-get update

root@be3af0a84263:/# apt-get install -y python3-pip

root@be3af0a84263:/# pip3 install psycopg2-binary

root@be3af0a84263:/# pip3 install apache-airflow

root@be3af0a84263:/# airflow db init

root@be3af0a84263:/# apt-get install nano

// edit airflow.cfg

root@be3af0a84263:/#  airflow db migrate

root@be3af0a84263:/# airflow db reset

root@be3af0a84263:/# airflow users create \
    --username airflow \
    --firstname YourFirstName \
    --lastname YourLastName \
    --email admin@example.com \
    --role Admin \
    --password airflow


    root@be3af0a84263:/# airflow scheduler

    root@be3af0a84263:/# pip3 install celery

    root@be3af0a84263:/# pip3 install apache-airflow-providers-sftp

    root@be3af0a84263:/# pip3 install --upgrade apache-airflow-providers-celery

    root@be3af0a84263:/# airflow db migrate

    root@be3af0a84263:/# nano /root/airflow/airflow.cfg 

    root@be3af0a84263:/# airflow scheduler -D

    root@be3af0a84263:~/airflow# airflow webserver -D
