ENTRYPOINT 

ENTRYPOINT is also used to run the container just like CMD.
but there are few differences 

1. we cant overide entrypoint, but we can override cmd.
2. we cant overide ENTRYPOINT , if you try to do so it will go and append to the ENTRYPOINT command.

FROM almalinux 
CMD ["google.com"]
ENTRYPOINT ["ping , "-c5"]

There you have ping -c5 it will not ping but if you run docker file the google.com -- cmd will give append to the entry point.

google ping -c5 --- it will ping 5 times 

3.If you use CMD and ENTRYPOINT and dont give any command from terminal, CMD acts as argument provider to entrypoint.
  you can see in docker ps command 
  
  
4.If you dnt provide any entry point from run then it will provide by CMD.


5. CMD will supply default arguments to ENTRYPOINT 
6. You can always override CMD argument by runtime 

7. you can stop misuing your image other commands 

Difference between CMD and ENTRYPOINT

CMD can be override but ENTRYPOINT can be override.

Its is clear you can over ride the CMD Command 
but you cant over ride entrypoint 


-----------------

Dockerfile 

FROM almalinux
CMD ["ping", "-c5", "google.com"]

Cd dockerfie 
git pull 

docker build -t entry:v1 .
docker run entry:v1 
There it will ping 5 times google.com 

BUT we use direct command 

docker run entry:v1 ping -c2 facebook.com
it will ping 2 times 

if you see docker ps -a 
then you can see command has 
ping -c2 facebook.com
ping -c5 google.com

so there if you dnt give any thing it will take by the google.com 
but if you give in command facebook.com then till will ping facbook.com 

1. docker build -t entry:v1 .-- it takes from the docker file 
2. docker run entry:v1 ping -c2 facebook.com

It is clear that you can over write cmd 