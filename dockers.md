Build your image
```
docker build -f your/Dockerfile -t your_name_tag .
```
Run your image with local directory mounted into container
```
docker run -d -it --name your_container name --gpus all -P -v /your/local/dir/:/docker_dir/ image_name 
## -d for detach, -it for iteractive, -P to open ports for ssh login
```
Execute certain commands in your container
```
docker exec -d -w /your/work/dir/ container_id your_command
```
