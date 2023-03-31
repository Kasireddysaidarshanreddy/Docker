ENV 

ENV is the instruction to provide environment variables to image and container.

FROM almalinux 
ENV AUTHOR="saidarshan"\
    DURATION="25hrs"/
	COURSE="DOCKER"
	
push and pull 


and docker build -t env:v1

docker inspect conatiner id 
or docker run env:v1 env ------> means it gives the inspect the value and give like above content 

example :- docker run env:v1 ping -c 4 google.com  

after v1 what we are entering will run inside the container. means google.com run inside the container. after 4 time ping it will expect the from the container.

There you can over write the file by using this command 
docker run -e DURATION=30hrs env:v1 env 

then it over wirte the file at runitime 
env variables are over write in runtime 
