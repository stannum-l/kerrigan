NAME := diablo

.PHONY: build clean push pull

default: clean

build:
	@docker build -t $(NAME) .

clean:
	@echo "Removing image $(NAME)"
	@docker rmi $(NAME)

push:
	@echo "Pushing image $(NAME)"

pull:
	@echo "Pulling image $(NAME)"
