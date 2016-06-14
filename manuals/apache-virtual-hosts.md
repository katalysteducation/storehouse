# Apache virtual hosts on OSX
Instructions for how to setup virtual hosts on OSX

1. Start the apache server with `$ sudo apachectl start`.
2. Edit the host file with `sudo nano /private/etc/hosts`.
 * Add to the bottom of the bottom of the file the following code (if the desired domain is `webview.dev`):
   
     ```
     127.0.0.1       www.webview.dev
     127.0.0.1       webview.dev
     ```
     
3. Edit the virtual host file so that you are directing to your desired domain. Pull up the editor with this command `$ sudo nano /etc/apache2/extra/httpd-vhosts.conf`.
 * If the desired domain is `webview.dev`, edit the config file so that it looks the same as below. Furthermore, make sure to put the installed `webview` folder into the directory `/Library/WebServer/Documents/`.
 * Save by typing in `^X`, then `Y`, then `return`.

     ```
     <VirtualHost *:80>
       ServerAdmin webmaster@webview.dev
       DocumentRoot "/Library/WebServer/Documents/webview/dist/"
       ServerName webview.dev
       ServerAlias www.webview.dev
     </VirtualHost>
     <VirtualHost *:80>
       ServerAdmin webmaster@localhost.com
       DocumentRoot "/Library/WebServer/Documents/"
       ServerName localhost.com
       ServerAlias www.localhost.com
     </VirtualHost>
     ```

4. Edit the config file: `$ sudo nano /etc/apache2/httpd.conf`
 * Type `^W` to search and type in `virtual hosts`.
 * Remove the `#` that comments out the following line: `# Include /private/etc/apache2/extra/httpd-vhosts.conf`
 * Save by typing in `^X`, then `Y`, then `return`.
5. Restart the server: `$ sudo apachectl restart`
6. Visit `webview.dev` in your browser to check if virtual host is running.

# Apache virtual hosts on Windows (XAMPP)
Instructions for how to setup virtual hosts on Windows with [XAMPP](https://www.apachefriends.org/pl/index.html)

> TO DO...
