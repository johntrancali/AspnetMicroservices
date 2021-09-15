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


Docker commands:
  - docker stop first 4 digits of container id(e.g. docker stop a543)
  - docker rm a543
  - docker images
  - docker-compose -f .\docker-compose.yml -f .\docker-compose.override.yml up -d