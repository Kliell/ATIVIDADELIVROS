# ATIVIDADELIVROS
**Comando base** 


**O conceito de Middleware no Express e sua função com JSON e Apps Mobile**
No framework Express, o middleware funciona como uma camada intermediária que intercepta a requisição antes que ela chegue à rota final. Ele é essencial para o processamento de dados vindos de aplicativos mobile porque esses dispositivos geralmente enviam informações estruturadas no formato JSON. Como o Node.js recebe esses dados nativamente como fluxos de bytes brutos, o middleware `express.json()` atua como um tradutor automático, interpretando o corpo da requisição e transformando-o em um objeto JavaScript acessível via `req.body`. Sem essa etapa, o servidor seria incapaz de ler as informações enviadas pelo aplicativo, resultando em falhas na comunicação entre o frontend mobile e o backend.

**Diferenças entre NoSQL e SQL para catálogos de livros com estrutura volátil**
Para um catálogo de livros que sofre alterações constantes em sua estrutura, a principal diferença reside na flexibilidade do esquema. O banco de dados SQL tradicional utiliza um esquema rígido, onde cada alteração (como adicionar um campo para "link de audiolivro" ou "metadados de e-book") exige comandos complexos de alteração de tabela que podem ser lentos e arriscados em bases grandes. Já o NoSQL orientado a documentos, como o MongoDB, é "schema-less", o que significa que cada documento de livro pode ter sua própria estrutura independente. Isso permite que você adicione novos atributos a novos registros sem precisar modificar os antigos, oferecendo uma agilidade muito maior para evoluir o sistema conforme a necessidade do negócio.

**O papel do Hashing via bcryptjs na proteção de dados**
O hashing realizado pelo pacote `bcryptjs` é uma técnica de segurança unidirecional que transforma senhas em strings de caracteres fixos e ilegíveis. Diferente da criptografia comum, o hash não pode ser revertido para o texto original, o que garante que nem mesmo os administradores do sistema conheçam as senhas reais. O bcryptjs é especialmente eficaz porque utiliza um "salt" (valor aleatório) que torna cada hash único, mesmo para senhas idênticas, e possui um custo computacional ajustável que retarda tentativas de invasão por força bruta. Em caso de um eventual vazamento do banco de dados, os dados expostos seriam inúteis para o invasor, pois descobrir as senhas originais a partir dos hashes exigiria um tempo e poder computacional impraticáveis.

**Importância do arquivo .env e do pacote dotenv em produção e GitHub**
O arquivo `.env` e o pacote `dotenv` são pilares da segurança e da organização técnica, pois permitem separar as configurações de infraestrutura do código-fonte. O arquivo `.env` armazena variáveis sensíveis, como senhas de banco de dados e chaves secretas de API, garantindo que esses dados não fiquem expostos diretamente no código. Em projetos compartilhados via GitHub, é vital que o `.env` seja listado no arquivo `.gitignore`, impedindo que segredos sejam publicados em repositórios públicos. O pacote `dotenv` completa esse ciclo ao carregar essas variáveis para o ambiente de execução de forma segura, permitindo que o mesmo código funcione em diferentes ambientes (desenvolvimento ou produção) apenas trocando o conteúdo do arquivo de configuração, sem riscos de exposição de dados críticos.


