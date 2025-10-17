# Bandit

- [Level 0](#Level-0)
- [Level 1](#Level-1)
- [Level 2](#Level-2)
- [Level 3](#Level-3)
- [Level 5](#Level-5)
- [Level 6](#Level-6)
- [Level 7](#Level-7)

---

## Level 0

### Problema: 

Conectar ao host bandit0 utilizando o SSH, com o usuário bandit0 e senha fornecidos.

### Solução:

Conexão do host bandit0 via secure shell (SSH)

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
password: bandit0
```

Comandos utilizados para visualizar o conteúdo do arquivo `readme`:

```bash
ls
cat readme
```

**Senha:** ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

---

## Level 1

### Problema: 

Acessar o conteúdo de um arquivo chamado - . Esse nome é problemático, pois o shell pode interpretar o - como uma opção do comando.

### Solução:

```bash
ls
cat < -
```

ou

```bash
cat ./-
```

**Senha:** 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

---

## Level 2

### Problema: 

Leitura do arquivo --spaces in this filename-- localizado no diretório do bandit2

### Solução: 

 ```bash
ls
```
```bash
cat ./--spaces\ in\ this\ filename--
```
ou 
```bash
cat "./--spaces in this filename--"
```

**Senha:** MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

---

## Level 3

### Problema: 

Encontrar o conteúdo do arquivo escondido no diretório inhere

### Solução: 

```bash
ls
```
```bash
ls -a
```
```bash
cat ...Hiding-From-You
```

**Senha:** 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

---

## Level 4

### Problema: 

A próxima senha está localizada em um arquivo legível a humanos

### Solução: 

```bash
ls
```
```bash
cd inhere
```
```bash
# Visualizar os tipos dos arquivos
file ./-file*
```
```bash
cat ./-file07
```
ou
```bash
cat -- -file07
```

**Senha:** 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

---

## Level 5

### Problema:

Encontrar a senha em algum lugar no diretório inhere com as seguintes caracterísiticas:

 - Legível para o ser humano
 - 1033 bytes de tamanho
 - não executável

**Solução:**

```bash
ls
```
```bash
cd inhere
```
```bash
find -size 1033c
```
```bash
cd maybehere07/
```
```bash
ls -a
```
```bash
cat .file2
```
**Senha:** HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

---

## Level 6

### Problema:

Encontrar a senha em um arquivo no servidor com as seguintes características:

- dono do usuário  bandit7
- dono por grupo bandit6
- 33 bytes de tamanho

**Solução:**

```bash
cd /
```
```bash
find -user bandit7 -group bandit6 -size 33c 2>/dev/null
```
```bash
cat /var/lib/dpkg/info/bandit7.password
```
**Senha:** morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

---

## Level 7

### Problema:

Localizar a senha que está armazenada no arquivo data.txt na linha com o nome millionth

**Solução:**

```bash
ls
```
```bash
# Visualizar o conteúdo do arquivo
cat data.txt
```
```bash
grep millionth data.txt
```



**Senha:** dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

---

## Level 8

### Problema:

A senha para o próximo nível é armazenada no arquivo data.txt e é a única linha de texto que ocorre apenas uma vez

**Solução**

```bash
# Visualizar o conteúdo do arquivo
cat data.txt
```
```bash
# ordenar o arquivo para juntar repedidos e filtrar o conteúdo que não repete
sort data.txt | uniq -u
```

**Senha:** 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

---
## Level 9

### Problema

A senha para o próximo nível é armazenada no arquivo data.txt em uma das poucas cordas legíveis por humanos, precedidas por várias ‘=’ personagens.

**Solução**

```bash
cat data.txt
```
```bash
strings data.txt
```

**Senha:** FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

--- 
## Level 10

### Problema

A senha para o próximo nível é armazenada no arquivo data.txt, que contém dados codificados base64

**Solução**

```bash
base64 -d data.txt
```

**Senha:** dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

---

## Level 11

### Problema

A senha para o próximo nível é armazenada no arquivo data.txt, onde todas as letras minúsculas (a-z) e maiúsculas (A-Z) foram girado por 13 posições

**Solução**
```bash
# Visualizar o conteúdo do arquivo data.txt
cat data.txt
```
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

**Senha:** 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

---

## Level 12

### Problema

A senha para o próximo nível é armazenada no arquivo data.txt, que é um hexdump de um arquivo que tem sido repetidamente comprimido. Para este nível pode ser útil criar um diretório em /tmp em que você pode trabalhar. Use o mkdir com um nome de diretório difícil de adivinhar. Ou melhor, use o comando “mktemp -d”. Em seguida, copie o arquivo de dados usando cp e renomeie-o usando mv (leia o manpages!)

### Comandos que você pode precisar para resolver este nível

`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file`

### Material de leitura útil

**[Hexdump na Wikipédia](https://en.wikipedia.org/wiki/Hex_dump)**

---

**Solução**

```bash
# Visualizar conteúdo do arquivo
cat data.txt
```

```bash
# Entrar na pasta tmp
cd /tmp
```
```bash
# Criar um diretório temporário
mktmp -d
```
```bash
# copiar o arquivo data.txt para a pasta temporária
cp ~/data.txt /tmp/tmp.JGT8lCwhih
```
```bash
# Entrar na pasta e conferir o arquivo
cd tmp.JGT8lCwhih && ls
```
```bash
# Converter hexdump para binário e criar outro arquivo
xxd -r data.txt > data
```
```bash
# descobrir qual é o tipo do arquivo
file data
```
```bash
# Remover o data.txt e renomear o data para descompactar em formato .gz
rm data.txt && mv data data.gz
```
```bash
# decompactar data.gz
gzip -d data.gz
```
```bash
# ver o tipo do arquivo
file data
```
```bash
# renomeia o arquivo com a extensão .bz2
mv data data.bz2
```
```bash
# descompacta arquivo bzip2
bzip2 -d data.bz2
```
> Segue essa lógica, descompactando o arquivo até encontrar à senha
```bash
cat data
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```


**Senha:** FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

---

## Level 13

**Problema**

A senha para o próximo nível é armazenada em /etc/bandit_pass/bandit14 e só pode ser lido pelo usuário bandit14. Para este nível, você não recebe a próxima senha, mas você obter uma chave SSH privada que pode ser usada para fazer login no próximo nível. Nota: localhost é um nome de host que se refere à máquina você está trabalhando.

### Comandos que você pode precisar para resolver este nível

`ssh`, `telnet`, `nc`, `openssl`, `s_client`, `nmap`

### Material de leitura útil

**[SSH/OpenSSH/Keys](https://help.ubuntu.com/community/SSH/OpenSSH/Keys)**

--- 

**Solução**
