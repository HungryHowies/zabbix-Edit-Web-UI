# zabbix-Remove-Welcome-pager-Username-and-password-box

Naviaget to this file
```
vi /usr/share/zabbix/include/views/general.login.php
```
Edit these lines 70,8-50 && 73,9-51
```
(new CList())
  ->addItem([
    new CLabel(_('Username'), 'name'),
       //      (new CTextBox('name'))->setAttribute('autofocus', 'autofocus'), <--- Comment out this line
        $error
     ])
   ->addItem([new CLabel(_('Password'), 'password'), new CPassBox('password')])  <--- Comment out this line
     ->addItem(
       (new CCheckBox('autologin'))
```
