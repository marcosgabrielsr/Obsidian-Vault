# Acesso automatizado ao Google Drive com Python

Tags: [[Projetos]] [[Python]] [[Progamação]]

### Descrição:
---
O objetivo deste projeto é ser uma ferramenta CLI (comand line interface), uma aplicação de terminal que me permita gerenciar melhor minhas pastas armazenadas no google drive. A necessidade de criar este projeto veio do fato das minhas trocas de sistema operacional e também pelo motivo de ter um backup na nuvem dos meus arquivos para caso algo aconteça com minhas ferramentas locais. Portanto, com esta ferramenta pretendo poder fazer downloads e uploads dos meus arquivos para o drive e para meu computador local de forma automatizada, sem a nessecidade de abrir o navegador e puxar e soltar arquivos na página web, similar ao git.

### Objetivos:
---
Para traçar um mapa do que eu pretendo fazer, devo seguir os seguintes passos:
- **Definir uma Estrutura Robusta de Projeto:** Esta etapa é importante para que meu projeto fique organizado e resistente à quebras. A estrutura que utilizo atualmente vem do Gemini, mas obviamente posso modificá-la e deixá-la da melhor forma para mim;
- **Criar uma ferramenta CLI com Python:** Acredito que posso utilizar como exemplo ferramentas que eu já tenha utilizado como `bluetoothctl` e `nmcli`;
- **Fazer Listagem de Arquivos:** Acredito que esta seja uma das primeiras e mais importantes, preciso ver o que eu quero baixar. Posso dar continuidade ao quickstart que eu vi e também ler a documentação para que eu possa imprimir mais do que simplesmente os "10 primeiros arquivos que eu editei por último";
- **Fazer Download dos arquivos:** Esta funcionalidade permitirá fazer o download de arquivos e pastas separadamente independente dos caminhos de ambos.
- **Fazer Upload de arquivos:** Esta opção também é importante, pois permitirá que eu possa subir meus arquivos para o drive. Ela também se faz complicada, pois a ideia e deixar este projeto similar ao git, então precisarei fazer upload apenas de arquivos que não foram modificados, dessa forma posso evitar ter que fazer upload de todos os meus arquivos;
- **Atualizar Sistema de Conexão:** Última e uma das mais importantes etapas, analisando projetos similares ao meu no github, percebi que eles utilizam sistemas via terminal para permitir que o usuário faça cadastro no projeto do `Google Workspaces` então preciso entender isso e aplicar ao meu projeto para evitar a necessidade de abrir o navegador e fazer o cadastro;

Para melhor análise das etapas concluídas irei utilizar a ferramenta de canvas [[Mapa Py-Drive.canvas]].
### Referências:
- Documentação Py-Doc da API do Google Drive: https://developers.google.com/resources/api-libraries/documentation/drive/v3/python/latest/drive_v3.files.html
- Tutorial rápido de como usar a API do Google Drive: https://developers.google.com/workspace/drive/api/quickstart/python
- Página principal da API do Google Drive: https://developers.google.com/workspace/drive/api/guides/about-sdk