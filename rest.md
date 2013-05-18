## Introdução

Em 1990, a web começou a ganhar força, e as pessoas começaram a perceber uma maneira de fazer negocios na web, surgindo assim, a necessidade de algum meio de se realizar transações pela internet. Surgiu então um novo paradigma; como evoluir a web, sair de uma web de páginas, para uma web de serviços?

A partir desse "problema", em 1998, algumas empresas entre elas a Microsoft, criaram um padrão chamado XML-RPC. Esse padrão evoluiu com o passar do tempo, após algumas funcionalidades que foram adicionadas. Graças a essa evolução, o XML-RPC serviu como base para outro padrão, o SOAP.

SOAP (Simple Object Access Protocol) é um padrão baseado em ações, que nada mais é do que uma abstração para chamadas de métodos, no geral um serviço SOAP possui um único endereço de acesso e várias ações. Essas ações podem ocorrer sobre vários protocolos, tais como, SMTP e HTTP, tendo como grande benefício o controle fim a fim da mensagem.

O SOAP, quando utilizado com o protocolo HTTP, utiliza somente o verbo `POST` para transmissão das informações, um verbo que não pode ser utilizado com cache, uma vez que a especificiação HTTP define que apenas o verbo `GET` pode ser utilzado desta maneira. O uso do `POST` ocorre até mesmo para consulta de recursos somente leitura, cenário que poderia ser beneficiado pelo uso do cache. Apesar desta limitação, não podemos nos esquecer que o SOAP foi projetado para ser utilizado com vários protocolos diferentes e ele não pode tirar vantagem de características específicas à um ou outro protocolo.

#### Surgimento do REST

Com o passar do tempo, uma outra linha de pensamento começou a surgir. Ela era composta por pessoas com diferentes perspectivas de interoperabilidade, que não ia de encontro com os cenários empresarias muito bem atendidos pelo SOAP, motivando o surgimento do REST.

O termo REST nasceu na tese de doutorado do __Roy Fielding__, um dos criadores do protocolo HTTP. Em sua tese, ele escreveu sobre o sucesso da internet, do www e do próprio protocolo, descrevendo o funcionamento da internet como sendo um __Estado Representacional de Transferência__, em inglês __RE__PRESENTATIONAL __S__TATE __T__RANSFER, ou seja, REST, considerado como um estilo arquitetural, e não uma especificação. 

Os serviços que seguem o estilo arquitetural REST, são conhecidos como serviços RESTful, e se baseiam no funcionamento da web e do protocolo HTTP. Este funcionamento utiliza a estrutura de recursos, que pode ser definido como qualquer coisa importante o suficiente para ser referenciada ou utilizada por um sistema, algo que pode ser armazenado no computador ou representado como uma sequência de bits. Por exemplo, um arquivo de áudio, uma linha em uma tabela de um banco de dados ou o retorno de um algoritmo, podendo ser um objeto físico, como um livro, ou um conceito abstrato, como uma emoção. 

A exposição do endereço do serviço na rede é feita através de uma URI (Uniform Resource Indicator). A URI pode ser considerada uma das tecnologias fundamentais da web.

#### Funcionamento do REST

O funcionmaneto da "web de serviços", é baseado no mesmo princípio da "web de páginas". Ou seja, os serviços devem ser simples e abertos, permitindo que qualquer pessoa, em qualquer lugar, utilizando qualquer plataforma, seja capaz de utilizá-los. Devem ser baseados em um protocolo universal, que para web podemos considerar o HTTP, um protocolo aberto e amplamente conhecido. Os serviços devem também, expor recursos que possam ser associados através de URIs, característica que faz parte das raízes do funcionamento da web e, por uma questão de escala, devem ser apresentados através de uma comunicação sem estado e sempre que possível utilizar algum tipo de cache pelos mecanismos já existentes na infra da web.

As chamadas às URIs, são realizadas através de verbos HTTP. O verbo utilizado na requisição indica para o serviço que ação deve ser realizada com o recurso, os verbos principais são: `GET`, `POST`, `PUT`, `DELETE`.

* GET: Indica que o cliente quer obeter uma representação de somente leitura do recurso
* POST: Utilizado para criar um novo recurso
* PUT: Utilizado para atualizar um recurso existente
* DELETE: Como o próprio nome sugere, é utilizado para excluir um recurso existente

 

---

REST é um estilo de arquitetura de software para sistemas distribuídos, que serviu de molde para o protocolo HTTP. O termo surgiu em uma tese de doutorado sobre web escrita por Roy Fielding.

Roy Fielding ajudou a escrever os primeiros servidores web, fez pesquisas explicando porque a web funciona como ela funciona, entre outros. 

REST significa __RE__presentational __S__tate __T__ransfer (Transferência de Estado Representacional).

Para entender de onde veio esse nome, temos que conhecer primeiro os principais conceitos sobre REST.

* Recursos: São os elementos de informação na aplicação. Tudo aquilo que é importante ser exposto.

* Identificadores de recurso (URI): São usados para identificar recursos específicos para interações no sistema.

Híbrido, REST é um conjunto de vários estilos arquitetônicos baseados em rede, tais como 

## Roy Fielding

* Ajudou a escrever os primeiros servidores web;
* Fez pesquisas explicando porque a web funciona como ela funciona; :+1:
* O nome dele está na especificação do protocolo usado para transferir páginas dos servidores para os navegadores (HTTP ?)

REST (Transferência do Estado Representativo) é pretendida como uma imagem do design da aplicação se comportará: uma rede de websites (um estado virtual), onde o usuário progride com uma aplicação selecionando as ligações (transições do estado), tendo como resultado a página seguinte (que representa o estado seguinte da aplicação) que está sendo transferida ao usuário e apresentada para seu uso.


REST afirma que a web já desfrutou de escalabilidade como resultado de uma série de desenhos fundamentais:
Um protocolo cliente/servidor sem estado: cada mensagem HTTP contém toda a informação necessária para compreender o pedido. Como resultado, nem o cliente e nem o servidor necessitam gravar nenhum estado das comunicações entre mensagens. Na prática, muitas aplicações baseadas em HTTP utilizam cookies e outros mecanismos para manter o estado da sessão (algumas destas práticas, como a reescrita de URLs, não são permitidas pela regra do REST).
Um conjunto de operações bem definidas que se aplicam a todos os recursos de informação: HTTP em si define um pequeno conjunto de operações, as mais importantes são POST, GET, PUT e DELETE. Com frequência estas operações são combinadas com operações CRUD para a persistência de dados, onde POST não se encaixa exatamente neste esquema.
Uma sintaxe universal para identificar os recursos. No sistema REST, cada recurso é unicamente direcionado através da sua URI.
O uso de hipermídia, tanto para a informação da aplicação como para as transições de estado da aplicação: a representação deste estado em um sistema REST são tipicamente HTML ou XML. Como resultado disto, é possível navegar com um recurso REST a muitos outros, simplesmente seguindo ligações sem requerer o uso de registros ou outra infraestrutura adicional.

---

REST afirma que a web já desfrutou de escalabilidade como resultado de uma série de desenhos fundamentais:
Um protocolo cliente/servidor sem estado: cada mensagem HTTP contém toda a informação necessária para compreender o pedido. Como resultado, nem o cliente e nem o servidor necessitam gravar nenhum estado das comunicações entre mensagens. Na prática, muitas aplicações baseadas em HTTP utilizam cookies e outros mecanismos para manter o estado da sessão (algumas destas práticas, como a reescrita de URLs, não são permitidas pela regra do REST).
Um conjunto de operações bem definidas que se aplicam a todos os recursos de informação: HTTP em si define um pequeno conjunto de operações, as mais importantes são POST, GET, PUT e DELETE. Com frequência estas operações são combinadas com operações CRUD para a persistência de dados, onde POST não se encaixa exatamente neste esquema.
Uma sintaxe universal para identificar os recursos. No sistema REST, cada recurso é unicamente direcionado através da sua URI.
O uso de hipermídia, tanto para a informação da aplicação como para as transições de estado da aplicação: a representação deste estado em um sistema REST são tipicamente HTML ou XML. Como resultado disto, é possível navegar com um recurso REST a muitos outros, simplesmente seguindo ligações sem requerer o uso de registros ou outra infraestrutura adicional.

* Em sistemas REST, os recursos são manipulados através da troca de representações do recurso.

Método GET.

Utilizado para retornar informação de acordo com a URI informada.
Não deve uma mudança de estado
Fica no cache.

Método POST

Utilizado para adicionar uma nova inforamação

Métodp PUT
• Utilize PUT para alterar uma informação
• Controle total na entidade utilizada quando o ID ou chave primária é conhecido

Método DELETE
Remove (logicamente) uma entidade

---
Serviços baseados em REST são muito fáceis de entender e de se trabalhar, pois o cliente que vai utilizar o serviço REST não precisa utilizar nenhuma API especializada, ele utiliza apenas HTTP padrão =), podemos usar nosso browser para testes e experimentos.
URI é uma maneira uniforme de identificar recursos e o HTTP é o meio utilizado para manipular estes recursos.
Fácil consumir e desenvolver com linguagens de scripting..

HATEOAS


