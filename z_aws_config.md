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

### Conecting to instance aws
```
Utilizar ssh
sudo su - postgres
psql -U postgres
\c {database}
```

Para executar script dentro do banco de dados
```
\i /var/lib/postgresql/relacional/{files}.sql
```

Verificar relações
```
\dt *.*
```

Inserindo dados no banco
```
INSERT INTO relacional.clientes(idcliente, cliente, estado, sexo, status)
VALUE (251, 'Fernando Amaral', 'RS', 'M', 'Silver');
```

### Data Warehouse
Criando cluster com RedShift

Observar os custos

### Tipos de NoSQL
Key Value (Hash, KVM)
> não existe um tipo de documento
> busca por linha de acordo com a Key
> devido a sua simplicidade no tipo de armazenamento, é muito eficiente em consultas

Ordenado a colunas (cassandra)
> usado para compreensao de dados
> a busca é tida por colunas especificas, nao se carrega toda a tabela de dados
> cada coluna é armazenada separadamente

Orientado a documentos (MongoDB)
> armazena uma key value
> documento estruturado com metadados fixados
> geralmente é usado o JSON
> estrutura separado por nome/valor, entre aspas duplas
> separados por virgula
> chaves separam os objetos
> vetores sao suportados atraves de colchete
> suporta esses tipos de dados: String / Numero / Vetor / Booleano / Nulo / Objeto
> exemplo:
```
{"clientes": [
    {"nome": "Marcelo", "sobrenome": "Galli"}
    {"nome": "John", "sobrenome": "Doe"}
]}
```

Orientados a grafos
> composto por vertices e arestas
> usado geralmente por redes sociais
> podendo ser grafo valorado, nulo ou direcionado
> podendo ser grafo direcionado ou nao direcionado


### MongoDB
Open source  
Multiplaforma  
Escalável  
Orientado a objeto: JSON  
Permite documentos aninhados  
Indexados com metadados
Não tem schema fixo
Não tem integridade referencial  
#
#### Comparando banco de dados relacional com MongoDB:  
Tabela = Coleção  
Linha = Documento  
Coluna = Campo  
#
#### Tipo de dados:  
String  
Booleano  
Inteiro  
Double  
Array 
Timestamp  
Object  
#
#### Criando e inserindo dados na Coleção:
```
db.createCollection("Clients")
```

```
db.{nome_da_coleção}.insert(
    {nome: "Jonh", post: "Good post!", date: "2024-03-05"}
)
WriteResult({ "nInserted": 1})
```

```
db.{nome_da_coleção}.insert[(
    {nome: "Jonh", post: "Good post!", date: "2024-03-05"},
    {nome: "Joseph", post: "Good post!", date: "2024-03-04"},
    {nome: "Mariah", post: "Good post!", date: "2024-03-03"}
)]
BulkWriteResult({ "nInserted": 1})
```
#
#### Recuperando dados/objetos
```
db.{nome_da_coleção}.find()
```

```
db.{nome_da_coleção}.findOne()
```

```
db.{nome_da_coleção}.find().pretty()
```
#
#### Usando operadores
```
$or = ou
$eq = igual
$gt = maior que
$gte = maior ou igual que
$lt = menor que
$lte = menor ou igual que
$ne = diferente de
$in = contém
$nin = não contém
$set = selecionar
```
#
#### Embedded Documents
```
{
    _id: "1010",
    nome: : "Jose"
}
{
    _id: "1010",
    endereco: "Rua Delta",
    cidade: "Beta",
    estado: "Pi",
    cep: "99999100"
}

{
    _id: "1010",
    nome: : "Jose"
    endereco: {
        endereco: "Rua Delta",
        cidade: "Beta",
        estado: "Pi",
        cep: "99999100"
    }
}
```
#
#### Document References
```
{
    _id: "1010",
    nome: : "Jose"
    endereco: [121234]
}
{
    _id: "121234",
    endereco: "Rua Delta",
    cidade: "Beta",
    estado: "Pi",
    cep: "99999100"
}
```