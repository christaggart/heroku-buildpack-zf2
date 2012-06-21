ZF2 build pack
========================

This is a build pack bundling PHP and Apache for Heroku apps. It allows the deployment of [ZendFramework 2](http://framework.zend.com/zf2) applications
on Heroku.

It supports the installation of any dependancies through the use of Composer. It will even download the composer.phar if it
is not present in the project.

Detection is done by looking for a index.php file in the public directory.

Example Usage
-------------
This is an example of creating a new ZF2 application of heroku using heroku-buildpack-zf2:  
`heroku apps:create zf2skeleton -s cedar -b https://github.com/jaconel/heroku-buildpack-zf2.git`

`git push heroku master`

Example of the output received from Heroku:
```
Counting objects: 1150, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (470/470), done.
Writing objects: 100% (1150/1150), 275.49 KiB | 12 KiB/s, done.
Total 1150 (delta 490), reused 1140 (delta 487)

-----> Heroku receiving push
-----> Fetching custom buildpack... done
-----> PHP app detected
-----> Bundling Apache version 2.2.22
-----> Bundling PHP version 5.3.10
-----> Updating Composer
-----> Installing Composer Dependencies
-----> Discovering process types
       Procfile declares types -> (none)
       Default types for PHP   -> web
-----> Compiled slug size is 86.7MB
-----> Launching... done, v4
       http://zf2skeleton.herokuapp.com deployed to Heroku

To git@heroku.com:zf2skeleton.git
 * [new branch]      master -> master

```

A current application is installed at http://zf2skeleton.herokuapp.com.

Configuration
-------------

The config files are bundled with the LP itself:

* conf/httpd.conf
* conf/php.ini
