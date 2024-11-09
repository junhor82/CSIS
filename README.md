Os scripts foram desenvolvidos para apoiar a análise de dados na tese de doutorado do Instituto Meira Mattos (IMM), facilitando a interpretação e segmentação de eventos cibernéticos significativos da base de dados do CSIS. O projeto utiliza a linguagem Python em Jupyter Notebook (Anaconda) para processar e organizar as informações de maneira analítica.

Descrição dos scripts:

1) BD_CSIS.ipynb:
  1) Realiza o download da base de dados de eventos cibernéticos significativos do CSIS (disponível em: https://csis-website-prod.s3.amazonaws.com/s3fs-public/2024-10/241007_Significant_Cyber_Events.pdf?VersionId=qn46PstY2SYKbsaXoE5F572aXHzv2E8r).
  2) Executa OCR no arquivo PDF baixado, convertendo-o em um arquivo de texto (ort.txt) adequado para análise.

2) FiltroEUA.ipynb:
  1) Lê o arquivo ort.txt.
  2) Filtra os dados para eventos relacionados aos Estados Unidos.
  3) Gera uma tabela CSV (bdEUA.csv) com os seguintes campos: ID, ano, mês e descrição dos eventos relevantes.
  4) OBS: Inclui a possibilidade de personalizar o filtro palavras_a_filtrar para refinar a pesquisa conforme a necessidade do analista.

3) OrganizacaoCSV.ipynb: Organiza os eventos em uma tabela detalhada, extraindo os seguintes campos com base na voz ativa ou passiva:
  1) País atacado.
  2) Estrutura atacada (estatal ou não estatal).
  3) País atacante.
  4) Estrutura atacante (estatal ou não estatal).
  5) Ferramentas utilizadas no ataque.
  6) Efeitos do ataque, classificados em físico, digital, econômico, psicológico, político/reputacional e societal.
  7) Classificação dos eventos em tipos de ação cibernética: guerra cibernética, inteligência cibernética, crime cibernético ou ataque cibernético.
  8) Verificação e ajuste de termos para consistência.
  9) O resultado final é uma tabela CSV (sabeSeparada.csv) com todos os eventos envolvendo os EUA, tanto como atacante quanto como atacado.
      
4) Atacado_analise_da_base_de_dados.ipynb:
  1) Segmenta os eventos onde os Estados Unidos foram alvos de ataques, extraindo linhas que identificam o país como atacado.
  2) Forma uma base de dados CSV, chamada "baseAtacado.csv"

5) Atacante_analise_da_base_de_dados.ipynb:
  1) Segmenta os eventos em que os Estados Unidos atuaram como atacantes, extraindo as linhas correspondentes.
  2) Forma uma base de dados CSV, chamada "baseAtacante.csv"
