# docker-setup-postgres
Base docker setup for postgres and mysql running on Ruby on Rails


Base set up running on Ruby on Rails with Postgres database.

* Create a folder under the main app name "postgres_db".
  - This will dump all data from local machine under test and development.

  - Include within postgres_db volume(see docker-compose.yml file)
    - ./postgres_db:/var/lib/postgresql
    - ./postgres_db/dumps:/db/dumps
    - ./postgres_db/tmp:/tmp
  
* Create a Postgres container superuser
  - run docker ps and find postgres image_id
  - run command using:
    docker exec -it #{image_id} psql -U postgres -c \ "CREATE USER root SUPERUSER PASSWORD 'password';"
