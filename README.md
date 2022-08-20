Grawlix is a content management system (CMS) for webcomics.

REQUIREMENTS
---

To install Grawlix, you will need a web host with support for:
- MySQL
- PHP 7.0+

A version of Grawlix for PHP 5.x is also available, see the `php5-compatible` branch.

HOW TO INSTALL
---

1. Download the Grawlix files.
   * To download the files most easily, click the big "Code" button near the top of the Github repository, and select "Download ZIP" from the dropdown menu.
2. Create a MySQL database on your site's host, or elsewhere that you can connect to. Note down the database host, name, username, and password.
3. With an FTP client\*, check your site folder and make sure it is empty. Some files, such as .htaccess, might be hidden by default. On your FTP client, make sure you have it set to show hidden files under View, Settings, or Preferences.
4. Open the Grawlix version folder. This folder contains the subfolders \_admin, \_system, etc. Drag all of the contents of the Grawlix version folder into your main site folder.
   * Among these contents is a file called "htaccess.txt". Change the name of this one to ".htaccess".
6. Once you load up the new Grawlix install, it should redirect you to /firstrun. Enter your database credentials, and your user credentials.
7. Grawlix should guide you from there!

If your new Grawlix site is giving you internal server errors, there's a line in `.htaccess` that you may need to uncomment, specifically:
``RewriteBase /``
Again, you may need to 'Show Hidden Files' in order to see the `.htaccess` file.

\*FTP CLIENTS: Some hosts provide a web FTP client, but some free ones you can download include [Cyberduck](https://cyberduck.io/) and [Filezilla](https://filezilla-project.org/).

UPDATING AN EXISTING INSTALL
---

If you're upgrading an existing install of Grawlix, you should be able to just overwrite the files. However, keep the following in mind:
- From the root directory, the only files you should replace are `functions.inc.php` and `index.php`. The others contain configuration specific to your site, keep them! Do replace the files in the subdirectories though.
- You can skip the `themes` subdirectory if you don't care to use the updated default themes.
- If your existing comic has any Disqus comments, you may want to compare `assets/snippets/snippet.comments.php` with your existing one, and possibly comment out line that sets `disqus_identifier`. If you have no existing comments, then overwrite this file.
- If you modified the default themes instead of making new ones, don't overwrite those or you'll lose your changes.
- If you're upgrading from Grawlix 1.2 or older, make sure you follow the additional steps in `upgradeupgrade-readme.html`.
