monitorning-stack-ansible
=========

Essa stack proviona o ambiente de monitoramento com o Prometheus, Node Exporter, Cadvisior e Grafana com o Ansible.

Requisitos
------------

python >= 2.7

ansible >= 2.8

molecule >= 2.0

molecule-vagrant >= 0.5.2

Para a instalação dos pacotes acima execute:


```bash
$ pip install -r requirements.txt
```

Teste da playbook com o Molecula
--------------

No arquivo molecule.yml, tem as configurações da VM do VirtualBox que o Molecula ira provisionar para o teste.

Exemplo:

```yml
driver:
  name: vagrant

platforms:
  - name: homologacao
    box: bento/debian-10
    memory: 1024
    cpus: 1
```

Para iniciar os testes, dentro do diretório execute para criar o ambiente de teste:

```bash
 $ molecula converge
```

Para destruir o ambiente de testes, execute:

```bash
 $ molecula destroy

```

Inventário
-------------

arquivo hosts_prom:

```bash
[monitorning]
SEU_IP

[monitorning:vars]
ansible_ssh_user=SEU_USER
ansible_ssh_private_key_file=/to/path/key.pem
```


Executando playbook
------------

Depois dos testes terem sido executados com sucesso, configure o seu arquivo de hosts, e execute a sua playbook!!!

```bash
 $ ansible-playbook monitorning-stack-ansible monitorning.yml
```