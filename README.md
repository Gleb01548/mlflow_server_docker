# MLflow Server with PostgreSQL and MinIO using Docker Compose

This repository provides a setup to deploy an MLflow server with PostgreSQL and MinIO using Docker Compose.

## Setup Instructions

1. **Create a `.env` file**  
   Create a `.env` file in the root directory with the following content:

   ```env
   # PostgreSQL
   POSTGRES_USER=user
   POSTGRES_PASSWORD=password
   POSTGRES_DB=mlflowdb

   # MinIO
   MINIO_ROOT_USER=minio_user
   MINIO_ROOT_PASSWORD=minio_password

   # MLflow
   MLFLOW_S3_ENDPOINT_URL=http://localhost:9000
   AWS_ACCESS_KEY_ID=minio_user
   AWS_SECRET_ACCESS_KEY=minio_password
   ARTIFACTS_DESTINATION=s3://bucket
   ```

2. **Build the Docker containers**
Run the following command to build the Docker containers:
```bash 
docker compose build
``` 

3. **Start the services**
Use the following command to start the services in detached mode:
```bash 
docker compose up -d
```

## What's Next?
Access the MLflow UI at **http://localhost:5000**.

Use the MinIO console at **http://localhost:9001** to manage your S3-compatible storage.

## Notes
Ensure Docker and Docker Compose are installed on your system.

Replace the values in the .env file with your own credentials for production use.

For more details, refer to the MLflow documentation.