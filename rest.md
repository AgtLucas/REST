## Introdução

Em 1990, a web começou a ganhar força, e as pessoas começaram a perceber uma maneira de fazer negocios na web, surgindo assim, a necessidade de algum meio de se realizar transações pela internet. Surgiu então um novo paradigma; como evoluir a web, sair de uma web de páginas, para uma web de serviços?

A partir desse "problema", em 1998, algumas empresas entre elas a Microsoft, criaram um padrão chamado XML-RPC. Esse padrão evoluiu com o passar do tempo, após algumas funcionalidades que foram adicionadas. Graças a essa evolução, o XML-RPC serviu como base para outro padrão, o SOAP.

SOAP (Simple Object Access Protocol) é um padrão baseado em ações, que nada mais é do que uma abstração para chamadas de métodos, no geral um serviço SOAP possui um único endereço de acesso e várias ações. Essas ações podem ocorrer sobre vários protocolos, tais como, SMTP e HTTP, tendo como grande benefício o controle fim a fim da mensagem.

O SOAP, quando utilizado com o protocolo HTTP, utiliza somente o verbo `POST` para transmissão das informações, um verbo que não pode ser utilizado com cache, uma vez que a especificiação HTTP define que apenas o verbo `GET` pode ser utilzado desta maneira. O uso do `POST` ocorre até mesmo para consulta de recursos somente leitura, cenário que poderia ser beneficiado pelo uso do cache. Apesar desta limitação, não podemos nos esquecer que o SOAP foi projetado para ser utilizado com vários protocolos diferentes e ele não pode tirar vantagem de características específicas à um ou outro protocolo.

#### Surgimento do REST

Com o passar do tempo, uma outra linha de pensamento começou a surgir. Ela era composta por pessoas com diferentes perspectivas de interoperabilidade, que não ia de encontro com os cenários empresarias muito bem atendidos pelo SOAP, motivando o surgimento do REST.

O termo REST nasceu na tese de doutorado do __Roy Fielding__, um dos criadores do protocolo HTTP. Em sua tese, ele escreveu sobre o sucesso da internet, do www e do próprio protocolo, descrevendo o funcionamento da internet como sendo um __Estado Representacional de Transferência__, em inglês __RE__PRESENTATIONAL __S__TATE __T__RANSFER, ou seja, REST, considerado como um estilo arquitetural, com um conjunto de restrições, e não uma especificação. 

Para Roy Fielding;

> "REST é pretendida como uma imagem do design da aplicação se comportará: uma rede de websites (um estado virtual), onde o usuário progride com uma aplicação selecionando as ligações (transições do estado), tendo como resultado a página seguinte (que representa o estado seguinte da aplicação) que está sendo transferida ao usuário e apresentada para seu uso."

Os serviços que seguem o estilo arquitetural REST, são conhecidos como serviços RESTful, e se baseiam no funcionamento da web e do protocolo HTTP. Este funcionamento utiliza a estrutura de recursos, que pode ser definido como qualquer coisa importante o suficiente para ser referenciada ou utilizada por um sistema, algo que pode ser armazenado no computador ou representado como uma sequência de bits. Por exemplo, um arquivo de áudio, uma linha em uma tabela de um banco de dados ou o retorno de um algoritmo, podendo ser um objeto físico, como um livro, ou um conceito abstrato, como uma emoção. 

Serviços baseados em REST são muito fáceis de entender e de se trabalhar, pois o cliente que vai utilizar o serviço REST não precisa utilizar nenhuma API especializada, ele utiliza apenas HTTP padrão, podemos usar nosso browser para testes e experimentos.

A exposição do endereço do serviço na rede é feita através de uma URI (Uniform Resource Indicator). A URI pode ser considerada uma das tecnologias fundamentais da web.

#### Funcionamento do REST

O funcionmaneto da "web de serviços", é baseado no mesmo princípio da "web de páginas". Ou seja, os serviços devem ser simples e abertos, permitindo que qualquer pessoa, em qualquer lugar, utilizando qualquer plataforma, seja capaz de utilizá-los. Devem ser baseados em um protocolo universal, que para web podemos considerar o HTTP, um protocolo aberto e amplamente conhecido. Os serviços devem também, expor recursos que possam ser associados através de URIs, característica que faz parte das raízes do funcionamento da web e, por uma questão de escala, devem ser apresentados através de uma comunicação sem estado e sempre que possível utilizar algum tipo de cache pelos mecanismos já existentes na infra da web.

As chamadas às URIs, são realizadas através de verbos HTTP. O verbo utilizado na requisição indica para o serviço que ação deve ser realizada com o recurso, os verbos principais são: `GET`, `POST`, `PUT`, `DELETE`.

* GET: Indica que o cliente quer obeter uma representação de somente leitura do recurso
* POST: Utilizado para criar um novo recurso
* PUT: Utilizado para atualizar um recurso existente
* DELETE: Como o próprio nome sugere, é utilizado para excluir um recurso existente

### Características

* __Arquitetura Cliente / Servidor__: Como a arquitetura cliente/servidor naturalmente leva à definição de uma interface, a aplicação cliente independe de plataforma e é possível a evolução das duas partes, cliente e servidor, desde que a interface permaneça a mesma. Tal arquitetura também permite a simplificação dos componentes do servidor. Respectivamente, obtemos maior portabilidade, extensibilidade e escalabilidade;

* __Sem estado__: Cada requisição do cliente para o servidor "se basta", ou seja, contém toda a informação necessária para ser atendida pelo servidor. Sem precisar guardar nenhuma informação de estado, o servidor fica mais escalável por ser mais simples e não precisar gerenciar os estados de vários clientes. Além disso, o sistema fica mais confiável, visto que facilita a recuperação de falhas;

* __Cacheamento__: Permitindo que o cache seja mantido no cliente, podemos eliminar interações com requisições equivalentes, permitindo que o servidor fique mais livre e, portanto, o sistema fica mais escalável. Além é claro, do aumento na performance, claramente percebida pelo usuário;

* __Interface Uniforme__: São os verbos, as operações que podem ser aplicadas aos recursos, No modelo REST a interface bem definida permite maior extensibilidade do sistema;

* __Camadas__: Adicionar camadas entre cliente e servidor permite escalabilidade, uma vez que esses intermediários permitem balanceamento de carga. Além disso, os intermediários podem manter caches, melhorando a performance geral da aplicação, e implementar políticas de segurança, melhorando a confiabilidade;

* __Código sob demanda__: As funcionalidades do cliente podem ser aumentadas por envio de código sob demanda, que pode vir na forma de scripts, para serem executados. Com isso, são os componentes do cliente que podem ser simplificados e melhorar a extensibilidade. Porém, isso reduz a visibilidade, ou seja, monitorar as ações no sistema fica mais díficil

---

#### Formato de representação de recursos

Pelo fato do REST ser um estilo arquitetural e não uma especificação, não existe uma padronização sobre o formato das informações trocadas entre os clientes e os serviços, logo, faz se o uso dos formatos utilizados na web, alguns deles:

* JSON (JavaScript Object Notation): é um formato baseado em texto bastante simples porém poderoso. Apesar do seu nome, esse formato vem sendo usado em várias linguagens de programação, e não somente com JavaScript. O seu principal benefício é a economia da banda de comunicação entre o cliente e o serviço.
* XML: Formato amplamente conhecido, existindo bibliotecas para processamento de XML para várias plataformas.
* RSS/Atom: O `Really Simple Syndication` e o `Atom Syndication Format` são representações XML utilizadas para publicação de feeds. O Atom é um formato mais recente e vem ganhando cada vez mais espaço.



