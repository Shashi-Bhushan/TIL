# Creating docker image from container

You could create a contains from image using 
```bash
docker run -d -it -p 8080:80 ubuntu
```

Then, the container will be started. Note that host port 8080 has been mapped with container port 80. 
Now, if we make few changes inside container. 

```bash
docker attach <container-id>
>> apt update
>> apt dist-upgrade
>> apt install vim
>> apt install apache2
>> /etc/init.d/apache2 start

<CTRL-P-Q>
```

Now, we need to persist these changes in an image. 
```bash
docker commit --change='ENTRYPOINT ["apachectl", "-DFOREGROUND"]' <container-id> custom/ubuntu-custom:1.0
```

entrypoint specifies to run apachectl, otherwise there won't be apache running on port 8080 here. 

Now, stop the existing container running on port 8080 and start a new container from this image. 
```bash
docker stop <container-id>
docker run -it -d -p 8080:80 custom/ubuntu-custom:1.0
```

