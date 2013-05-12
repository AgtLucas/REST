REST (Representational State Transfer, ou Transferência de Estado Representativo) é uma técnica de engenharia de software. O termo surgiu em uma tese de doutorado sobre web escrita por Roy Fielding.

## Roy Fielding

* Ajudou a escrever os primeiros servidores web;
* Fez pesquisas explicando porque a web funciona como ela funciona; :+1:
* O nome dele está na especificação do protocolo usado para transferir páginas dos servidores para os navegadores (HTTP ?)

REST afirma que a web já desfrutou de escalabilidade como resultado de uma série de desenhos fundamentais:
Um protocolo cliente/servidor sem estado: cada mensagem HTTP contém toda a informação necessária para compreender o pedido. Como resultado, nem o cliente e nem o servidor necessitam gravar nenhum estado das comunicações entre mensagens. Na prática, muitas aplicações baseadas em HTTP utilizam cookies e outros mecanismos para manter o estado da sessão (algumas destas práticas, como a reescrita de URLs, não são permitidas pela regra do REST).
Um conjunto de operações bem definidas que se aplicam a todos os recursos de informação: HTTP em si define um pequeno conjunto de operações, as mais importantes são POST, GET, PUT e DELETE. Com frequência estas operações são combinadas com operações CRUD para a persistência de dados, onde POST não se encaixa exatamente neste esquema.
Uma sintaxe universal para identificar os recursos. No sistema REST, cada recurso é unicamente direcionado através da sua URI.
O uso de hipermídia, tanto para a informação da aplicação como para as transições de estado da aplicação: a representação deste estado em um sistema REST são tipicamente HTML ou XML. Como resultado disto, é possível navegar com um recurso REST a muitos outros, simplesmente seguindo ligações sem requerer o uso de registros ou outra infraestrutura adicional.
