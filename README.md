Based on Youtube video: [Deploy a .NET API with Docker(Step-by-Step)](https://www.youtube.com/watch?v=f0lMGPB10bM&list=PLsR2Rzhb3qgwZpPKMGv6gUrlZ9A6mJjYH&index=2)
`dotnet new webapi -n DockerAPI` - builds project
`dotnet build`
### Will run it locally
`dotnet run` 
- go to https://localhost:7289/swagger/index.html to see swagger UI
- go to https://localhost:7200/WeatherForecast to see json

- [8:41 - Project set up, moving onto docker](https://youtu.be/f0lMGPB10bM?t=521)
- 17:10 `docker build .` will build docker file, but there is a better way (using tags for naming)
Naming convention: <Docker Hub ID>/<Project Name>:<Version>
`docker build -t corky1/dockerapi .`
- note: if you leave off the version it will make one for you (...:latest)
- note: video has old base image and runtime image I had to update [link](https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/docker/building-net-docker-images?view=aspnetcore-6.0#the-dockerfile)

19:22 - listing images
`docker images`

19:59 - run it as a container
### Will run it in a container
`docker run -p 8080:80 <name of image>` such as `docker run -p 8080:80 corky1/dockerapi`
- note: name of image has to be lowercase

23:00 - uploading onto docker hub
 - need to login first with `docker login`
25:40 - `docker push corky1/dockerapi` to push it to docker hub

28:00 downloading onto linux box

32:00 - Deploying into Azure