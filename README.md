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

  $ pip install -r requirements.txt


Teste da playbook com o Molecula
--------------

No arquivo molecule.yml, tem as configurações da VM do VirtualBox que o Molecula ira provisionar para o teste:


Para iniciar os testes, dentro do diretório execute para criar o ambiente de teste:

```bash
 $ molecula converge
```

Para destruir o ambiente de testes, execute:

```bash
 $ molecula destroy
```

Executando playbook
------------

Depois dos testes terem sido executados com sucesso, configure o seu arquivo de hosts, e execute a usa playbook!!!

