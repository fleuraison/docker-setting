all: install up
.PHONY: all

up:
	docker-compose up -d
.PHONY: up

install:

.PHONY: install

migrate:
	  docker-compose run rasp-web73 bin/cake migrations migrate
.PHONY: migrate

test:
	  docker-compose run rasp-web73 ./vendor/bin/phpunit
.PHONY: test

clean:
	  docker-compose down
.PHONY: clean

web73:
	winpty docker exec -it rasp_web73 sh
.PHONY: web73

nginx:
	winpty docker exec -it rasp_nginx sh
.PHONE: nginx
