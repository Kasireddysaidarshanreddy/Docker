USER 

it is use to run the commands as particular user 

FROM almalinux
RUN touch /temp/hello.txt



There you can use user to instration for specific role only 

FROM almalinux
RUN adduser nginx
USER nginx 
RUN touch /tmp/hello.txt 

there you can pull and after 
docker build -t user:v1 .
docker run -it user:v1

You can see  $ symbol over there search with id you know all groups 
there user is nginx user. means you dnt have root access 
ls -l 


it is usful for security perpose 