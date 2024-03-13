### Glue
- serviço de etl
- baseado em spark
- schema = meta dados
- necessario conectar a origem e destino dos dados
- connector, possui informações necessárias para conexões com fontes de dados 
#
##### Crawler
- ele descobre o esquema dos dados
- cria metadados no Glue "Data Catalog"
#
##### Glue Job
- Processo ETL
    - Origem
    - Transformações
    - Destino
- Executados
    - Batch
    - Triggered
    - On Demand
- Cuidados
    - Cuidado com nomes iguais em diferentes tabelas
    - Necessario troca os nomes