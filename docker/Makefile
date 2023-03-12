# This script to manage docker container
 
# Start ALl Container
start: config node1-start node2-start lb-start

#Stop All Container
stop: node2-stop lb-stop node1-stop

config:
	@sudo sysctl -w vm.max_map_count=262144

lb-start:
	@echo "Starting load-balancer"
	@docker-compose -f load-balancer/docker-compose.yaml up -d
	@echo "Load-balancer is up"

lb-stop:
	@echo "Stopping load-balancer"
	@docker-compose -f load-balancer/docker-compose.yaml down
	@echo "Load-balancer is down"

node1-start:
	@echo "Starting node1"
	@echo "Starting docker compose for node1"
	@docker-compose -f node1/docker-compose.yaml up -d 
	@echo "Docker compose for node1 is up"

node2-start: 
	@echo "Starting node2"
	@echo "Starting docker compose for node2"
	@docker-compose -f node2/docker-compose.yaml up -d
	@echo "Docker compose for node2 is up"

node1-stop:
	@echo "Stopping node1"
	@docker-compose -f node1/docker-compose.yaml stop

node2-stop:
	@echo "Stopping node2"
	@docker-compose -f node2/docker-compose.yaml stop

node1-down:
	@echo "Stopping node1"
	@docker-compose -f node1/docker-compose.yaml down

node2-down:
	@echo "Stopping node2"
	@docker-compose -f node2/docker-compose.yaml down

node1-logs:
	@echo "Showing logs for node1"
	@docker-compose -f node1/docker-compose.yaml logs -f

node2-logs:
	@echo "Showing logs for node2"
	@docker-compose -f node2/docker-compose.yaml logs -f

import-news:
	@echo "Importing news"
	@elasticdump --input=news.json --output=http://localhost:1000/news --type=data