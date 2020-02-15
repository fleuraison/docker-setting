FROM nginx

ADD nginx.conf /etc/nginx/nginx.conf
ADD fastcgi.conf /etc/nginx/fastcgi.conf
ADD server.conf /etc/nginx/conf.d/default.conf
# ADD localhost.key /etc/ssl/private/localhost.key
# ADD localhost.crt /etc/ssl/certs/localhost.crt
ADD localhost.crt.pem /etc/ssl/certs/localhost.crt.pem
ADD localhost.key.pem /etc/ssl/certs/localhost.key.pem

