# Apache Airflow with an Ubuntu Image & Custom PORT

### 1) Pull the Ubuntu Image:
   Open your terminal and execute the following command to pull the latest Ubuntu image from Docker Hub:

   ```bash
   docker pull ubuntu:latest
   ```

### 2) Run the Ubuntu Container:
   Run a new Ubuntu container in interactive mode with a bash shell:

   ```bash
   docker run -it --name air-flow -p 3234:3234 -v /Users/ambujsingh/Documents/Airflow/dags:/opt/airflow/dags -e TZ=Your_TIMEZONE ubuntu:latest /bin/bash
   ```
   #### Explanation of Above command:

   **3) Update, Install Apache Airflow & It's Dependencies:**
   Inside the container, update the package repository and install necessary dependencies:

   ```bash
   apt-get update
   apt-get install -y python3-pip
   ```
   ```bash
   pip3 install psycopg2-binary
   ```

### 4) Install Apache Airflow:
   Install Apache Airflow using pip:

   ```bash
   pip3 install apache-airflow
   ```

### Open another `terminal` (normal terminal) to install postgres in different container, you may install postgres in same container also by following same below steps-
   ```bash
   docker pull postgres
   ```
   ```bash 
   docker run --name postgres-container -e POSTGRES_USER=user -e POSTGRES_PASSWORD=password -d -p 5432:5432 postgres
   ```
   It will create postgres container enter in bash using command: `docker exec -it postgres-container bash`
      Then execute this `psql -U my-postgres-user` to enter in interactive session with the PostgreSQL database. Create a database or your choice.
      When you are done with above steps, then follow below steps to link this with airflow.

  

## Now you need to come back to air-flow container and configure `airflow.cfg` with appropriate port and database-
- Use below command to list the file names in airflow folder
```bash
ls /root/airflow
```
- Here you will find a file name `airflow.cfg` open it using text editor like nano
- If you don't have nano you may install it using command: `apt-get install nano`
- Now open `airflow.cfg` file using command: `nano /root/airflow/airflow.cfg`
- Find this line: `web_server_port = 8080`
- Change `8080` to your desired port which you have chosen while creating container like in my case it was `3234`
* Find below line- 
```bash
[database]
sql_alchemy_conn = sqlite:////root/airflow/airflow.db
```
Change that with this -
```bash

[database]
sql_alchemy_conn = postgres://username:password@postgres-host:5432/dbname


```
- Make sure you replace 'username', 'password', 'dbname' and 'postgres-host' with actual names.
- For `postgres-host` you need to enter HOST-IP of postgres container which you can get by executing this command `docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container_name_or_id>` in your normal terminal.

- Then save that `airflow.cfg` file by pressing `ctrl+o` then press `enter` then press `ctrl+x` to exit.


### 5) Initialize Airflow Database:
   Initialize the Airflow metadata database:

   ```bash
   airflow db init
   ```

### 6) Create an Admin User:
   Create an admin user for the Airflow Web UI:

   ```bash
   airflow users create \
       --username admin \
       --firstname YourFirstName \
       --lastname YourLastName \
       --email admin@example.com \
       --role Admin \
       --password admin
   ```

### 7) Start Airflow Scheduler and Webserver:
   Start the Airflow scheduler and webserver in the background:
```bash
   export AIRFLOW__CORE__TIMEZONE=Your_TIMEZONE (same as above)
airflow scheduler -D
airflow webserver -D
```

### 8) Access the Airflow Web UI:
   Open your web browser and navigate to `http://localhost:3234` if you have chosen another PORT make sure you write same in URL. You'll see the Airflow Web UI. Log in using the credentials you provided earlier.

### 9) Change from SequentialExecutor to LocalExecutor
You can see this on web UI `Do not use the SequentialExecutor in production. Click here for more information.`

#### Open `airflow.cfg` file by following above method and find this line-
```bash
executor = SequentialExecutor
```
Change it to-
```bash
executor = LocalExecutor
```




### If you want to exit the container you can do this by typing `exit`. 
#### And to stop and remove the container, use the following commands:

```bash
docker stop container-name
docker rm container-name
``` 

##### If you get warning like this `/usr/local/lib/python3.10/dist-packages/airflow/configuration.py:421 FutureWarning: Bad scheme in Airflow configuration core > sql_alchemy_conn: `postgres`. As of SQLAlchemy 1.4 (adopted in Airflow 2.3) this is no longer supported.  You must change to `postgresql` before the next Airflow release.` while executing this command `airflow config get-value api auth_backends` then open `airflow.cfg` file again and change [database] section like below you just need to replace `postgres` to `postgresql` nothing else. see below line-


```bash
sql_alchemy_conn = postgresql://postgres:postgres@172.17.0.3:5432/postgres
```

### Activate to accept API resquest 
#### Open `airflow.cfg` file again and do this- 
```bash
# auth_backend = airflow.api.auth.backend.deny_all
auth_backend = airflow.api.auth.backend.basic_auth
```
In above i just commented above line and written new to accept aip requests.


### Change timezone of airflow 
Open `airflow.cfg` file again and find this line-
```bash
default_timezone = UTC
```
change it to your desired timezone like i have changed it to Indian Standard Time
```bash
default_timezone = IST
``` 

## Run DAG using curl command
```bash
# Replace these placeholders with your actual values
AIRFLOW_API_URL="http://airflow-server:8080/api/v1/dags/<your_dag_id>/dagRuns"
AUTH_TOKEN="your_auth_token"

# Create a DAG run for a specific DAG
curl -X POST \
  -H "Authorization: Bearer $AUTH_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"dag_run_id": "your_run_id"}' \
  "$AIRFLOW_API_URL"
```

You can modify -d to give it execution_date and other parameters based on your requirements.
