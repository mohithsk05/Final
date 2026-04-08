11.


12.
mvn archetype:generate
write code
mvn package
mvn clean test
make changes and again mvn clean test

14.
same steps as 12 till mvn package
in pom below build
<plugins>
      <plugin>
        <groupId>org.jacoco</groupId>
        <artifactId>jacoco-maven-plugin</artifactId>
        <version>0.8.11</version>
        <executions>
          <execution>
            <goals>
              <goal>prepare-agent</goal>
            </goals>
          </execution>
          <execution>
            <id>report</id>
            <phase>test</phase>
            <goals>
              <goal>report</goal>
            </goals>
          </execution>
        </executions>
      </plugin>
    </plugins>
mvn clean test

15.
docker --version
docker ps
docker ps -a
docker images
docker run hello-world
docker pull nginx
docker run -d -p 8080:80 nginx
docker stop 'id'
docker rm 'id'

17.
docker run -d nginx
docker run -d -p 8088:80 nginx
volume create vol
docker run -it -v vol:/data ubuntu bash
cd /data
echo "hello world" > f1.txt
exit
docker run -it -v vol:/data ubuntu bash
cat /data/f1.txt
exit
docker run -d -p 8089:80 -v vol:/usr/share/nginx/html nginx
docker run -it -v vol:/data ubuntu bash
echo "<h1> good </h1>" > /data/index.html
exit
