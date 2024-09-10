## Project Modules
This project contains the following modules:
- Contacts
- Companies
- Leads
- Accounts
- Invoices (todo)
- Cases (todo)
- Opportunity (todo)

## Installation Guide

### Docker / docker-compose

Clone the project code from github to C:\Django-CRM\ folder.
Download docker from https://www.docker.com/products/docker-desktop/ 
Make sure your docker desktop application running.

To use docker, please run the next commands after cloning repo:
```
docker build -t djcrm:1 -f docker/Dockerfile .
docker-compose -f docker/docker-compose.yml up
```

In case of errors during the creation or initialization of a Docker image (docker build, docker-compose), it is recommended to delete existing Docker containers, images, and volumes, restart the PC, and then recreate and reinitialize the image.

Additionally, when working with the project in the chosen Python environment, installing all required components for proper code display and recognition in VSCode is recommended.
```
pip install -r .\requirements.txt
```

**Note**: Check this link to be sure it is working properly http://localhost:8000/swagger-ui/
### next steps
```
docker exec -it crm-app /bin/bash
cd ../app
python3 manage.py startapp
python3 manage.py makemigrations
python3 manage.py migrate

```
- Then open http://localhost:8000/swagger/ in your browser to explore API.

## Generating schemas file for swagger documentation
To generate schema automatically you should avoid the 'response' parameter in your views @extend_schema. In case of using docker automatical schema generation should be running with ran docker container:
```
docker exec -it crm-app /bin/bash
python3 manage.py spectacular --file schema.yaml
```

### Useful tools and packages
```
pipdeptree # to see pip dependency tree
black # to format code to meet Python coding standards
pip-check -H  # to see upgradable packages
isort # to sort imports in Python
```
