# Bandit

- [Level 0](#Level-0)
- [Level 1](#Level-1)
- [Level 2](#Level-2)
- [Level 3](#Level-3)
- [Level 5](#Level-5)
- [Level 6](#Level-6)

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
---

## Level 1

### Problema: 

Acessar o conteúdo de um arquivo chamado - . Esse nome é problemático, pois o shell pode interpretar o - como uma opção do comando.

### Solução:

```bash
ls
cat < -
```
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

senha: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

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

senha: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

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
cat ./-file07
```

senha: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

---

## Level 5

### Problema:

Encontrar a senha em algum lugar no diretório inhere com as seguintes caracterísiticas:

 - Legível para o ser humano
 - 1033 bytes de tamanho
 - não executável

### Solução:

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
senha: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

---

## Level 6

### Problema:

Encontrar a senha em um arquivo no servidor com as seguintes características:

```bash
dono por usuário  bandit7
```
  - dono por grupo bandit6
  - 33 bytes de tamanho

Solução:

```bash
cd /
```
```bash
find -user bandit7 -group bandit6 -size 33c 2>/dev/null
```
```bash
cat /var/lib/dpkg/info/bandit7.password
```

senha: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
---
Level 7
