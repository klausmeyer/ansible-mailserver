# Mailserver Ansible Playbook

Installs a Mailserver with:

* Postfix for SMTP
* Dovecot for IMAP
* MySQL for User Management
* Rspamd for Spam detection

Inspired by a [DigitalOcean Guide][digitalocean-guide]

## Development

```
$ vagrant up
$ vagrant provision
```

[digitalocean-guide]: https://www.digitalocean.com/community/tutorials/how-to-configure-a-mail-server-using-postfix-dovecot-mysql-and-spamassassin
