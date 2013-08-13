php-pecl-hidef
======

NONE THREAD SAFE (MAYBE...)

The original hidef extension is thread safe.

But I don't know to write a TS one.
So don't use this with apache...


diffrent with original one
======
you can define ini_path, data_path in php-fpm pool configure file.

>eg.
> 
> /etc/php-fpm.d/www.conf
>
> [www]
>
> ..............
> 
> php_admin_value[hidef.ini_path] = /home/project1/constant
>

This will over-written ini_path defined in php.ini


others:
* Will read and parse both ini-spec-path(fpm main) and fpm-spec-path(cgi child). (can never know if fpm-spec exists)
* Must parse again when every child start (but seems very fast...).
* 
