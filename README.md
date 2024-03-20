# dev-ops

docker container cp Nginx:/etc/nginx/nginx.conf D:\develop\IDEA\workspace\dev-ops\nginx\conf
docker container cp Nginx:/etc/nginx/conf.d/default.conf D:\develop\IDEA\workspace\dev-ops\nginx\conf\conf.d
docker container cp Nginx:/usr/share/nginx/html/index.html D:\develop\IDEA\workspace\dev-ops\nginx\html

docker run \
--name Nginx \
-p 80:80 \
-v D:\develop\IDEA\workspace\dev-ops\nginx\logs:/var/log/nginx \
-v D:\develop\IDEA\workspace\dev-ops\nginx\html:/usr/share/nginx/html \
-v D:\develop\IDEA\workspace\dev-ops\nginx\conf/nginx.conf:/etc/nginx/nginx.conf \
-v D:\develop\IDEA\workspace\dev-ops\nginx\conf/conf.d:/etc/nginx/conf.d \
-v D:\develop\IDEA\workspace\dev-ops\nginx\ssl:/etc/nginx/ssl/  \
--privileged=true -d --restart=always nginx