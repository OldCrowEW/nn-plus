# nn-plus
This repo will contain my progress as I get [newznab+](http://www.newznab.com/) working properly.

Currently this will install on centos7. When playbook completes it will screen newznab_screen_job.sh, updating as new groups are added. Here is a [dump](http://pastebin.com/raw/FNsi3zb4) which can be added under {{ site_url }}/admin/group-bulk.php.

Now the gotchas:

* set a hostname before running. localhost will cause mysql play to fail.

* turn on the firewall before running. firewalld disabled will cause firewall add to fail.

* No default accounts are created. Go here ( and no further) {{ site_url }}/install/step6.php? to create your account. You will be redirected to {{ site_url }}/install but just go to step6.php again and you'll be g2g. Do not use any of the other steps or the {{ newznab_dir_www }}/config.php will be overwritten. You **MUST** delete {{ newznab_dir_www }}/install when completed or **anyone will be able to create admin accounts**.

* All the menu pages on the site refer to localhost. This should be fixed.


You must set the following variables under roles/defaults/main.yml

* newznab_svn_user: 
* newznab_svn_passwd: 
* newznab_id:
* mysql_root_passwd:
* nntp_username:
* nntp_password:
* nntp_server:
* nntp_port:
* nntp_sslenabled: