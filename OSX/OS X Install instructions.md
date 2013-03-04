*please see the README.md at the root of this project for more general instructions*

#OS X Setup#

These are examples of how to configre this to function on an OS X Mountian Lion Server (it should also work for Lion)
It uses the webappctl control, but can also be used with the server app.

this project was forked with the intention of running on sub-path of /macnamer (eg http://your.server.com/macnamer)
and that is represented in the included httpd_macnamer.conf file with the WSGIScriptAlias line

	WSGIScriptAlias /macnamer */path/to/your/*macnamer_env/macnamer/macnamer.wsgi


the other primary change in this fork was to allow for multiple django-wsgi apps to be run side-by side hence the renaming of /static/ directive in the settings.py file to /static_macnamer/.  With that set you can Alias more than one set of static files properly.

	Alias /static_macnamer/ */path/to/your/*macnamer_env/macnamer/static_macnamer/

####To install (on 10.8 )####
Edit macnamer.wsgi specifiying your virtualenv directory and place in 

	*/path/to/your/*macnamer_env/macnamer/

Now edit the httpd_macnamer.conf specifying the location of where you just placed the macnamer.wsgi file, and place that file in

	/Library/Server/Web/Config/apache2/

and finally edit the the com.aapps.macnamer.plist specifying the location of where you placed macnamer.wsgi, and place that file in

	/Library/Server/Web/Config/apache2/webapps/

