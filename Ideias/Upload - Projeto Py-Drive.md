## Sistema de upload de arquivos para o google drive com a API do Google Drive v3

tags: [[Projeto Py-Drive]] [[Python]] [[Programação]]

### Descrição:
---
A ideia aqui é implementar um sistema de upload simples e abranjente, de forma que eu possa utilizá-lo sem complicações no meu sistema e que ele me ajude e não cause dores de cabeça.
### Passos:
---
- [ ] Utilizar sistema de upload básico apresentado no tutorial da google sobre a API;
- [ ] Utilizar bibliotecas como `pathlib` e `os` para verificar se o upload é de um arquivo simples ou de uma pasta:
	- **Arquivo simples:** Chamar função de upload para o arquivo;
	- **Pasta:** Iterar sobre a pasta e aplicar função simples sobre todos os arquivos;
### Referências:
- Documentação Py-Doc da API do Google Drive: https://developers.google.com/resources/api-libraries/documentation/drive/v3/python/latest/drive_v3.files.html
- Tutorial rápido de como usar a API do Google Drive: https://developers.google.com/workspace/drive/api/quickstart/python
- Página principal da API do Google Drive: https://developers.google.com/workspace/drive/api/guides/about-sdk
- Documentação da biblioteca Typer: https://typer.tiangolo.com/tutorial/commands/
- Como criar um programa de lista de tarefas de linha de comando com Python: https://realpython.com/python-typer-cli/
- Documentação e tutorial sobre como listar pastas e arquivos: https://developers.google.com/workspace/drive/api/guides/search-files#python