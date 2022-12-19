[Русский](https://github.com/shoei1944/listing/) | English
# Beautiful listing for nginx and apache

![preview](http://img.sho20.ru/listing.png) 

# Installing on NGINX

1. Download folder ```.html``` for nginx
2. Put the ```.html``` folder in the root directory of the site
3. Paste the code in ```location```
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

# Installing on apache
1. Downpload ```tpl``` folder
2. Put the ```tpl``` folder in the root directory of the site
3. Paste the code in ```.htaccess```
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

 
