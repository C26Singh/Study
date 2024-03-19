# Docker
## Docker logs commands  
docker logs --tail <number_of_lines> <container_id>  
docker logs --tail 50 ef94ab8b7846  
docker logs -f <container_id>  
docker logs id -f  ----------> streams the logs  
docker inspect--->gives info about container json output   
# Pull MongoDB and MongoDB Express Docker images
docker pull mongo-express
docker pull mongo

# Create a custom Docker network
docker network create mongo-network

# Run MongoDB container (Mac)
docker run -d \
  --name mongodb-container \
  --network mongo-network \
  -e MONGO_INITDB_ROOT_USERNAME=admin \
  -e MONGO_INITDB_ROOT_PASSWORD=secret \
  -p 27017:27017 \
  mongo

# Run MongoDB container (Windows)
docker run -d ^
  --name mongodb-container ^
  --network mongo-network ^
  -e MONGO_INITDB_ROOT_USERNAME=admin ^
  -e MONGO_INITDB_ROOT_PASSWORD=secret ^
  -p 27017:27017 ^
  mongo

# Run MongoDB Express container (Mac)
docker run -d \
  --name mongo-express-container \
  --network mongo-network \
  -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
  -e ME_CONFIG_MONGODB_ADMINPASSWORD=secret \
  -e ME_CONFIG_MONGODB_SERVER=mongodb-container \
  -p 8081:8081 \
  mongo-express

# Run MongoDB Express container (Windows)
docker run -d ^
  --name mongo-express-container ^
  --network mongo-network ^
  -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin ^
  -e ME_CONFIG_MONGODB_ADMINPASSWORD=secret ^
  -e ME_CONFIG_MONGODB_SERVER=mongodb-container ^
  -p 8081:8081 ^
  mongo-express

## Go Template
# Go Template Usage in README.md

### Variables
`{{variable}}`

### Actions
Actions control the template's execution. Example: `{{action}}`

### Pipelines
Pipelines represent a sequence of commands separated by vertical bars `|`. They process data through a series of functions or operations. Example: `{{pipeline}}`

### Control Structures
Go templates support control structures like if, range, and with.

```go
{{if condition}}
    // code
{{else}}
    // code
{{end}}

{{range .Items}}
    // code
{{end}}

{{with .Data}}
    // code
{{end}}

