# Airflow-in-Docker
## Find docker container IP
```bash
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container name>
```
In this i have included command history of each setup, i have removed unnecessary installation info after each command execution to make it short.
You may refer the desired file according to your need.

## To run RabbitMQ in docker use this command:
`docker run -d --hostname rmq --name rabbit-server -p 15672:15672 -p 5672:5672 rabbitmq:3-management`

## Find the Process ID (PID) of the Airflow Web Server:
Open a terminal or command prompt and use a command like ps or pgrep to find the PID of the Airflow web server process. For example:
ps aux | grep 'airflow webserver'
kill <PID>
