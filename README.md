# docker-superset
Superset with clickhouse support Docker image


# notes on getting this running


docker pull crobox/superset 

    #I'm pulling the copy of superset that has been built for use with clickhouse to test it out

    #I run the image

docker run --name superset -d -p 8088:8088 crobox/superset 

    #once the docker is running, lets reset the admin password so we can connect to it when it asks for a user/pw

sudo docker exec -i -t superset /bin/bash

    #once you are on the docker image's commandline, you'll want to run the initialisation program
    #which you do by pasting in this command and hitting return:
    
/usr/local/bin/.bin/superset-init

    #you will see it prompts you for the admin username, first name, surname, email, and password.
    #use the admin/password you set up to access the console when you get the superset login page

    #once you have configured the admin details, it spools a bunch of logs and completes. 
    #exit
    
    #visit http://<dockerHostIP>:8088
    
    #you should now be able to see the main superset UI, and click sources to attache a clickhouse db
