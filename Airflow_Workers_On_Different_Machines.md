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
