package-autoload
================

Automatically detect .deb packages that appear in a directory and insert them into the local apt repository.

Service descriptions
--------------------

* `autoimport-package.conf` is triggered when a .deb file is created in `/srv/apt/incoming/`. It imports the file into the apt repo, then deletes the file.
* `autoimport-start-listener.conf` starts the file-bridge service on `/srv/apt/incoming/`, which is responisble for emitting inotify events.

Installing
----------

Place both the `.conf` files in `/etc/init/`. Restart the computer, or run `start autoimport-start-listener`