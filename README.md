# Launch a Docker container with an Ubuntu image, install the latest stable version of Apache Airflow, and bring up the Airflow Web UI

**Pull the Ubuntu Image:**
   Open your terminal and execute the following command to pull the latest Ubuntu image from Docker Hub:

   ```bash
   docker pull ubuntu:latest
   ```

**Run the Ubuntu Container:**
   Run a new Ubuntu container in interactive mode with a bash shell:

   ```bash
   docker run -it --name ubuntu-airflow -p 8080:8080 -e TZ=Your_TIMEZONE ubuntu:latest /bin/bash
   ```

**Update and Install Dependencies:**
   Inside the container, update the package repository and install necessary dependencies:

   ```bash
   apt-get update
   apt-get install -y python3-pip
   ```

**Install Apache Airflow:**
   Install Apache Airflow using pip:

   ```bash
   pip install apache-airflow
   ```

**Initialize Airflow Database:**
   Initialize the Airflow metadata database:

   ```bash
   airflow db init
   ```

**Create an Admin User:**
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

**Start Airflow Scheduler and Webserver:**
   Start the Airflow scheduler and webserver in the background:
```bash
   export AIRFLOW__CORE__TIMEZONE=Your_TIMEZONE (same as above)
airflow scheduler -D
airflow webserver -D
```

**Access the Airflow Web UI:**
   Open your web browser and navigate to `http://localhost:8080`. You'll see the Airflow Web UI. Log in using the credentials you provided earlier.

If you want to exit the container you can do this by typing `exit`. 
And to stop and remove the container, use the following commands:

```bash
docker stop ubuntu-airflow
docker rm ubuntu-airflow
```
