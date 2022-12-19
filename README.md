# Красивый листинг для NGINX и apache

# Установка на NGINX

1. Загрузить .html для nginx 
2. Положить папку .html в кореневую директорию сайта
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

# Установка на apache
1. Загрузить папку tpl
2. Положить папку tpl в кореневую директорию сайта
3. Вставить код в .htaccess
```
Options +Indexes
IndexOptions Charset=UTF-8 FancyIndexing FoldersFirst HTMLTable IconsAreLinks IgnoreCase SuppressRules VersionSort SuppressHTMLPreamble SuppressDescription SuppressColumnSorting
IndexIgnore tpl
HeaderName /tpl/header.html
ReadmeName /tpl/readme.html

AddIcon /tpl/icons/folder.svg ^^DIRECTORY^^
AddIcon /tpl/icons/folder-home.svg ..
AddIcon /tpl/icons/zip.svg .zip
AddIcon /tpl/icons/java.svg .jar
AddIcon /tpl/icons/json.svg .json
AddIcon /tpl/icons/file-text.svg .cfg .txt
DefaultIcon /tpl/icons/file.svg
```

