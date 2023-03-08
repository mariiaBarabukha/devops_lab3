### Simple Nodejs app with Docker

### How to dockerize the app?<br/>

#### 1. Create an image
```
docker build <app dir> -t <docker hub username>/<image name>[:<tag>]
```
Flag <i>-t</i> is used to set a name of the image<br/>
<i>[:tag]</i> in the name is optional, <i>:latest</i> will be applied by default.<br/>
If you are not planning to push your image to Docker Hub, you can drop <i>\<docker hub username\></i> in the name<br/><br/>

#### 2. Run container
```
docker run --name <container name> -p <destination port>:<original port> --memory=<value> --cpus=<value> [-d] <docker hub username>/<image name>[:tag]
```
We use flags <i>--memory</i> and <i>--cpu</i> to limit memory and cpu usage respectively.<br/>
Flag <i>-d</i> is also optional and it will run image on background. <br/><br/>

#### 3. Monitor activity
```
docker logs -f <container name>
```
<br/>

#### 4. Push image to Docker Hub

##### Login
```
docker login -u <docker hub username> -p <password> docker.io
```
##### Push
```
docker push <docker hub username>/<image name>[:tag]
```
