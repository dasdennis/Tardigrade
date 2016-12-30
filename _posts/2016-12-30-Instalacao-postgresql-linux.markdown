---
layout: post
title: "Instalação do PostgreSQL no Linux Debian"
date:   2016-12-29 16:00 -0300
categories: post
---

Olá pessoa!


Este é um post simples e aborda a instalação básica e direta, no linux (Debian), vamos lá.

Atualize as dependências do sistema operacional:

```
sudo apt update
sudo apt upgrade
```

Preparando a instalação (__execute uma linha por vez__):

```
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt/ $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'

sudo apt install wget ca-certificates

wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
```

Instalando a versão 9.6, altere-a se desejar. O _pgadmin3_ é uma plataforma Open Source de administração e desenvolvimento para PostgreSQL, possui uma interface gráfica para administrar as databases e SQL queries.

```
sudo apt -y update && sudo apt -y install postgresql-9.6 pgadmin3
```

Verificando a instalação:

```
dennis@Jehuty:~$ ps -fu postgres
UID        PID  PPID  C STIME TTY          TIME CMD
postgres 32126     1  0 18:54 ?        00:00:00 /usr/lib/postgresql/9.6/bin/postgres -D /var/lib/postgresql/9.6/main -c config_file=/etc/postgresql/9.6/main/postgresql.conf
postgres 32128 32126  0 18:54 ?        00:00:00 postgres: 9.6/main: checkpointer process
postgres 32129 32126  0 18:54 ?        00:00:00 postgres: 9.6/main: writer process
postgres 32130 32126  0 18:54 ?        00:00:00 postgres: 9.6/main: wal writer process
postgres 32131 32126  0 18:54 ?        00:00:00 postgres: 9.6/main: autovacuum launcher process
postgres 32132 32126  0 18:54 ?        00:00:00 postgres: 9.6/main: stats collector process
```

Para desinstalar e remover completamente o PostgreSQL, rode a instrução abaixo;

```
sudo apt remove --purge postgresql*
```


Até a próxima.
