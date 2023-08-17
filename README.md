# Apache Airflow with an Ubuntu Image

**1) Pull the Ubuntu Image:**
   Open your terminal and execute the following command to pull the latest Ubuntu image from Docker Hub:

   ```bash
   docker pull ubuntu:latest
   ```

**2) Run the Ubuntu Container:**
   Run a new Ubuntu container in interactive mode with a bash shell:

   ```bash
   docker run -it --name ubuntu-airflow -p 8080:8080 -e TZ=Your_TIMEZONE ubuntu:latest /bin/bash
   ```

**3) Update and Install Dependencies:**
   Inside the container, update the package repository and install necessary dependencies:

   ```bash
   apt-get update
   apt-get install -y python3-pip
   ```

**4) Install Apache Airflow:**
   Install Apache Airflow using pip:

   ```bash
   pip install apache-airflow
   ```

**5) Initialize Airflow Database:**
   Initialize the Airflow metadata database:

   ```bash
   airflow db init
   ```

**6) Create an Admin User:**
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

**7) Start Airflow Scheduler and Webserver:**
   Start the Airflow scheduler and webserver in the background:
```bash
   export AIRFLOW__CORE__TIMEZONE=Your_TIMEZONE (same as above)
airflow scheduler -D
airflow webserver -D
```

**8) Access the Airflow Web UI:**
   Open your web browser and navigate to `http://localhost:8080`. You'll see the Airflow Web UI. Log in using the credentials you provided earlier.

If you want to exit the container you can do this by typing `exit`. 
And to stop and remove the container, use the following commands:

```bash
docker stop ubuntu-airflow
docker rm ubuntu-airflow
``` 

## How to change PORT number to custom PORT number
### If you are running in docker so you have mapped it to 8080 (default port), so follow below steps to run airflow on custom port-
#### Create different container by following above step 2, but give your custom port instead of 8080 for example see below -
```bash
docker run -it --name container-name -p 1234:1234 -e TZ=UTC ubuntu:latest /bin/bash
```
Here i have used 1234 as my custom port.
Now you need to install python and everything in this again for which you may refer to above steps from 3 to 6.
#### After you are done with above steps now you need to open configuration file to change the port number to your desired port number, so follow below steps-

- Use below command to list the file names in airflow folder
```bash
ls /root/airflow
```
- Here you will find a file name `airflow.cfg` open it using text editor like nano
- If you don't have nano you may install it using command: `apt-get install nano`
- Now open `airflow.cfg` file using command: `nano /root/airflow/airflow.cfg`
- Find this line: `web_server_port = 8080`
- Change `8080` to your desired port which you have chosen while creating container like in my case it was `1234`

### When you are done with above steps follow below steps to start airflow on your custom port-
- Go in your container terminal (you may use this command from your terminal to go in your container terminal: `docker exec -it your-container-name /bin/bash`).
- Now execute this command: 
```bash 
export AIRFLOW__CORE__TIMEZONE=Your_TIMEZONE
airflow scheduler -D
airflow webserver -D 
```
- Then execute below command: 
```bash
airflow webserver -d
```
This will start your airflow in background to your custom PORT.
