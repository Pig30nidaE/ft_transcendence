RM = rm -rf
COMPOSE_FILE = docker-compose.yml

all:
	@docker compose -f $(COMPOSE_FILE) build
	@docker-compose run app django-admin startproject project .

up:
	@docker compose -f $(COMPOSE_FILE) up -d

down:
	@docker compose -f $(COMPOSE_FILE) down

logs:
	@docker compose -f $(COMPOSE_FILE) logs

clean:
	@make down
	@docker system prune -f --all

fclean:
	@make down
	@volumes=$(shell docker volume ls -q); \
	if [ -z "$$volumes" ]; then \
	    echo "No volumes to remove."; \
	else \
	    docker volume rm $$volumes; \
	fi
	@make clean

re:
	@make fclean
	@make all

.PHONY: all clean fclean re up down