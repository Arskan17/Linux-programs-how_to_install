It summarizes the steps on this website [pgadmin.org](https://www.pgadmin.org/docs/pgadmin4/latest/container_deployment.html)

#
## 1. Download Docker images for Postgres and PgAdmin4
Run these in a terminal (`tag name` is optional).

```python
docker pull postgres:<tag name>
```

```python
docker pull dpage/pgadmin4:<tag name>
```
`<tag name>` can be one of the following
![image](https://github.com/Arskan17/Linux-programs-how_to_install/assets/75216911/0f53983a-922e-4148-a774-a8590fe04e5f)

#
## Startup in Docker
#### 2. Setup Docker network (if not already done)
```python
docker network create --driver bridge mynetwork
```
you can rename `mynetwork` to whatever you want

#### 3. Run the PostgreSQL container:
```python
docker run --name some-postgres --network=mynetwork -e POSTGRES_PASSWORD=postgres -e POSTGRES_USER=postgres -e POSTGRES_DB=example-DB -v pgdata:/var/lib/postgresql/data -d postgres
```

#### 4. Run the pgAdmin4 container:
Specify the ports. In our case, it connects port 6688 to the docker's port 80
```python
docker run -p 6688:80 --name some-postgres-pgAdmin4 --network=mynetwork \
    -e 'PGADMIN_DEFAULT_EMAIL=user@domain.com' \
    -e 'PGADMIN_DEFAULT_PASSWORD=SuperSecret' \
    -d dpage/pgadmin4
```

#### 5. Connect to pgAdmin4 in browser
Open http://localhost:6688 in the browser and login with your email and password  
in our case, `user@domain.com` and `SuperSecret`

![image](https://github.com/Arskan17/Linux-programs-how_to_install/assets/75216911/5a040c9a-9019-4ff5-aa48-95481babc897)

#### Optional
#### 6. Or connect to the server directly from the terminal
```python
docker exec -it 68e4218d6673 psql -U postgres example-DB
```
replace `68e4218d6673` by the container's Id  
see here...  
![image](https://github.com/Arskan17/Linux-programs-how_to_install/assets/75216911/5f7f5e89-fdb2-4f75-b58d-6e91ee06f07b)



