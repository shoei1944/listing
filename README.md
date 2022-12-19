# Красивый листинг для NGINX и apache

# Установка на NGINX

1. Загрузить .html для nginx 
2. Положить папку .html в главную директорию сайта
2. Вставить код в location
```
autoindex on;
autoindex_localtime on;
autoindex_exact_size off;
sub_filter '<html>' '';
sub_filter '<head><title>Index of $uri</title></head>' '';
sub_filter '<body>' '';
sub_filter '<h1>Index of $uri</h1><hr>' '';
sub_filter '<hr></body>' '';
sub_filter '</html>' '';
sub_filter_once on;
add_before_body /.html/header.html;
add_after_body /.html/footer.html;
```
