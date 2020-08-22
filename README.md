# PREPARAÇÃO CTOS6

Procedimentos para preparação do servidor ctos6 padrão Argon
```
https://docs.google.com/document/d/1Vj1eJ_CNfUmg0x0S1VVOMuIsCKhhuEEaKa0D2iTD8dk/edit?usp=sharing
```

# DRBD

Procedimentos para execução da role "install_drbd_argon"
```
https://docs.google.com/document/d/1tMDTspzCY90T9j8xhTouoe4o_GYPkoyzegJR8Le28gA/edit?usp=sharing
```

# SAMBA

Procedimentos para execução da role "install_samba"
```
https://docs.google.com/document/d/1bAkU1XvA6FUsUAup1vgPwKZadxNaFg-XxEXnQI3C0D8/edit?usp=sharing
```
### Pendências
|Ansible      |Descrição|
|-------------|-----------|
|`install_samba_argon`| Remover mkdir / inserir local_samba, local_documentos, local_imagens, local_sistema em vars/main.yml / remover crontab / remover etc/hosts

