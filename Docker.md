# Docker
Source: https://www.youtube.com/watch?v=_jKNnHROiC0&t=910s


## Table of Contents
* [Part 1](#part-1)
* [Part 2](#part-2)
* [Part 3](#part-3)


<a id="part-1"></a>
## Part 1
* Get image from docker hub:

```bash
docker pull <image_name>
```

* Run image:

```bash
docker run <image_name>
```
> **Note:** If the image is not available locally, it will be downloaded from docker hub.  

We can give commands to the image by adding them at the end of the `docker run` command:

```bash
docker run <image_name> <command>
```
For example:

```bash
docker run busybox echo "Hi there!"
```

* Show all images:

```bash
docker images
```

* Show all running containers:

```bash
docker ps
```

> **Note:** To show all containers, including the ones that are not running, use `docker ps -a`.  

> **Note:** `ps` stands for `process status`.

* Remove container:

```bash
docker rm <container_id>
```

* Remove image:

```bash
docker rmi <image_id>
```
> **Note:** To remove an image, all containers that are using that image must be removed first otherwise we will get an error.


* Image vs Container:
  * Image is the application we want to run.
  * Container is an instance of that image running as a process.
  * We can have many containers running off the same image.  
  
<br>  

* Remove all stopped containers:  

```bash
docker container prune
```

* See Help of a command:
```bash
docker <command> --help
```
or
```bash
docker help <command>
```

* Run image & remove container after exit:
```bash
docker run --rm <image_name>
```

* Run image & get shell access:
```bash
docker run -it <image_name>
```

* Run image & connect a container port to a system port:
```bash
docker run -p <system_port>:<container_port> <image_name>
```

* Run a command inside a running container:
```bash
docker exec <container_id> <command>
```

* Run a command inside a running container & get shell access:
```bash
docker exec -it <container_id> <command>
```
example:
```bash
docker exec -it 3b3b3b3b3b3b vi /etc/nginx/nginx.conf
```
or
```bash
docker exec -it 3b3b3b3b3b3b sh
```


<a id="part-2"></a>
## Part 2

- Run image and give it a favorite name:
```bash
docker run --name <favorite_name> <image_name>
```
then we can use the favorite name instead of the container id for "exec" command:
```bash
docker exec <favorite_name> <command>
```

- Run image and map a directory on the host to a directory inside the container:
```bash
docker run -v <host_dir>:<container_dir> <image_name>
```
> **Note:** '-v' stands for 'volume'.  

> **Note:** This is useful when we want to make changes to the files inside the container and we want to `keep those changes after the container is removed`. We can use this data again when we run another container from the same image.


<a id="part-3"></a>
## Part 3