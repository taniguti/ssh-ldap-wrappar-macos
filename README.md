# ssh-ldap-wrappar-macos
AuthorizedKeysCommand script for sshd on macOS and other helper tools.

You can store ssh-user's ssh public key in your OpenLDAP DB.
Bind your macOS computers to your OpenLDAP Directory Service. 
Then edit sshd_config as following and restart sshd on macOS computer.

    AuthorizedKeysCommand /usr/local/bin/ssh-ldap-wrappar-macos
    AuthorizedKeysCommandUser _sshd

Install two scripts 'ssh-ldap-wrappar-macos' and 'mkhome' under '/usr/local/bin'.

Edit sudoers file with visudo. Add a line as following.

    _sshd ALL=(ALL) NOPASSWD: /usr/local/bin/mkhome