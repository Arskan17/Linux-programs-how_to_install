It summarizes the steps on this website [pgadmin.org](https://www.pgadmin.org/docs/pgadmin4/latest/container_deployment.html)

#
## Download the docker [image](https://hub.docker.com/r/dpage/pgadmin4/)
Run this in a terminal
```python
docker pull dpage/pgadmin4:<tag name>
```
`<tag name>` can be one of the following
![image](https://github.com/Arskan17/Linux-programs-how_to_install/assets/75216911/0f53983a-922e-4148-a774-a8590fe04e5f)

#
## Startup in Docker
Now you'll need to initialize the `PGADMIN_DEFAULT_EMAIL` and `PGADMIN_DEFAULT_PASSWORD` at startup, so run this.  
chose a port you want
```python
docker run -p 6688:6688 \
    -e 'PGADMIN_DEFAULT_EMAIL=user@domain.com' \
    -e 'PGADMIN_DEFAULT_PASSWORD=SuperSecret' \
    -e POSTGRES_PASSWORD=postgres \
    -e POSTGRES_USER=postgres \
    -e POSTGRES_DB=example-DB \
    -v pgdata:/var/lib/postgresql/data \
    -d dpage/pgadmin4
```
and to connect to the postgres instance run
```python
docker exec -it 6ed9e3c78672 psql -U postgres example-DB
```
replace `6ed9e3c78672` by the container's id  
see here  
![image](https://github.com/Arskan17/Linux-programs-how_to_install/assets/75216911/df491d74-d20b-4fd3-af34-561180b0d61a)


