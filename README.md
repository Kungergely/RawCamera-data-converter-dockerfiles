# RawCamera-data-converter-dockerfiles
Dockerfiles for building the [ov7670 raw camera data to PNG converter](https://github.com/ComputerNerd/RawCamera-data-converter) by [ComputerNerd](https://github.com/ComputerNerd) for both Windows and Linux

Both dockerfiles are based on Ubuntu 16.04 images which should be good for at least 2 more years (till 2021, official 14.04 support was finished a couple days ago i.e. April 2019). All the prerequisites should be automatically taken care of by the dockerfiles themselves, the only thing necessary is a working Docker installation. If it doesn't work this way then something's broken.

To extract the resulting executable, run the following commands in the directory containing the Docker files:
```
docker build --rm -f Dockerfile.linux .    -OR- 
docker build --rm -f Dockerfile.windows .
docker run -it --rm <hash_of_the_image_generated_in_the_previous_step> /bin/bash
docker cp <hash_of_the_running_docker_instance>:/root/converter/RawCamera-data-converter/convert    -OR-
docker cp <hash_of_the_running_docker_instance>:/root/converter/RawCamera-data-converter/convert.exe
```
The executables will have their dependencies (zlib and libpng) statically linked thus they should run fine pretty much on any Linux or Windows system.
