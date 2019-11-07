# Clone
Clone repository
<br/>
# hits_nginxbalancer
In `/hits_nginxbalancer/` dirrectory run `docker-compose up -d --scale server=5` <br/>
Edit `/loadbalancer/nginx.conf` <br/>
You will see <br/>
```
    upstream app_servers {

        server hits_nginxbalancer_server_1:5000;
        server hits_nginxbalancer_server_2:5000;
        server hits_nginxbalancer_server_3:5000;
        server hits_nginxbalancer_server_4:5000;
        server hits_nginxbalancer_server_5:5000;

    }
```
Change `hits_nginxbalancer_server_<num>` on names of your containers with server. <br/>
Up servers withou `-d` flag, to check names of servers. <br/>
Find the line
```
Attaching to hits_nginxbalancer_redis_1, hits_nginxbalancer_server_3, hits_nginxbalancer_server_1, hits_nginxbalancer_server_2, hits_nginxbalancer_server_5, hits_nginxbalancer_server_4, hits_nginxbalancer_loadbalancer_1
```
<br/>
Containers with <i>server</i> word is your servers. <br/>
Go to `/hits_nginxbalancer/` dirrectory and run `docker-compose up -d --scale server=num`, <br/>
where num - number of new servers. <br/>
<br/>

# hits_traefik

In `/hits_traefik/` dirrectory run `docker-compose up -d --scale homevork=num`, <br/>
where num - number of servers. <br/>
