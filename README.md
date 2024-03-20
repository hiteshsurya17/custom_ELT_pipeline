# Custom_elt_pipeline
This is a complete ELT pipeline connecting source_postgres_db to destination_postgres_db and performing transformations using dbt and orchestrated using apache-airflow .\
All these services are run using docker images in a single environment .\
ETL_SCRIPT:\
subprocess package is used ;first the connection to host_postgres is verified using wait_for_postgres function and then the db config is set \
and dump command is executed \
DBT:\
dbt is an open source software used to transform data on top of the loaded database which can be used on a variety of sql databases .\
in the root directory of dbt there is a profiles.yaml which is the config info of what database we are connecting to ,I have set the profiles \
to the destination_db\
we add the custom tables or queries inside the models/dbt_project folder and also update the schema.yaml and source.yaml files which is the schema of the tables\
and we add the dbt image and service in the docker-compose-file with volumes,depends-on,environment .\
macros can be used to replace any long repetitive queries \
Airflow:\
The whole pipeline tasks are orchestrated in apache-airflow  .

