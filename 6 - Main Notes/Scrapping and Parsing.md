2025-10-23 08:02

Status: #teen 

Tags:[[Pantanal.dev]] [[Desafio Pantanal.dev]]

# Scrapping and Parsing

### Pipeline Geral
- **Crawling / download** — baixar PDFs (ou páginas HTML) com um crawler (ex.: `requests`/`aiohttp`, `Scrapy`, ou headless browser `Playwright`/`Selenium` quando a página exige JS).
    
- **Classificação inicial** — identificar se o PDF é _digitally generated_ (texto embutido) ou _scanned image_ (precisa OCR).
    
- **Pré-processamento**
    - Para _scanned_: rodar OCR (ex.: `ocrmypdf` que usa Tesseract, ou serviços cloud).
        
    - Normalizar nomes, remover páginas irrelevantes, metadata.
        
- **Extração** — separar e extrair **texto**, **tabelas**, **imagens/figuras**, **metadados** e **posicionamento (bbox / page)**.
    
- **Parsing / limpeza** — limpar texto (normalização, remover headers/footers), converter tabelas para CSV/Parquet, salvar imagens em diretório com metadados (origem, página, bbox).

### Técnicas por tipo de conteúdo
#### Texto (PDF digital)
- **Leitura direta**: extrair texto que já está no PDF (text layer) com bibliotecas como **PyMuPDF (fitz)**, **pdfplumber**, **pdfminer.six** ou **PyPDF2**. PyMuPDF é rápido e dá bom acesso a layout/posicionamento. [pymupdf.readthedocs.io+1](https://pymupdf.readthedocs.io/en/latest/the-basics.html?utm_source=chatgpt.com)

#### Texto (PDF escaneado / imagens)
- **OCR**: usar `ocrmypdf` (workflow local que aplica Tesseract e preserva o PDF com camada de texto) ou serviços cloud (Amazon Textract, Azure Document Intelligence, Google Document AI) quando precisar de alta qualidade/estruturas complexas. Teste diferentes engines; cloud costuma ser mais robusto em layouts/handwriting. [GitHub+2Amazon Web Services, Inc.+2](https://github.com/ocrmypdf/OCRmyPDF?utm_source=chatgpt.com)

#### Tabelas
- Se o PDF é _vetorial_ (tabelas reais no PDF): **Camelot** e **Tabula-py** funcionam bem para tabelas “reticuladas” — exportam direto para CSV/JSON/Excel. Para layouts mais complexos, `pdfplumber` ou abordagens baseadas em layout (Unstructured) ajudam. Para PDFs escaneados, combine OCR primeiro e depois extração de tabela (ou use ferramentas cloud que suportam tabelas). [Unstract.com →+1](https://unstract.com/blog/extract-tables-from-pdf-python/?utm_source=chatgpt.com)

#### Imagens / Figuras
- **Extrair imagens embutidas** diretamente do PDF com **PyMuPDF** (consegue extrair os bitmaps originais) ou `pikepdf`/`pdfminer` para casos especiais. Salve metadados: página, x/y, tamanho, formato. [pymupdf.readthedocs.io+1](https://pymupdf.readthedocs.io/en/latest/recipes-images.html?utm_source=chatgpt.com)
#### Gráficos / plots (extrair os dados dos gráficos)
- Para **recuperar os números que geraram um gráfico**, use ferramentas de digitização de gráficos como **WebPlotDigitizer** (UI web) ou bibliotecas de digitização em lote (`plotdigitizer`) se tiver muitos gráficos. Para automatizar, combine detecção de regiões (OpenCV) + digitizer. [PlotDigitizer+1](https://plotdigitizer.com/?utm_source=chatgpt.com)
# References
