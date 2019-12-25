``` 
git init
git add .
git commit -m "first commit"
git remote add origin https://github.com/fzhygithub/docker_build_java.git
git push -u origin master


FROM tomcat:8.5.29-jre8

COPY . /root/
CMD  mv m2 .m2 &&  mvn clean package
WORKDIR /root/

### run ###
EXPOSE 8080
CMD ["catalina.sh", "run"]


#docker build -t hellojava .
#docker run -d --name hellojava -p 8080:8080 hellojava
#http://localhost:8080/docker-demo/
```
