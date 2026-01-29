## Sistema de listagem de arquivos e pastas contidos no Drive

tags: [[Projeto Py-Drive]] [[Python]] [[Programação]]

### Ideias:
---
- [ ] Utilizar sistema de queries para sempre evitar arquivos na lixeira e também para poder adicionar sistemas condicionais, como busca por nome e por talvez conteúdo;
### Concluídas:
---
- [x] Utilizar sistema de nextPage da resposta da API do google drive para poder coletar todos os arquivos retornados da API por conta do limite de 100 arquivos. Isso pode ser feito utilizando um while e também aplicando um sistema condicional para verificar se total de arquivos coletados não chega a ser maior do que o limite definido pelo parâmetro pg_size;
- [x] Renomear alguns parâmetros aplicando o padrão `Snake Case`;
### Referências:
- Documentação Py-Doc da API do Google Drive: https://developers.google.com/resources/api-libraries/documentation/drive/v3/python/latest/drive_v3.files.html
- Tutorial rápido de como usar a API do Google Drive: https://developers.google.com/workspace/drive/api/quickstart/python
- Página principal da API do Google Drive: https://developers.google.com/workspace/drive/api/guides/about-sdk
- Documentação da biblioteca Typer: https://typer.tiangolo.com/tutorial/commands/
- Como criar um programa de lista de tarefas de linha de comando com Python: https://realpython.com/python-typer-cli/