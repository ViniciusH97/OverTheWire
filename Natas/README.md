# Natas

## A Natas ensina o básico da segurança na web do lado do servidor.

Cada nível de natas consiste em seu próprio site localizado em http://natasX.natas.labs.overthewire.org, onde X é o nível número. Não há login SSH. Para acessar um nível, insira o nome de usuário para esse nível (por exemplo, natas0 para o nível 0) e sua senha.

Cada nível tem acesso à senha do próximo nível. O teu trabalho é de alguma forma obter essa próxima senha e subir de nível. Todas as senhas também são armazenado em /etc/natas_webpass/. Por exemplo, a senha do natas5 é armazenada no arquivo /etc/natas_webpass/natas5 e apenas legível por natas4 e natas5.

Comece aqui:

Username: natas0
Password: natas0
URL:      http://natas0.natas.labs.overthewire.org

Ferramentas que você pode achar úteis para resolver este jogo de guerra

Um navegador de webbrowser, curl, proxy ZAP

## ìndice

- [Level 0](#Level-0)

### Level 0

Username: natas0
Password: natas0
URL:      http://natas0.natas.labs.overthewire.org

<img width="401" height="320" alt="image1" src="https://github.com/user-attachments/assets/26f816a1-2f79-4a82-bfba-a998b9c0a5eb" />

---

### Level 0 -> Level 1

A senha pode ser visualizada no código fonte da página, utilizando a opção `View Page Source`.

<img width="1113" height="435" alt="image2" src="https://github.com/user-attachments/assets/c513e3fa-d074-4bb0-b576-cc2aa8e31e17" />


Password: 0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq 

---

### Level 1 -> Level 2

Como o clique direito está bloqueado optei por utilizar a requisição `POST` do login pela ferramenta `httpx`. É possível utilizar o curl também.

Comando:

```bash
httpx -m POST http://natas1.natas.labs.overthewire.org/ --auth natas1 0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq
```

<img width="1266" height="725" alt="image3" src="https://github.com/user-attachments/assets/2c17541e-94d8-4710-8b77-6aaedb461155" />


ou com o `curl`

```bash
curl -X POST http://natas1.natas.labs.overthewire.org/ -u natas1 
```

<img width="927" height="510" alt="image4" src="https://github.com/user-attachments/assets/2bd6be83-aff5-4973-8ec5-1e0c84c4cdfa" />


Password: TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI

---
