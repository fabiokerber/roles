# SAMBA

Primeiramente edite o arquivo vars/main.yml alterando para as variáveis conforme seu ambiente.
```
$ vi /etc/ansible/roles/install_samba/vars/main.yml
```

```
$ ansible-playbook /etc/ansible/playbook_default.yml --tags "before_provision"
```

```
$ sudo hostname servidor
```

```
$ sudo /work0/argon-infra/samba4/bin/samba-tool domain provision --use-rfc2307 --server-role=dc --realm=home.domain --domain=home --adminpass=s3nh@001  --option="interfaces=lo eth1" --option="bind interfaces only=yes" --host-name=servidor --host-ip=192.168.0.200 --dns-backend=SAMBA_INTERNAL
```

```
$ ansible-playbook /etc/ansible/playbook_default.yml --tags "after_provision"
```

```
$ ansible-playbook /etc/ansible/playbook_default.yml --tags "test_provision"
```

```
$ sudo kinit administrator (s3nh@001)
```
