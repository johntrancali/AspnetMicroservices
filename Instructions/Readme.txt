https://github.com/aspnetrun/run-aspnetcore-microservices

Install Mongo Database
- Open terminal from VS
- type: docker pull mongo
- type: docker run -d -p 27017:27017 --name shopping-mongo mongo
- List all running images, type: docker ps
- type: docker logs -f shopping-mongo
- To run mongo, type: docker exec -it shopping-mongo /bin/bash

Mongo
- type: mongo
- type: show dbs
- type: use CatalogDb
- type: db.createCollection('Products')
- type: db.Products.insertMany(
[
  {
    "Name": "Asus Laptop",
	"Category": "Computers",
	"Summary": "Summary",
	"Description": "Description",
	"ImageFile": "ImageFile",
	"Price": 54.93
  },
  {
    "Name": "HP Laptop",
	"Category": "Computers",
	"Summary": "Summary",
	"Description": "Description",
	"ImageFile": "ImageFile",
	"Price": 88.93
  },
  {
    "Name": "Dell Laptop",
	"Category": "Computers",
	"Summary": "Summary",
	"Description": "Description",
	"ImageFile": "ImageFile",
	"Price": 100.93
  }
])

- type: db.Products.find({}).pretty()
- To remove db, type: db.Products.remove({})


Install Mongo GUI
  - docker run -d -p 3000:3000 mongoclient/mongoclient 


Docker commands:
  - docker stop first 4 digits of container id(e.g. docker stop a543)
  - docker ps
  - docker ps -a
  - docker rm a543
  - docker images
  - docker-compose -f .\docker-compose.yml -f .\docker-compose.override.yml up -d
  - When there are changes to microservice, use
      - docker-compose -f .\docker-compose.yml -f .\docker-compose.override.yml up --build
  - docker-compose -f .\docker-compose.yml -f .\docker-compose.override.yml down
  - docker ps -aq
  - docker stop $(docker ps -aq)
  - docker rm $(docker ps -aq)
  - docker rmi $(docker images -q)
  - docker volume rm $(docker volume ls -q)
  - docker system prune
  
 
Install Redis
  - docker pull redis
  - docker images
  - docker run -d -p 6379:6379 --name aspnetrun-redis redis
  - docker logs -f aspnetrun-redis
  - docker exec -it aspnetrun-redis /bin/bash
  
Redis CLI Commands
  - redis-cli
  - ping
  - set key value
  - get key
  - set name john
  - get name
  

Portainer
  - Login Portainer with info below
    - Username: admin
    - Password: Pass@123456789
  - Select Docker then click Connect


Install PostgreSQL
  - docker pull postgres 
  

Add Db Migration
  - Set Ordering.API as Startup project
  - Make sure Microsoft.EntityFrameworkCore.Tools is installed in Ordering.API
  - Set Ordering.Infrastructure as Default project in Package Manager Console
  - Type: add-migration InitialCreate


RabbitMQ
  - username: guest
  - password: guest
    
IdentityServer
  - https://localhost:5020/.well-known/openid-configuration