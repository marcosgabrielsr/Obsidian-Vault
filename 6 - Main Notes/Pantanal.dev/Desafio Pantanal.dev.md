2025-09-23 20:11

Status: #adult

Tags: [[Pantanal.dev]] [[Artificial Inteligence]] [[University Activities]]

# Desafio Pantanal.dev

#### Desafio: Validação de Saídas de um Sistema RAG (Retrieval-Augmented Generation) com uso de ML

**Contexto:**
Em diversas empresas estamos vendo a utilização da arquitetura RAG (Retrieval-Augmented Generation) para a criação de diversos chatbots relacionados aos seus dados, mas garantir a integridade e a precisão das informações que são geradas por sistemas de IA é crucial para o sucesso da aplicação. Este desafio visa criar um sistema de RAG que forneça respostas baseadas em dados extraídos de documentos de referência e também valide os fatos da saída com um score de confiança.

A  base de dados a ser utilizada na tarefa é de livre escolha. Entretanto, o site ENET ([Consulta de Documentos de Companhias Abertas (cvm.gov.br)](https://www.rad.cvm.gov.br/ENET/frmConsultaExternaCVM.aspx)) e FundosNET ([Fundnnos.NET (bmfbovespa.cozm.br)](https://fnet.bmfbovespa.com.br/fnet/publico/abrirGerenciadorDocumentosCVM)) são as recomendações da B3 por conterem uma gama de documentos não estruturados em formato .pdf, podendo haver imagens, gráficos, tabelas dentro deles. Aumentando o desafio e possibilitando avaliar melhor os times.

Os alunos devem desenvolver um projeto arquitetural detalhado, explicar a metodologia do score de confiança, implementar uma fila para processamento assíncrono dos documentos, e documentar os requisitos funcionais e não-funcionais

**Tecnologias e Ferramentas Sugeridas:**
- Machine Learning/Deep Learning: PyTorch.
- Framework de API: FastAPI.    
- Containerização: Docker.    
- Armazenamento: Azure Blob Storage, Azure CosmosDB for MongoDB, MongoDB, AWS S3.    

**Dicas**
- Analisar o domínio na hora de escolher o modelo: no momento de escolher modelos que normalizam dados com caixa baixa/alta e que fazem uma limpeza de acentos;
- Estado da arte pode ser caro, mas o estado da prática deve ser barato;
- Fazer similaridade de texto;
- Usar *infoNCE LOSS* (retrieval e score de confiabilidade);
- Utilizar técnicas de busca híbrida;
- Utilizar FactScore para score de confiabilidade das respostas;
- Utilizar técnicas de busca na internet para melhorar a resposta e agregar mais confiabilidade ao produto;
- Equilibrar a *Ciência* com as *Regras de Negócio*;
- Pesquisar sobre *tool calling*;
# References

