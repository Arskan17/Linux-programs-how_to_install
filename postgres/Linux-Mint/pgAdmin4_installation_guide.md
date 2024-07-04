It summarizes the steps on this website [pgadmin.org](https://www.pgadmin.org/docs/pgadmin4/latest/container_deployment.html)

## Setup the repo

#### Install the public key for the repository (if not done previously):
```python
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg
```

#### Create the repository configuration file:
```python
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
```

## Install pgAdmin

#### for some reason unbeknowns to me, this won't work:
```python
sudo apt install pgadmin4
```
#### See Terminal output...

![image](https://github.com/Arskan17/Linux-programs-how_to_install/assets/75216911/0498cb73-46f3-4f13-bbeb-d0a7b81c02b3)



#
#### some guy on the [linuxmint-forum](https://forums.linuxmint.com/viewtopic.php?t=393497) told to donload these [packages](https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/jammy/dists/pgadmin4/main/binary-amd64/) and install one after the other.
download the latest ones of course

![image](https://github.com/Arskan17/Linux-programs-how_to_install/assets/75216911/909566c0-91f2-4e86-9ec8-c9ad74f581d7)



