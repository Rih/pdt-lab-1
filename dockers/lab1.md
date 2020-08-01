# based https://training.play-with-docker.com/beginner-linux/

git clone https://github.com/dockersamples/linux_tweet_app

# task 1. Executing docker commands
docker container run alpine hostname

docker container ls --all

docker container run --interactive --tty --rm ubuntu bash

ls /
ps aux
cat /etc/issue
exit

cat /etc/issue

docker container run \
--detach \
--name mydb \
-e MYSQL_ROOT_PASSWORD=my-secret-pw \
mysql:latest

docker container ls

docker container logs mydb

docker container top mydb

docker exec -it mydb \
mysql --user=root --password=$MYSQL_ROOT_PASSWORD --version

docker exec -it mydb sh

mysql --user=root --password=$MYSQL_ROOT_PASSWORD --version

exit

# task 2 build website image

 cd ~/linux_tweet_app

 cat Dockerfile

export DOCKERID=rodrihgo

echo $DOCKERID

docker image build --tag $DOCKERID/docker-begginer-linux .

 docker container run \
 --detach \
 --publish 80:80 \
 --name linux_tweet_app \
 $DOCKERID/docker-beginner-linux