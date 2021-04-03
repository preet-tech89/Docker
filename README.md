# Docker Commands

#commands

## create docker network

docker network create mongo-network

# start mongo db
docker run -d \
-p 27017:27017 \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=password \
--name mongodb \
--net mongo-network \
mongo

#start mongo-express
docker run -d \
-p 8081:8081 \
-e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
-e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
-e ME_CONFIG_MONGODB_SERVER=mongodb \
--net mongo-network \
--name mongoexpress \
mongo-express  

minikube win 10

minikube start --vm-driver hyperv --hyperv-virtual-switch "Primary Virtual Switch"      
