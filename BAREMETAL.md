
Create certificates

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout localhost.key -out localhost.crt

cp localhost.crt /etc/ssl/certs/localhost.crt

cp localhost.key /etc/ssl/private/localhost.key

------

Configure nginx

apt-get update && apt-get install nginx

1) create heygen file with nginx config

cd /etc/nginx/sites-available
cat >heygen (copy template from repo)

2) create symlink

cd /etc/nginx/sites-enabled
ln -s /etc/nginx/sites-available/heygen heygen

3) test and reload nginx

nginx -t
nginx -s reload

------

Copy the html file which contains the avatar

cd /var/www/heygen/html

cat >heygen.html  (copy from repo)


------

Configure hosts on client machine

cd C:\Windows\System32\drivers\etc

add an entry in hosts file using same name as in nginx

192.168.0.213   heygen

------

open an browser in client machine

https://heygen/heygen.html

<allow microphone>








