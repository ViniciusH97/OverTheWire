## Level 1

---

### Problema: 

Acessar o conteúdo de um arquivo chamado - . Esse nome é problemático, pois o shell pode interpretar o - como uma opção do comando.

### Solução:

```bash
ls
cat < -
```