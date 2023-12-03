# Api REST e RESTFul

Uma API, é um conjunto de regras que definem como aplicativos ou dispositivos podem se conectar e se comunicar uns com os outros. Uma API de REST segue os princípios de design do REST ou o estilo de arquitetura do Representational State Transfer.  Por esta razão, as APIs de REST são muitas vezes chamadas de APIs de RESTful. 

### Princípios de Design REST

1. ***Interface uniforme:*** Todas as solicitações da API para o mesmo recurso devem ser iguais, independentemente da origem da solicitação. Esses recursos podem ser muito grandes mas devem suprir as necessidades do cliente.

2. ***Desacoplamento do cliente-servidor:*** Os aplicativos cliente e servidor devem ser completamente independentes um do outro. A única informação que o aplicativo cliente deve receber é o URI do recurso solicitado. Ele não pode interagir com o aplicativo do servidor de qualquer outra forma. Da mesma forma, um aplicativo do servidor não deve modificar o aplicativo cliente, exceto para transferi-los aos dados solicitados via HTTP.

3. ***Sem estado definido:*** Cada solicitação precisa incluir todas as informações necessárias para processá-lo. As APIs de REST não requerem nenhuma sessão do lado do servidor. Os aplicativos do servidor não tem permissão para armazenar nenhum dado relacionado a uma solicitação de cliente.

4. ***Capacidade de armazenamento em cache:*** Quando possível, os recursos devem ser armazenados em cache pelo cliente ou servidor. As respostas do servidor também precisam conter informações sobre as permissões de cache do recurso fornecido. 

5. ***Arquitetura de sistema em camadas:*** As chamadas e respostas passam por diferentes camadas. Pode haver uma série de intermediários diferentes no loop de comunicação. As APIs de REST precisam ser projetadas para que nem o cliente e nem o servidor possam dizer se ele se comunica com o aplicativo final ou um intermediário.

6. ***Código sob demanda (opcional):*** As APIs de REST geralmente enviam recursos estáticos, mas em certos casos, as respostas também podem conter código executável (como applets Java). Nestes casos, o código deve ser executado somente sob demanda.

## Diferenças entre REST e RESTFul

REST é um estilo arquitetural que define princípios gerais para projetar serviços web, enquanto RESTful refere-se à aplicação prática desses princípios. Um serviço web RESTful segue as restrições e princípios do REST para criar uma arquitetura robusta e escalável. Portanto, você pode dizer que um serviço é RESTful se ele adere aos princípios do REST.

## HTTP verbs

    Seu texto...

## HTTP Status Code

    Seu texto...

    ---

Autor do resumo: Nome Sobrenome - Matrícula

