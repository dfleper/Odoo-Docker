# Odoo-Docker 
## Sistemas de Gestión Empresarial SSG.

![GitHub repo size](https://img.shields.io/github/repo-size/dfleper/Odoo-Docker?logo=github)
![GitHub last commit](https://img.shields.io/github/last-commit/dfleper/Odoo-Docker?color=blue&label=last-commit&logo=github&logoColor=white)

- Odoo exercise with Docker subject Business Management Systems.
- Ejercicio de Odoo con Docker asignatura Sistemas de Gestión Empresarial, DAM (SSG).

### docker-compose.yml
```
version: '3.1' 
services: 
  web: 
    image: dfleper/odoo:17
    depends_on: 
      - db 
    ports: 
      - "8069:8069" 
    volumes: 
      - odoo-web-data:/var/lib/odoo 
      - odoo-web-config:/etc/odoo 
      - ./extra-addons:/mnt/extra-addons 
  db: 
    image: dfleper/postgres:15
    environment: 
      - POSTGRES_DB=postgres 
      - POSTGRES_PASSWORD=odoo 
      - POSTGRES_USER=odoo 
      - PGDATA=/var/lib/postgresql/data/pgdata 
    ports: 
      - "5433:5432" 
    volumes: 
      - odoo-db-data:/var/lib/postgresql/data/pgdata
volumes: 
  odoo-web-data: 
  odoo-db-data: 
  odoo-web-config:
```
### Step 1/Paso 1
```
git clone https://github.com/dfleper/Odoo-Docker
cd Odoo-Docker
```
### Step2/Paso2
```
docker-compose up
``` 
#### 🛠 [Visual Studio Code](https://code.visualstudio.com/)
#### 🛠 [Docker](https://hub.docker.com/)
-----
