REST (Representational State Transfer, ou Transferência de Estado Representativo) é uma técnica de engenharia de software. O termo surgiu em uma tese de doutorado sobre web escrita por Roy Fielding.

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


