2025-09-19 11:07

Status: #teen 

Tags: [[OESNPG Project]] [[Artificial Inteligence]] [[Embeddeds]]

# OESNPG - Teste com N=2 para o UMAP

#### Objetivo:
O principal objetivo deste teste é verificar como os dados são organizados e distribuídos quando os embeddings tem sua dimensão reduzida para **2** utilizando o UMAP.

#### Resultados:
-> Utilizando o Modelo: paraphrase-multilingual-mpnet-base-v2
- Para o primeiro teste os dados foram agrupados da seguinte forma(K=15):![[Pasted image 20250919111454.png]]
- Para o segundo teste os dados foram agrupados da seguinte forma(K=14):![[Pasted image 20250919111814.png]]
- Para o terceiro teste os dados foram agrupados da seguinte forma(K=16):![[Pasted image 20250919112340.png]]

-> Utilizando o Modelo: all-MiniLM-L12-v2
- Primeiro Teste: K = 20
	![[Pasted image 20251009121436.png]]
- Segundo Teste: 
#### Observações:
- Todos os testes foram feitos utilizando o mesmo objeto UMAP;
- O valor de K utilizando o silhouette score variou no intervalo [12,15];

# References

