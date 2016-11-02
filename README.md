# Password Complexity Checker for GoSA
Sean Caron scaron@umich.edu

This is a simple password complexity check script for GoSA.

To install, edit /etc/gosa/gosa.conf and add a plugin in the pathMenu section, like below:

```
  <!-- These entries will be rendered on the path navigator -->
  <pathMenu>
      <plugin acl="users/netatalk:self,users/environment:self,users/posixAccount:self,users/kolabAccount:self,users/phpscheduleitAccount:self,users/oxchangeAccount:self,users/proxyAccount:sel
f,users/connectivity:self,users/pureftpdAccount:self,users/phpgwAccount:self,users/opengwAccount:self,users/pptpAccount:self,users/intranetAccount:self, users/webdavAccount:self,users/nagiosA
ccount:self,users/sambaAccount:self,users/mailAccount:self,users/groupware, users/user:self,users/scalixAccount:self,users/gofaxAccount:self,users/phoneAccount:self,users/Groupware:self" clas
s="MyAccount" />
      <plugin acl="users/password:self" class="password" check="/usr/share/gosa/scripts/chkpwcomplexity" />
  </pathMenu>
```

Copy the script to /usr/share/gosa/scripts and ensure it is set to mode 775.

If desired, the file /usr/share/gosa/plugins/personal/password/password.tpl may be edited
to contain text describing the password complexity policy, in addition to the password
strength meter provided by GoSA.

