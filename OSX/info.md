These are examples of how to configre this to function on an OS X .7 or .8 Server.
It uses the webappctl control, but can also be used with the server app.

this project was forked in order for the sub-path of /macnamer (eg http://your.server.com/macnamer)
and that is represented in the included httpd_macnamer.conf file with the WSGIScriptAlias line

	WSGIScriptAlias /macnamer /usr/local/www/macnamer_env/macnamer/macnamer.wsgi


the other primary change in this fork was to allow for multiple django-wsgi apps to be run side-by side hence the renaming of /static/ directive in the settings.py file to /static_macnamer/.  With that set you can Alias more than one set of static files things properly.

		Alias /static_macnamer/ /usr/local/www/macnamer_env/macnamer/static_macnamer/

