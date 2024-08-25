Move to the downloaded repository 
'''
cd ~/GitHub/vector-wire-pod
'''
Create Docker image named vector-wire-pod
'''
docker build --rm -t vector-wire-pod ./ 
'''
Start a new Docker container running this image
'''
  docker run --rm -it \
    --name vector-wire-pod \
    --volume $local_workdir:$container_workdir \
    --workdir $container_workdir \
    --publish $local_port:$container_port \
    $image_tag