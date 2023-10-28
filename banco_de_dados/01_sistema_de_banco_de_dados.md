# Sistema de banco de dados

Banco de dados = 'banco de dados é uma coleção de dados relacionados'

sgbd = 'independência entre dados e programas'

banco ---- sdbd ---- aplicação

middleware = 'O middleware é um software que diferentes aplicações usam para se
comunicar umas com as outras. Ele oferece funcionalidade para conectar
aplicações de modo inteligente e eficiente, para que você possa inovar mais
rapidamente. O middleware atua como uma ponte entre diversas tecnologias,
ferramentas e bancos de dados para integrá-los perfeitamente em um único
sistema.'

fonte de dados ---- middleware ---- aplicação web

### Tabelas
atributo = colunas
valores dos atributos = conteúdo
tipos = int, char, boolean
esquema = conjunto de atributos de um tabela
tupla = linha de uma tabela
instância = conjunto de linhas de uma tabela
campo = encontro da linha com a coluna
valor = conteúdo de um campo
nulo = ausência de valor em um campo


chave primária = id da tabela (provê a integridade de chave primária)
chave primária composta = quando utiliza o valor de duas tabelas
chave candidata = quando um campos é único e pode se utilizado como pk

chave estrangeira = provê a ligação entre as tabelas relacionada


### Diferenças entre sistema de arquivos e sistema de banco de dados

#### Níveis de esquemas

- O __nível externo__: Descreve como os dados são armazenados no computador
como: tipos de arquivos, formatos e ordenação de registros e caminhos de
acesso.

- O __nível conceitual__: São aqueles que representam, de maneira abstrata, a
implementação dos bancos de dados, ocultando detalhes de como os dados são
armazenados e acessados no disco.

- O __nível interno__: São aqueles que representam a visão dos dados do ponto
de vista do usuário final, no nível de abstração mais próximo do mundo real.


#### Gera dois tipos de idependências

- __Independência lógica de dados__: consiste em alterar o esquema conceitual
lógico sem afetar o esquema conceitual externo.

- __Independência física de dados__: consiste em alterar o esquema conceitual
físico (com a reestruturação dos arquivos, diretório ou partição do banco) sem
afetar o esquema conceitual lógico ou externo.

outras características:

- Natureza autocontida: trata-se dos metadados, que contém descrições sobre
estruturas e restrições das tabelas.

- Abstração de dados: trata-se do ocultamento no modelo conceitual de dados
dos metadados retratados anteriormente.

- Suporte ao compartilhamento de dados e processamento de transações
concorrentes: trata-se da do acesso concorrente - múltiplo - aos dados contidos
no sbd.

> Nota: quando é alterado algo na estrutura do arquivo do modelo tradicional,
> o software terá que ser readaptado para manter a fluência na comunicação,
> porém, no modelo com a adição dos sgbd's uma alteração na estrutura do
> arquivo apenas impacta na reformulação dos arquivos com os metadados dos
> dados em questão, onde isso é responsabilidade so próprio sgbd.

#### Garantias providas pelo SGBD - ACID

- Atomicidade: Cada transação é tratada como uma unidade composta de uma
sequência de operações, de modo que deve executar completamente com sucesso ou
falhar completamente.

  - Begin Transaction: Trata-se da operação que marca o início da transação
  e só será encerrada com um commit ou rollback.

  - Commit: Trata-se da operação que indica que a transação foi realizada com
  êxito, portanto os concluída e os dados originais sobrepostos.

  - Rollback: Trata-se da operação que indica que a transação foi realizada com
  falha, portanto será abortada e os dados originais serão mantidos.

- Consistência: Uma transação só pode levar o banco de dados de um estado
válido para outro, de acordo com suas regras de integridade, ou seja, embora
exista o acesso múltiplo, as transações são sequenciais para prover a
consistência nos dados.

- Isolamento: Cada transação é isolada das demais, isto é, essa propriedade
assegura que transações executadas concorrentemente levem o banco de dados ao
mesmo estado que chegaria se as transações fossem executadas sequencialmente.

- Durabilidade: Uma vez que a transação é aceita (committed), o que significa
que seu resultado foi gravado em memória não volátil, esse resultado
permanecerá válido mesmo em caso de falhas do sistema através dos mecanismo de
recuperação.


