# Apache virtual hosts on OSX
Instructions for how to setup virtual hosts on OSX

1. Start the apache server with `$ sudo apachectl start`.
2. Edit the host file with `$ sudo nano /private/etc/hosts`.
 * Add to the bottom of the bottom of the file the following code (if the desired domain is `localhost`):

     ```
     127.0.0.1       localhost
     ```
 * Save by typing in `^X`, then `Y`, then `return`.

3. If the directory `/Library/WebServer/Documents/` does not exist
 * Create directory `/Library/WebServer/Documents/`
 * Put the file `index.html` into the directory `/Library/WebServer/Documents/`. This file might looks like below

     ```
     <html>
      <body>
        <h1>It works!</h1>
      </body>
    </html>
     ```

4. Edit the virtual host file so that you are directing to your desired domain. Pull up the editor with this command `$ sudo nano /etc/apache2/extra/httpd-vhosts.conf`.
 * If the desired domain is `localhost`, edit the config file so that it looks the same as below.
 * Save by typing in `^X`, then `Y`, then `return`.

     ```
     <VirtualHost *:80>
       ServerAdmin webmaster@wlocalhost
       DocumentRoot "/Library/WebServer/Documents/"
       ServerName localhost
       ServerAlias www.localhost
     </VirtualHost>
     ```

5. Edit the config file: `$ sudo nano /etc/apache2/httpd.conf`
 * Type `^W` to search and type in `virtual hosts`.
 * Remove the `#` that comments out the following line: `# Include /private/etc/apache2/extra/httpd-vhosts.conf`
 * Save by typing in `^X`, then `Y`, then `return`.

6. Restart the server with `$ sudo apachectl restart`.
7. Visit `localhost` in your browser to check if virtual host is running.

### NOTE:

1. You can set up any virtual host (e.g., `demo`, `test.dev`, etc.) in a same way.
2. You cannot use `_` in the domain name and also this sign should not be in the directory name.

# Apache virtual hosts on Windows (XAMPP)
Instructions for how to setup virtual hosts on Windows with [XAMPP](https://www.apachefriends.org/pl/index.html)

> TO DO...
