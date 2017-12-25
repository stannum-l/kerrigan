NAME    := k8s-keystone-auth
DFLAGS  := -v -d --tmpfs=/run --tmpfs=/run/lock -p 8443:8443

.PHONY: default pre build bash run rmc rmi clean cleanall

default: pre

pre:
	@git clone https://github.com/dims/k8s-keystone-auth.git $(NAME)
	mkdir -p assets
	make -C $(NAME) && make -C (NAME) build
	cp -f $(NAME)/bin/* assets
	rm -rf $(NAME)

build:
	@docker build -t $(NAME) .

bash:
	@docker run -it $(NAME) /bin/bash

run:
	@docker run -t $(DFLAGS) --name $(NAME) $(NAME)

rmc:
	@docker stop $(NAME)
	@docker rm $(NAME)

rmi:
	@docker stop $(NAME)

clean: rmc

cleanall: clean rmi
	rm -rf assets
