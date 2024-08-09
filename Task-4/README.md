# Devops Task 4

## Description

This document outlines the steps to set up a web server using Nginx and PHP 7.3. The setup includes configuring a
virtual host, handling PHP files, serving static content, and ensuring proper gzip compression for static files.

## Steps

1. **Update the package list:**
    - Run the following command to update the package list:
      ```bash
      sudo apt update
      ```
2. **Install Nginx:**
    - Run the following command to install Nginx:
      ```bash
      sudo apt install nginx
      ```
3. **Start Nginx:**
    - Run the following command to start the Nginx service:
      ```bash
      sudo systemctl start nginx
      ```
4. **Enable Nginx:**
    - Run the following command to enable the Nginx service to start on boot:
      ```bash
      sudo systemctl enable nginx
      ```
5. **Install PHP 7.3:**
    - Run the following command to install PHP 7.3 and the necessary PHP extensions:
      ```bash
      sudo apt install php7.3-fpm php7.3-mysql
      ```
6. **Create a Virtual Host on Nginx**
    - Configure Nginx to create a virtual host for the domain ```mobadra.com```. The virtual host configuration should
      point to the directory ```/var/www/html```
    - ```bash
     sudo nano /etc/hosts
     ```
    - Add the following line to the file:
      ```127.0.0.1       mobadra.com```

7. **Create info.php File**
    - Create a new file named `info.php` in the `/var/www/html` directory.
    - Add the following content to the file:
      ```php
      <?php
      phpinfo();
      ?>
      ```
8. **Configure Nginx to Handle PHP Files**
    - Make a new Nginx configuration file located at `/etc/nginx/conf.d`.
      - Run the following command to create the file:
        ```bash
        sudo nano /etc/nginx/conf.d/mobadra.conf
        ```
      - Add the following configuration to the file to handle PHP files:
        ```nginx
          server {
              listen 80;
              server_name mobadra.com;
              root /var/www/mobadra.com/html;
              index index.php index.html index.htm;
              location / {
                  try_files $uri $uri/ =404;
              }
              location ~ \.php$ {
                  include snippets/fastcgi-php.conf;
                  fastcgi_pass unix:/var/run/php/php7.3-fpm.sock;
              }
          }
        ```
9. **Add Static Folder**
    - Create a new folder named `static` in the `/var/www/html` directory.
    - Add some static files (e.g., images, CSS, JavaScript) to the `static` folder.
10. **Create Static Location in Nginx**
    - Run the following command to edit the Nginx configuration file:
      ```bash
      sudo nano /etc/nginx/conf.d/mobadra.conf
      ```
    - Add the following configuration to the file to serve static content:
      ```nginx
      location /static {
            alias /var/www/html/static;
      }
      ```
    - Enable Gzip Compression
      ```nginx
      gzip on;
      gzip_types image/png image/gif image/jpeg image/jpg text/plain text/css application/json application/javascript text/xml application/xml application/xml+rss text/javascript image/svg+xml application/vnd.ms-fontobject application/x-font-ttf font/opentype font/ttf font/eot font/otf image/vnd.microsoft.icon ;
      ```
12. **Test the Nginx Configuration**
    - Run the following command to test the Nginx configuration:
      ```bash
      sudo nginx -t
      ```
13. **Reload Nginx**
    - Run the following command to reload the Nginx service:
      ```bash
      sudo systemctl reload nginx
      ```
14. **Access Your Website**
    - Open a web browser and enter `http://mobadra.com/info.php` in the address bar.
    - You should see the PHP info page.
    - Open a web browser and enter `http://mobadra.com/static/image.jpg` in the address bar.
    - You should see the static image served by Nginx.