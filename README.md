
CONTENTS OF THIS FILE
---------------------

 * About Drupal
 * Configuration and features
 * Installation profiles
 * Appearance
 * Developing for Drupal

ABOUT DRUPAL
------------

Drupal is an open source content management platform supporting a variety of
websites ranging from personal weblogs to large community-driven websites. For
more information, see the Drupal website at http://drupal.org/, and join the
Drupal community at http://drupal.org/community.

Legal information about Drupal:
 * Know your rights when using Drupal:
   See LICENSE.txt in the same directory as this document.
 * Learn about the Drupal trademark and logo policy:
   http://drupal.com/trademark

CONFIGURATION AND FEATURES
--------------------------
#### Exporting the Database
1- In phpMyAdmin, select your database from the sidebar list, then select the Export tab.

2- In this menu we'll change the Export Method to Custom.

3- In the Format section verify that SQL is selected.

4- In Tables verify that all tables are selected for export.

5- In the Output section, select Save output to a file and choose zipped for the compression type. Avoid the gzipped compression because it gets corrupted easily. You can leave the Format-specific options in their default state.

6- Under Object creation options make sure every option is selected except the IF NOT EXISTS box in the create table options. Finally, the Data creation options can be left as default. Click Go to export your database.


#### Import the Database Dump
1- Open phpMyAdmin and click on the "Import" tab.

2- Leave all the default settings and make sure the character set is "utf-8" to match the collation selection we made when we created the database: "utf8_general_ci".

3- Now click on the "Choose File" button next to "Browse your computer" and select the .sql.zip file we included in our sites/db-backup folder. It's okay to leave it zipped.

4- Then click the "Go" button on the bottom left.

#### Create the Database User
we must recreate the database username/password that Drupal uses to store things in the database. We do this the same way we did when we created the database.

1- After importing the .sql.zip file, select the "Privileges" tab and click on "Add User".
2- Use the same username and password from before. (If we have forgotten what that was, we can always find that information in settings.php, or in the PDO Exception error message we saw displayed in the browser.)

After importing the database, if you have any trouble logging in with your Site Maintenance account, clear your browser's cookies by clearing the browser history.

#### Built-In Users and Databases
When continuing work on a project, you may want to delete previous users and databases from phpmyadmin. Keep in mind you should never delete SQL's built-in users and databases. This includes the information_schema, mysql, and performance_schema databases, and the root user.

Deleting any of these will cause errors that are tricky to fix.


#### server
http://localhost:8888/

INSTALLATION PROFILES
---------------------

Installation profiles define additional steps (such as enabling modules,
defining content types, etc.) that run after the base installation provided
by core when Drupal is first installed. There are two basic installation
profiles provided with Drupal core.

Installation profiles from the Drupal community modify the installation process
to provide a website for a specific use case, such as a CMS for media
publishers, a web-based project tracking tool, or a full-fledged CRM for
non-profit organizations raising money and accepting donations. They can be
distributed as bare installation profiles or as "distributions". Distributions
include Drupal core, the installation profile, and all other required
extensions, such as contributed and custom modules, themes, and third-party
libraries. Bare installation profiles require you to download Drupal Core and
the required extensions separately; place the downloaded profile in the
/profiles directory before you start the installation process. Note that the
contents of this directory may be overwritten during updates of Drupal core;
it is advised to keep code backups or use a version control system.

Additionally, modules and themes may be placed inside subdirectories in a
specific installation profile such as profiles/your_site_profile/modules and
profiles/your_site_profile/themes respectively to restrict their usage to only
sites that were installed with that specific profile.

More about installation profiles and distributions:
 * Read about the difference between installation profiles and distributions:
   http://drupal.org/node/1089736
 * Download contributed installation profiles and distributions:
   http://drupal.org/project/distributions
 * Develop your own installation profile or distribution:
   http://drupal.org/developing/distributions

APPEARANCE
----------

In Drupal, the appearance of your site is set by the theme (themes are
extensions that set fonts, colors, and layout). Drupal core comes with several
themes. More themes are available for download, and you can also create your own
custom theme.

More about themes:
 * Download contributed themes to sites/all/themes to modify Drupal's
   appearance:
   http://drupal.org/project/themes
 * Develop your own theme:
   http://drupal.org/documentation/theme

DEVELOPING FOR DRUPAL
---------------------

Drupal contains an extensive API that allows you to add to and modify the
functionality of your site. The API consists of "hooks", which allow modules to
react to system events and customize Drupal's behavior, and functions that
standardize common operations such as database queries and form generation. The
flexible hook architecture means that you should never need to directly modify
the files that come with Drupal core to achieve the functionality you want;
instead, functionality modifications take the form of modules.

When you need new functionality for your Drupal site, search for existing
contributed modules. If you find a module that matches except for a bug or an
additional needed feature, change the module and contribute your improvements
back to the project in the form of a "patch". Create new custom modules only
when nothing existing comes close to what you need.

More about developing:
 * Search for existing contributed modules:
   http://drupal.org/project/modules
 * Contribute a patch:
   http://drupal.org/patch/submit
 * Develop your own module:
   http://drupal.org/developing/modules
 * Follow best practices:
   http://drupal.org/best-practices
 * Refer to the API documentation:
   http://api.drupal.org/api/drupal/7
