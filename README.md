# MLflow Server with PostgreSQL and MinIO using Docker Compose

This repository provides a setup to deploy an MLflow server with PostgreSQL and MinIO using Docker Compose.

## Setup Instructions

1. **Create a `.env` file**  
   Create a `.env` file in the root directory with the following content:

   ```env
   # Postgres configuration
   PG_USER=mlflow
   PG_PASSWORD=mlflow
   PG_DATABASE=mlflow
   PG_PORT=5432

   # MLflow configuration
   MLFLOW_PORT=5000
   MLFLOW_BUCKET_NAME=mlflow

   # MinIO access keys - these are needed by MLflow
   MINIO_ACCESS_KEY=gBBMM4pecy0UgVOX2Ff4
   MINIO_SECRET_ACCESS_KEY=QzvaQpV9mNSWAJH51Znmz5EiBOXS9BpC5lInXhTX

   # MinIO configuration
   MINIO_ROOT_USER: 'minio_user'
   MINIO_ROOT_PASSWORD: 'minio_pwd'
   MINIO_ADDRESS: ':9000'
   MINIO_STORAGE_USE_HTTPS: False
   MINIO_CONSOLE_ADDRESS: ':9001'
   MINIO_PORT=9000
   MINIO_CONSOLE_PORT=9001
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
Use the MinIO console at **http://localhost:9001** to manage your S3-compatible storage. Create new **ACCESS_KEY** and **SECRET_ACCESS_KEY** and change **MINIO_ACCESS_KEY** and **MINIO_SECRET_ACCESS_KEY** in `.env`

Access the MLflow UI at **http://localhost:5000**

## Notes
Ensure Docker and Docker Compose are installed on your system.

Replace the values in the .env file with your own credentials for production use.

For more details, refer to the MLflow documentation.