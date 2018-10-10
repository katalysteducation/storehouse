# Pi-stacja website instalation on the local machine
Instructions how to install Pi-stacja test website on the local machine.

## Requirements

1. WWW server (Apache, nginx, XAMPP e.t.c.)
2. PHP 7.0 or higher
3. MySQL 5.6 or higher

## Additionally
Tt is good to have but it is not necessary.

1. Separate domain/subdomain for instalation.
2. Separate database.

## Steps

1. Download and unpack (to the main directory for the website) installation script zip file (http://pistacja.kylos.net.pl/pistacja_test2/kickstart-core-5.4.0.zip).
2. Download (to the main directory for the website) dump file (http://pistacja.kylos.net.pl/pistacja_test2/site-pistacja.kylos.net.pl-20181010-110147utc.jpa).
3. Run `kickstart.php` in the browser. Video tutorial to the installation process: https://www.akeebabackup.com/videos/1212-akeeba-backup-core/1618-abtc04-restore-site-new-server.html
4. In the command line:
  4.1. `cd <main-directory-for-the-website>`
  4.2. `php cli/finder_indexer.php`
