## Analisador léxico para tratar de queries mais complexas

tags: [[Projeto Py-Drive]] [[Python]] [[Programação]]

### Descrição:
---
A ideia aqui seria implementar um analisador léxico para poder criar queries mais complexas sem a necessidade de aumentar a quantidade de parâmentros. Um exemplo seria poder criar um caracteres especiais para executar comandos, talvez algo como `'c['text']'` para poder usar o operador `contain` de queries ao invés de utilizar o parâmentro `in_name:str`.

Essa ideia é mais #ambiciosa, então vou deixá-la para depois, mas acho que seria algo muito interessante para adicionar no futuro.

Pensando bem, talvez possa utilizar essa ideia de forma mais simples, utilizando o sistema de comandos da cli e a função `build_query` e algumas flags como por exemplo `$contains` de forma que a função que gera o query recebe uma lista e consiga interpretar que o valor anterior é uma `query_term` o atual é um `operator` e o próximo um `value`.
### Passos:
---

### Passos Concluídos:
---

### Referências:
---
