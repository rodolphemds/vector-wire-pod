# vector-wire-pod

Fully-featured server for the Anki (now Digital Dream Labs) Vector robot allowing voice control, remote control, and robot management. This project is a fork of [wire-pod](https://github.com/kercre123/wire-pod/).

## Requirements

Remote server has to have the following installed:

- [Docker](https:://www.docker.com) for running a full-time containerized development environment. You have to login on your computer to be able to pull Docker images from Docker Hub. You can do this by running the following command:

  ```
   docker login --username <username>
  ```

## Installation

The installation guide exists on the wiki: [Installation guide](https://github.com/kercre123/wire-pod/wiki/Installation)

### Note for Docker :

- Clone [vector-wire-pod](https://github.com/rodolphemds/vector-wire-pod.git) repository inside ~/GitHub
```shell
git clone https://github.com/rodolphemds/vector-wire-pod.git
```
- Move to the cloned repository 
```shell
cd ~/GitHub/vector-wire-pod
```
- Create Docker image named vector-wire-pod
```shell
docker build --rm -t vector-wire-pod ./ 
```

- Start a new Docker container running this image
```shell
docker run -i -t \
  --hostname escapepod \
  --name vector-wire-pod \
  --restart unless-stopped \
  --publish 443:443 \
  --publish 8080:8080 \
  --publish 80:80 \
  --publish 8084:8084 \
  --volume wire-pod-data:/chipper/ \
  --volume wire-pod-model:/vosk/ \
vector-wire-pod
```

## Usage

Check out the [wiki](https://github.com/kercre123/wire-pod/wiki) for more information on what wire-pod is, a guide on how to install wire-pod, troubleshooting, how to develop for it, and for some generally helpful tips.

## Project structure

Quick overview of project structure, components and their roles.

```
├── 📁chipper                                # Scripts for voice back-end that drives conversations with the robot
├── 📁vector-cloud                           # Programs that make Vector talk to the cloud
├── 📄.gitignore
├── 📁.github                                
├── 📄Dockerfile                             # Instructions to build development Docker image.
├── 📄setup.sh                               # Initial set-up script for installing wire-pod
├── 📄update.sh                              # Wire-pod update script
├── 📖LICENSE
├── 📖README.md
```

## Credits
- [kercre123](https://github.com/kercre123/wire-pod/) for creating wire-pod
- [Digital Dream Labs](https://github.com/digital-dream-labs) for open sourcing chipper and creating escape pod (which made this possible)
- [bliteknight](https://github.com/bliteknight) for making wire-pod more accessible with his easy-to-use pre-setup Linux boxes
- [dietb](https://github.com/dietb) for rewriting chipper and giving tips
- [fforchino](https://github.com/fforchino) for adding many features such as localization and multilanguage, and for helping out
- [xanathon](https://github.com/xanathon) for the publicity and web interface help
- Anyone who has opened an issue and/or created a pull request for wire-pod