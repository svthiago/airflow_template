# airflow_template
An apache airflow template with a DAG to do the following tasks in order:
    1 - Get a list of rocket image urls
    2 - Download them
    3 - Notify the user

Docker command to test it:

docker run -ti -p 8080:8080 -v rockets.py:/opt/airflow/dags/rockets.py --entrypoint=/bin/bash --name airflow apache/airflow:2.0.0-python3.8 -c '(airflow db init && airflow users create --username Admin --password Admin --firstname asd --lastname asd --role Admin --email admin@admin.com); airflow webserver & airflow scheduler'
