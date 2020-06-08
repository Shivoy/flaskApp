Dockerfile

FROM python:latest 
COPY . /app
WORKDIR /app
RUN pip3 install -r requirements.txt 
EXPOSE 5001 
CMD [ "python3","hello.py" ] 

-----####----####----####----####----
requirements.txt

click==7.1.2
Flask==1.1.2
itsdangerous==1.1.0
Jinja2==2.11.2
MarkupSafe==1.1.1
Werkzeug==1.0.1

-----####----####----####----####----
run flask app locally->
	python3 fileName.py
create docker image->
	docker build --tag dockerreponame .
	{reponame cannot have UpperCase letters}
run docker image->
	sudo docker run --name dockerreponame -p 5001:5001 dockerreponame
list docker active containers->
	docker ps --all
kill all docker active container->
	docker rm $(docker ps -a -q)
