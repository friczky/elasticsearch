## This script to manage docker container
 
# Start ALl Container
start: node1 node2

# Restart All Container
restart: node1 node2

#Stop All Container
stop: node1 node2

load-balancer:
	@echo "Starting load-balancer"
	@docker-compose -f load-balancer/docker-compose.yml up -d

node1:
	@echo "Starting node1"
	@docker-compose -f node1/docker-compose.yml up -d 

node2: 
	@echo "Starting node2"
	@docker-compose -f node2/docker-compose.yml up -d

node1-restart:
	@echo "Restarting node1"
	@docker-compose -f node1/docker-compose.yml up -d

node2-restart:
	@echo "Restarting node2"
	@docker-compose -f node2/docker-compose.yml up -d

node1-stop:
	@echo "Stopping node1"
	@docker-compose -f node1/docker-compose.yml down

node2-stop:
	@echo "Stopping node2"
	@docker-compose -f node2/docker-compose.yml down

