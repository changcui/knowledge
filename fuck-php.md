### [How to invoke php in html file?](https://stackoverflow.com/questions/20637944/how-to-call-a-php-file-from-html-or-javascript)

Firstly, you should write a html file named foo as below.

```php+HTML
<a href="my.php">run php</a>
```

Secondly, you shold write a php file named my as below.

`<?php echo “hello world” ?>`

Finally, open foo.html with your browser and try to click the link “run php”, if “hello world” not displayed, you should refer to linux-tricks to tackle the problem.