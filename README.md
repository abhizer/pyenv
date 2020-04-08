Frist, download and install Docker Desktop in your computer. Once, you are done with that, you can follow the steps here to create a development environment!
## Setting up the Docker

First pull the docker image:
`docker pull alpine`

Verify that it as been downloaded:
`docker images`

Now run it:
`docker run -it alpine`

Then, list all docker containers:
`docker container ls -a`
Note the first 3 letters of your alpine linux docker container. Mine is, 743.

You can stop or stop the docker using the following commands on your host machine:

Starting the container:
`docker container start 743`

Stopping the container:
`docker container stop 743`

Attaching the STDIO to a docker container:
`docker container attach 743`

You can also copy files from your host machine to the container:

Copying from host to docker:
`docker cp Python 743:/`

Now, I don't like running those long comands to start and attach the docker, so I create an alias for it:

Because I am using zsh, I'll add the configuration the zshrc file, if you're on Windows you should do it in the profile file. 

`vi ~/.zshrc`

Go to the end:
```
pyenv(){
        docker container start 743 && docker container attach 743
}
```
Now, you probably know how to save and exit `vim`. :P

Source the file so that the changes take place:
`. ~/.zshrc`

To run start the docker now:
`pyenv`

Now, you should be in your container! 

### Updating alpine linux

In the docker:

`apk update`
`apk upgrade`


### Adding python

`apk add python3 py-pip nmap nmap-scripts`

`pip install --upgrade pip`
`pip3 install --upgrade pip`

### Adding python modules:
`pip3 install bs4 Mechanize requests python3-nmap`
