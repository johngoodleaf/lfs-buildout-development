# REAMDE #

## Installation with Nginx and uWSGI w/SSL ##

1. Make virtualenvs for each catalog
    `virtualenv ENV`
2. In each virtualenv, run `pip -r requirements.txt`
3. In each virtualenv, customize db access if required
4. In each virtualenv, tweak uwsgi.ini file
5. Make `/etc/uwsgi/vassals`
6. Symlink each uwsgi.ini file into `/etc/uwsgi/vassals`
7. Run uwsgi in "emperor mode" `uwsgi --emperor /etc/uwsgi/vassals --uid=django --gid=www-data --daemonize=/tmp/lfs1.log`
8. uwsgi can be restarted in emperor mode by `touch uwsgi.ini`
9. `source bin/activate` to initiate virtualenv
10. `python lfs_project/manage.py syncdb`
11. `createsuperuser`
12. `lfs_init`
13. Restart nginx