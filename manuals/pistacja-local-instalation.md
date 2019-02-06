# Pi-stacja website instalation on the local machine

Instructions how to install Pi-stacja test website on the local machine.

## Requirements

1. WWW server (Apache, nginx, XAMPP e.t.c.)
2. PHP 7.0 or higher
3. MySQL 5.6 or higher

## Additionally
It is good to have but it is not necessary.

1. Separate domain/subdomain for installation.
2. Separate database.

## Steps

1. Download and unpack (to the main directory for the website) installation script zip file (http://pistacja.kylos.net.pl/pistacja_test/kickstart-core-5.4.0.zip).
2. Download (to the main directory for the website) dump file (http://pistacja.kylos.net.pl/pistacja_test/site-pistacja.kylos.net.pl-20190206-141053utc.jpa).
3. Run `kickstart.php` in the browser. Video tutorial to the installation process: https://www.akeebabackup.com/videos/1212-akeeba-backup-core/1618-abtc04-restore-site-new-server.html
  **Important:** You need to uncheck option "Replace main .htaccess file with default".
4. In the command line:
  * `cd <main-directory-for-the-website>`
  * `php cli/finder_indexer.php`
