2025-08-27 08:22

Status: #child 

Tags: [[OESNPG Project]] [[Artificial Inteligence]]

# ADR.001 - Técnicas e Ferramentas de Geração de Embeddings  

## Context and Problem Statement
---
O objetivo deste trabalho é gerar representações vetoriais de textos em português para a classificação e agrupamento dos temas de trabalho de pós-graduação divulgados pela CAPES.

Os textos de entrada serão títulos dos trabalhos de pós-graduação, estes títulos serão fragmentados em três partes: **título**, **descrição**, **palavras-chave**; contendo termos técnicos do âmbito acadêmico.

O ambiente de execução será um servidor local com GPU limitada, os modelos selecionados devem possuir um equilíbrio entre precisão e eficiência computacional.

A avaliação dos embeddings...

---

## Decision Drivers
---
- Necessidade de **representar textos em português** de forma vetorial preservando significado semântico.  
- Busca por **modelos pré-treinados acessíveis e de fácil integração** com Python.  
- Desejo de comparar **desempenho entre modelos multilíngues e modelos específicos para o português**.  
- Limitação de **recursos computacionais** disponíveis (CPU e GPU da universidade).  
- Facilidade de reprodutibilidade dos resultados por outros pesquisadores.

---

## Considered Options
---
Os principais modelos utilizados para a geração de embeddings são os da biblioteca **Sentence Transformers** em Python, que fornece vários modelos pré-treinados capazes de calcular representações vetoriais de tamanho fixo (*embeddings*).  

Grande parte dos modelos oferecidos por este pacote consegue lidar com múltiplas línguas, incluindo o português, apresentando boa precisão semântica, baixo custo computacional e fácil integração com Python.

| Opção                                     | Descrição                                                       | Prós                                                                    | Contras                                                   |
| ----------------------------------------- | --------------------------------------------------------------- | ----------------------------------------------------------------------- | --------------------------------------------------------- |
| **paraphrase-multilingual-mpnet-base-v2** | Modelo multilíngue de alta precisão semântica baseado em MPNet. | Boa generalização entre línguas; alto desempenho em tarefas semânticas. | Maior tempo de inferência.                                |
| **distiluse-multilingual-cased-v1**       | Versão reduzida de USE (Universal Sentence Encoder).            | Leve e rápido; bom equilíbrio entre custo e precisão.                   | Menor desempenho em nuances semânticas complexas.         |
| **all-MiniLM-l12-v2**                     | Modelo leve e eficiente para similaridade semântica.            | Boa precisão; rápido; baixo consumo de memória.                         | Treinado principalmente em inglês.                        |
| **bert-base-portuguese-cased**            | Modelo BERT específico para o português.                        | Especializado no idioma alvo; bom desempenho em tarefas locais.         | Necessita adaptação para uso com *Sentence Transformers*. |
O modelo **bert-base-portuguese-cased** não é originalmente oferecido pela biblioteca *Sentence Transformers*, mas sim um modelo BERT pré-treinado para o português brasileiro disponibilizado pela comunidade.

---

## Decision Outcome
---
Foi decidido utilizar o modelo **paraphrase-multilingual-mpnet-base-v2** como principal ferramenta de geração de *embeddings* no projeto.  
Essa escolha foi feita com base em sua **alta precisão semântica**, **suporte multilíngue**, e **compatibilidade direta com a biblioteca Sentence Transformers**, o que simplifica a integração e experimentação.  

Os demais modelos serão utilizados para **fins comparativos**, avaliando trade-offs de desempenho, tempo de inferência e adequação à língua portuguesa.

---

## Consequences
---
**Positivas:**  
- Fácil implementação e integração com Python.  
- Resultados semânticos robustos em português e inglês.  
- Permite comparações consistentes com outros modelos multilíngues.

**Negativas:**  
- Maior tempo de inferência em comparação a modelos menores.  
- Dependência de GPU para processar grandes volumes de dados de forma eficiente.  

---

## Alternatives and Future Considerations
---
- Testar modelos de última geração, como **text-embedding-3-large** (OpenAI) ou **E5-mistral** (Hugging Face).  
- Avaliar redução de dimensionalidade via PCA ou UMAP para visualização e clusterização.  
- Investigar técnicas de *fine-tuning* com corpus em português.  

---

## References
---
- [Reimers & Gurevych (2019). Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks.](https://arxiv.org/abs/1908.10084)  
- [Sentence Transformers Documentation](https://www.sbert.net/)  
- [Hugging Face Model Hub](https://huggingface.co/models)  
- [BERTimbau: BERT for Portuguese](https://github.com/neuralmind-ai/portuguese-bert)


