# This script to manage docker container
 
# Up ALl Container
up: config node1-up node2-up lb-up

#Down All Container
down: node2-down lb-down node1-down

# Start ALl Container
start:lb-start node1-start node2-start 

#Stop All Container
stop: node2-stop lb-stop node1-stop

config:
	@sudo sysctl -w vm.max_map_count=262144

# Load Balancer Up
lb-up:
	@echo "Starting load-balancer"
	@docker-compose -f load-balancer/docker-compose.yaml up -d
	@echo "Load-balancer is up"

# Load Balancer Down
lb-down:
	@echo "Stopping load-balancer"
	@docker-compose -f load-balancer/docker-compose.yaml down
	@echo "Load-balancer is down"

# Load Balancer Start
lb-start: 
	@echo "Starting load-balancer"
	@docker-compose -f load-balancer/docker-compose.yaml start
	@echo "Load-balancer is up"

# Load Balancer Stop
lb-stop:
	@echo "Stopping load-balancer"
	@docker-compose -f load-balancer/docker-compose.yaml stop
	@echo "Load-balancer is down"

# Elasticsearch Node1 Up
node1-up:
	@echo "Starting node1"
	@echo "Starting docker compose for node1"
	@docker-compose -f node1/docker-compose.yaml up -d 
	@echo "Docker compose for node1 is up"

# Elasticsearch Node2 Up
node2-up: 
	@echo "Starting node2"
	@echo "Starting docker compose for node2"
	@docker-compose -f node2/docker-compose.yaml up -d
	@echo "Docker compose for node2 is up"

# Elasticsearch Node1 Down
node1-down:
	@echo "Stopping node1"
	@docker-compose -f node1/docker-compose.yaml down
	@echo "Docker compose for node1 is down"

# Elasticsearch Node2 Down
node2-down:
	@echo "Stopping node2"
	@docker-compose -f node2/docker-compose.yaml down
	@echo "Docker compose for node2 is down"

# Elasticsearch Node1 Start
node1-start:
	@echo "Starting node1"
	@docker-compose -f node1/docker-compose.yaml start
	@echo "Docker compose for node1 is up"

# Elasticsearch Node2 Start
node2-start:
	@echo "Starting node2"
	@docker-compose -f node2/docker-compose.yaml start
	@echo "Docker compose for node2 is up"

# Elasticsearch Node1 Stop
node1-stop:
	@echo "Stopping node1"
	@docker-compose -f node1/docker-compose.yaml stop
	@echo "Docker compose for node1 is down"

# Elasticsearch Node2 Stop
node2-stop:
	@echo "Stopping node2"
	@docker-compose -f node2/docker-compose.yaml stop
	@echo "Docker compose for node2 is down"


node1-logs:
	@echo "Showing logs for node1"
	@docker-compose -f node1/docker-compose.yaml logs -f

node2-logs:
	@echo "Showing logs for node2"
	@docker-compose -f node2/docker-compose.yaml logs -f

import-news:
	@echo "Importing news"
	@elasticdump --input=news.json --output=http://localhost:1000/news --type=data