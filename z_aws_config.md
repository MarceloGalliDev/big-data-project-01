### Create EC2 instance
```
chmod 400 "{name}.pem"

ssh -i "{name}.pem" ubuntu@{chave}.compute-1.amazonaws.com
```

### Structure Bucket S3
The files inside the bucket follow this path pattern: `<bucket>/folder/subfolder/file.csv`

Maximum size file is `5Gbytes`

Object tag's: up to `10 key/value pairs`

### S3 Layers
S3 Standard - for general user

S3 Infrequent Access - for IA

S3 One Zone - for use to one layer

S3 Smart Layer - for optimize price

Glacier - files to archive

### S3 Lifecycle
Root Bucket > Gerenciamento 

Incluir um nome

O prefix é a pasta que será aplicado a regra

Podemos aplicar a transição dos dados para determinado tipo de classe

### S3 Security
Existe 4 tipos de chaves

SSE-S3 - chaves gerenciada pela aws

SSE-KMS - chaves gerenciada pela aws mas temos acesso

SSE-C - chaves gerenciada pelo usuario

Criptografia do lado do cliente - dados ja chegam criptografados

### S3 Tags
Usamos tags para incluir conjuntos de chave/valor, para variadas situações, como por exemplo segurança