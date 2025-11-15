
<img width="338" height="79" alt="image" src="https://github.com/user-attachments/assets/827881e9-0492-4dea-abd7-8a3991dc0a82" />

## O que é o OverTheWire?

OverTheWire é uma plataforma de wargames, focado em aprendizado de terminal Linux e cibersegurança. Muito semelhante a problemas de capture the flag (CTF). A cada problema resolvido você encontra a chave (flag) para o próximo exercício, tornando o aprendizado não só desafiador mas também divertido.

## Wargames

Wargames é a coleção de jogos do OverTheWire, cada jogo possuem levels(níveis) que vão aumentando a dificuldade a cada problema que resolve.

São eles:

- [Bandit](https://github.com/ViniciusH97/OverTheWire/tree/main/Bandit)
- Leviathan
- Natas
- Kripton
- Narnia
- Behermoth
- Utumno
- Maze
- Vortex 
- Manpage 
- Drifter
- FormulaOne

## Como jogar?

Para jogar Wargames no OverTheWire, é necessário ter instalado o secure shell(SSH) em sua distribuição Linux. Caso não houver, instale utilizando o comando:
```bash
sudo apt install openssh-client openssh-server
```

Em seguida, selecione o nível de dificuldade, e níveis em cada Wargame. Na tela principal há uma lista dos wargames. Selecione o Bandit para começar, e clique no level 0.

Para conectar com o host via ssh podemos usar o comando abaixo, esse é um exemplo para entrar no jogo Bandit0:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
Insira a Senha `bandit0`. A partir desse momento, poderá seguir a resolução do problema.
