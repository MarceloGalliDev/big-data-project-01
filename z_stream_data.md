### Kinesis Data Stream
- Tempo real ou próximo do real
#### Produtores:
- Aceita 1mb por segundo ou 1000 mensagens por escrita em um `SHARD`
#### Consumidores:
- Aceita 2mb por segundo em um `SHARD`
- 5 chamadas de API por `SHARD` entre todos Consumidores
#
#### Retençao dados
- 24 horas por padrão, podendo ser estendido por 7 dias.
#
### Kinesis Data Firehose
- Latencia de 60 segundos.
- Podemos fazer ingestão de dados do S3, Redshift, ElasticSearch, Splunk
- Converte dados CSV / JSON para Parquet ou ORC
- Suporta compresão de dados quando usado S3
- Paga-se pela quantidade de dados que entra no Firehouse
- Os dados produzidos pelo produtor pode ser acessado por vários consumidores