# Docker help

To install docker, it changes based on your OS, you can find instructions here: https://www.docker.com/

On debian or ubuntu, just run

```
sudo apt install  docker.io
```

To launch an image,you just need to pull it:

```
sudo docker pull postgres:latest
```

and then run it:

```
sudo docker run -e POSTGRES_USER=user -e POSTGRES_PASSWORD=password -e POSTGRES_DB=db -p 5432:5432 postgres:latest
```

You can change the username and password in the command above for more security.
