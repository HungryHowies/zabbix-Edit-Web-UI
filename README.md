# zabbix-Remove-Welcome-pager-Username-and-password-box

Navigate to this file
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

Should look like this
```
(new CList())
                                                ->addItem([
                                                //      new CLabel(_('Username'), 'name'),
                                                //      (new CTextBox('name'))->setAttribute('autofocus', 'autofocus'),
                                                        $error
                                                ])
                                                // ->addItem([new CLabel(_('Password'), 'password'), new CPassBox('password')])
                                                ->addItem(
                                                        (new CCheckBox('autologin'))
                                                                ->setLabel(_('Remember me for 30 days'))
                                                                ->setChecked($data['autologin'])
                                                )
                                                // ->addItem(new CSubmit('enter', _('Sign in')))
                                                ->addItem($guest)
                                                ->addItem($http_login_link)
                                                ->addItem($saml_login_link)
```
