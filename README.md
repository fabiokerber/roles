# SAMBA

Primeiramente edite o arquivo vars/main.yml alterando para as variáveis conforme seu ambiente.
```
$ vi /etc/ansible/roles/install_samba/vars/main.yml
```


Execute o comando abaixo com a tag "before_provision". Serão executadas somente as tasks para preparação do servidor antes de realizar o provisionamento do SAMBA.
```
$ ansible-playbook /etc/ansible/playbook_default.yml --tags "before_provision"
```


Caso o hostname do servidor atual for diferente de "servidor", execute o comando abaixo.
```
$ sudo hostname servidor
```


Agora execute o comando abaixo alterando por exemplo o nome do dominio ou IP do servidor.
Lembre-se que estas opções devem estar equivalentes ao que foi alterado em vars/main.yml anteriormente.
```
$ sudo /work0/argon-infra/samba4/bin/samba-tool domain provision --use-rfc2307 --server-role=dc --realm=home.domain --domain=home --adminpass=s3nh@001  --option="interfaces=lo eth1" --option="bind interfaces only=yes" --host-name=servidor --host-ip=192.168.0.200 --dns-backend=SAMBA_INTERNAL
```


Após o provisionamento execute o comando abaixo para finalizar a pós configuração do serviço SAMBA.
```
$ ansible-playbook /etc/ansible/playbook_default.yml --tags "after_provision"
```


A execução do comando abaixo realiza os testes no domínio provisionado e exibe os resultados em tela.
```
$ ansible-playbook /etc/ansible/playbook_default.yml --tags "test_provision"
```


Por úlimo acesse o servidor e configure a senha do usuario "administrator" do domínio recém criado.
```
$ sudo kinit administrator (s3nh@001)
```
