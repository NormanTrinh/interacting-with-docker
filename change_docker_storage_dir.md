Source: https://www.ibm.com/docs/en/cloud-private/3.1.1?topic=pyci-specifying-default-docker-storage-directory-by-using-bind-mount
## 1. Remove all Docker containers and images.
```
sudo docker rm -f $(docker ps -aq); docker rmi -f $(docker images -q)
```

## 2. Stop the Docker service.
```
sudo systemctl stop docker
```

## 3. Remove the default Docker storage directory.
```
sudo rm -rf /var/lib/docker
```

## 4. Create a new storage directory.
For example, to store images and containers in /home/$USER/docker:
```
sudo mkdir /home/$USER/docker
```

## 5. Add `data-root` parameter in `/etc/docker/daemon.json`
For example, to set the new location as `/home/$USER/docker` run the following commands:
```
sudo gedit /etc/docker/daemon.json
```
Add the following line, **Note**: replace `<Type your user name here>` by your user name
```
"data-root": "/home/<Type your user name here>/docker"
```

## 6. Start the Docker service.
```
sudo systemctl start docker
```
