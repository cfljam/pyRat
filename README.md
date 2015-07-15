# pyRat

## Docker Container for Jupyter notebooks with R kernel and R Cell Magic

- R install using [Littler](http://dirk.eddelbuettel.com/code/littler.html) copied from  rocker https://github.com/rocker-org/rocker
- R kernel for Jupyter provided by https://github.com/IRkernel/IRkernel
- R2Py from http://rpy.sourceforge.net/
-  REVEAL slideshows from @damianavila https://github.com/damianavila/RISE
-  - bash kernel

Example Notebooks
------------------

- [R kernel](https://github.com/cfljam/pyRat/blob/master/Notebooks/Jupyter%20Notebooks%20with%20the%20R%20kernel.ipynb)
- [Python kernel + R2Py R cell magic](https://github.com/cfljam/pyRat/blob/master/Notebooks/Using%20R2Py%20in%20Jupyter%20NOtebooks.ipynb)



-----------------

### To Use

- pull image from Dockerhub and run default

```
docker run --rm -it -p 8888:8888 cfljam/pyrat
```

### To Build Docker Image

- this example uses Virtualbox as host
- install and configure docker-machine https://docs.docker.com/machine/#getting-started-with-docker-machine-using-a-local-vm
- clone the repo from Github



```
git clone https://github.com/cfljam/pyRat
cd pyRat
```
- if you are behind a proxy , insert lines at the head of the dockerfile
```
ENV http_proxy  http://my.proxy.url:my_proxy_port
ENV https_proxy  https://my.proxy.url:my_proxy_port
```
- build the image (you can call it anything you want-but in this case repo name, no other tags)
```
docker build -t cfljam/pyrat .
```

### To run the image
- ensure that there is a port forwarding rule for port 8888 on the virtual host (on Virtualbox in this case) 
![Virtualbox port forward rule](https://dl.dropboxusercontent.com/u/8064851/images/VirtualBoxPortForwardiPynbExample.png)
- run the container, sharing default Virtualbox shared directory mapping /Users
```
docker run --rm -p 8888:8888 -v /Users/:/Users -it cfljam/pyrat
```
- point your browser to localhost:8888 . You should see something like the screen below. Navigate the links to where you want to work and select **new** to create content.
![Jupyter Screen](https://dl.dropboxusercontent.com/u/8064851/images/JupyterScreen%20Shot.png)

