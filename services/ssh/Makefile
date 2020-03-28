all:
	mkdir -p src/resources
	cp ${HOME}/.ssh/id_rsa.pub src/resources/authorized_keys
	docker build --tag ssh:latest .
clean:
	docker image rm -f ssh:latest
