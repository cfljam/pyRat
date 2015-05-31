# pyRat

## Docker Container for Jupyter notebooks with R kernel

- R install based on rocker https://github.com/rocker-org/rocker
- R kernel for Jupyter provided by https://github.com/IRkernel/IRkernel

### To Build Docker Container

- install docker-machine (assuming here that host is Virtualbox)
- clone the repo
```
git clone https://github.com/cfljam/pyRat
cd pyRat
```
- build the image
```docker build -t cfljam/pyrat .
```
- run the container, sharing default Virtualbox shared directory mapping /Users
```
docker run -rm -p 8888:8888 -v /Users/:/Users -it cfljam/pyrat:dev
```
