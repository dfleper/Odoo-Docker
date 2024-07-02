# Odoo-Docker

![GitHub repo size](https://img.shields.io/github/repo-size/dfleper/Odoo-Docker?logo=github)
![GitHub last commit](https://img.shields.io/github/last-commit/dfleper/Odoo-Docker?color=blue&label=last-commit&logo=github&logoColor=white)

- Odoo exercise with Docker subject Business Management Systems.
- Ejercicio de Odoo con Docker asignatura Sistemas de Gestión Empresarial, DAM.

### docker-compose.yml
```
version: '3.1'

services:
  db:
    image: dfleper/postgres:15
    environment:
      POSTGRES_DB: odoo
      POSTGRES_USER: odoo
      POSTGRES_PASSWORD: odoo
    volumes:
      - postgres_data:/var/lib/postgresql/data

  odoo:
    image: dfleper/odoo:17
    depends_on:
      - db
    ports:
      - "8069:8069"
    environment:
      HOST: db
      USER: odoo
      PASSWORD: odoo
    volumes:
      - odoo_data:/var/lib/odoo

volumes:
  postgres_data:
  odoo_data:
```
