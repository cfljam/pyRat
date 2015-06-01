# pyRat

## Docker Container for Jupyter notebooks with R kernel

- R install based on rocker https://github.com/rocker-org/rocker
- R kernel for Jupyter provided by https://github.com/IRkernel/IRkernel

### To Build Docker Image

- this example uses Virtualbox as host
- install docker-machine https://docs.docker.com/machine/#getting-started-with-docker-machine-using-a-local-vm
- clone the repo from Github
```
git clone https://github.com/cfljam/pyRat
cd pyRat
```
- build the image
```
docker build -t cfljam/pyrat .
```

### To run the image
- run the container, sharing default Virtualbox shared directory mapping /Users
```
docker run -rm -p 8888:8888 -v /Users/:/Users -it cfljam/pyrat:dev
```
- point your browser to localhost:8888 
- ensure that  

