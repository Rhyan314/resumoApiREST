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

O protocolo HTTP define um conjunto de métodos de requisição responsáveis por indicar a ação a ser executada para um dado recurso. Cada verbo possui um significado específico e está associado a uma operação particular.

- **GET:** Solicita a representação de um recurso.
- **HEAD:** Similar ao GET, mas usado para obter apenas os cabeçalhos da resposta, sem o corpo da mensagem.
- **POST:** Envia dados para serem processados ​​a um recurso específico para criar um novo recurso.
- **PUT:** Atualiza um recurso ou cria um novo recurso se ele não existir.
- **DELETE:** Remove um recurso específico.
- **CONNECT:** Estabelece um túnel para o servidor identificado pelo recurso de destino.
- **OPTIONS:** Retorna os métodos HTTP suportados no recurso especificado, geralmente usado para informar ao cliente sobre as opções disponíveis.
- **TRACE:** Executa um teste de chamada loop-back junto com o caminho para o recurso de destino.
- **PATCH:** Atualiza parcialmente um recurso.

## HTTP Status Code

Os códigos de status de resposta HTTP indicam se uma solicitação HTTP específica foi concluída com êxito. As respostas são agrupadas em cinco classes:

- **Informativo**: Indica que a requisição foi recebida e o processo está em andamento.
- **Sucesso**: Significa que a ação foi recebida, compreendida e aceita com sucesso.
- **Redirecionamento**: Implica que uma ação adicional é necessária para completar a requisição.
- **Erro do Cliente**: Ocorre quando a requisição contém sintaxe incorreta ou não pode ser atendida.
- **Erro do Servidor**: Surge quando o servidor falha em atender uma requisição aparentemente válida.

Segue então uma lista de alguns de Códigos:

1. **Rspostas Informativas**
   - `100 Continue` Indica que o cliente deve continuar a solicitação ou ignorar a resposta se a solicitação já tiver sido concluída.
   - `101 Switching Protocols` É enviado em resposta a um Upgradecabeçalho de solicitação do cliente e indica o protocolo para o qual o servidor está mudando.
   - `102 Processing` Indica que o servidor recebeu e está processando a solicitação, mas ainda não há resposta disponível.
   - `Early Hints` Usado com o Linkcabeçalho, permitindo que o agente do usuário comece a pré-carregar recursos enquanto o servidor prepara uma resposta ou se pré-conecta a uma origem da qual a página precisará de recursos.

2. **Respostas de Sucesso**
   - `200 OK` A solicitação foi bem-sucedida. O significado do resultado de "sucesso" depende do método HTTP
   - `201 Created` A solicitação foi bem-sucedida e, como resultado, um novo recurso foi criado.
   - `202 Accepted` A solicitação foi recebida, mas ainda não foi atendida.
   - `203 Non-authoritative Information` Essa Resposta significa que os metadados retornados não são exatamente os mesmos que estão disponíveis no servidor de origem, mas são coletados de uma cópia local ou de terceiros.
   - `204 No Content` Não há conteúdo a ser enviado para esta solicitação, mas os cabeçalhos podem ser úteis.
   - `205 Reset Content` Diz ao agente do usuário para redefinir o documento que enviou esta solicitação.
   - `206 Partial Content` Este código de resposta é usado quando o Rangecabeçalho é enviado do cliente para solicitar apenas parte de um recurso.
   - `207 Multi-Status` Transmite informações sobre vários recursos, para situações em que vários códigos de status podem ser apropriados.

3. **Mensagens de Redirecionamento**
   - `300 Multiple Choices` A solicitação tem mais de uma resposta possível. O agente ou usuário do usuário deve escolher um deles.
   - `301 Moved Permanently` A URL do recurso solicitado foi alterada permanentemente. A nova URL é fornecida na resposta.
   - `302 Found` Este código de resposta significa que o URI do recurso solicitado foi alterado temporariamente .
   - `303 See Other` O servidor enviou esta resposta para direcionar o cliente para obter o recurso solicitado em outro URI com uma solicitação GET.
   - `304 Not Modified`: Isso é usado para fins de cache. Ele informa ao cliente que a resposta não foi modificada, para que o cliente possa continuar a usar a mesma versão em cache da resposta.
   - `307 Temporary Redirect` O servidor envia esta resposta para direcionar o cliente a obter o recurso solicitado em outro URI com o mesmo método usado na solicitação anterior.
   - `308 Permanent Redirect` Isso significa que o recurso agora está permanentemente localizado em outro URI, especificado pelo Location:cabeçalho HTTP Response.

4. **Respostas de Erro do Cliente**
   - `400 Bad Request` O servidor não pode ou não irá processar a solicitação devido a algo que é percebido como um erro do cliente
   - `401 Unauthorized` O cliente deve se autenticar para obter a resposta solicitada.
   - `402 Payment Required`: Usado muito raramente e não existe nenhuma convenção padrão.
   - `403 Forbidden` O cliente não possui direitos de acesso ao conteúdo; isto é, não é autorizado, portanto o servidor se recusa a fornecer o recurso solicitado.
   - `404 Not Found` O servidor não consegue encontrar o recurso solicitado. No navegador, isso significa que o URL não é reconhecido. Em uma API, isso também pode significar que o endpoint é válido, mas o recurso em si não existe.
   - `405 Method Not Allowed` O método de solicitação é conhecido pelo servidor, mas não é suportado pelo recurso de destino. 
   - `406 Not Acceptable` Esta resposta é enviada quando o servidor web, após realizar a negociação de conteúdo orientada pelo servidor , não encontra nenhum conteúdo que esteja em conformidade com os critérios fornecidos pelo agente do usuário.
   - `407 Proxy Authentication Required` Isso é semelhante, 401 Unauthorizedmas a autenticação precisa ser feita por um proxy.
   - `408 Request Timeout` Esta resposta é enviada em conexão ociosa por alguns servidores, mesmo sem nenhuma solicitação prévia do cliente. Isso significa que o servidor gostaria de encerrar esta conexão não utilizada.
   - `409 Conflict` Esta resposta é enviada quando uma solicitação entra em conflito com o estado atual do servidor.
   - `410 Gone` Esta resposta é enviada quando o conteúdo solicitado foi excluído permanentemente do servidor, sem endereço de encaminhamento. Espera-se que os clientes removam seus caches e links para o recurso.
   - `411 Length Required` O servidor rejeitou a solicitação porque o Content-Lengthcampo do cabeçalho não está definido e o servidor exige isso.
   - `412 Precondition Failed` O cliente indicou pré-condições em seus cabeçalhos que o servidor não atende.
   - `413 Payload Too Large` A entidade solicitada é maior que os limites definidos pelo servidor. O servidor pode fechar a conexão ou retornar um Retry-Aftercampo de cabeçalho.
   - `414 Request-URI Too Long` O URI solicitado pelo cliente é mais longo do que o servidor deseja interpretar.
   - `415 Unsupported Media Type` O formato de mídia dos dados solicitados não é suportado pelo servidor, portanto o servidor está rejeitando a solicitação.
   - `416 Requested Range Not Satisfiable` O intervalo especificado pelo Rangecampo de cabeçalho na solicitação não pode ser atendido. É possível que o intervalo esteja fora do tamanho dos dados do URI de destino.
   - `417 Expectation Failed` Este código de resposta significa que a expectativa indicada pelo Expectcampo do cabeçalho da solicitação não pode ser atendida pelo servidor.

5. **Respostas de Erro do Servidor**
   - `500 Internal Server Error` O servidor encontrou uma situação que não sabe como lidar.
   - `501 Not Implemented` O método de solicitação não é suportado pelo servidor e não pode ser manipulado. 
   - `502 Bad Gateway` Essa resposta de erro significa que o servidor, enquanto trabalhava como gateway para obter a resposta necessária para tratar a solicitação, obteve uma resposta inválida.
   - `503 Service Unavailable` O servidor não está pronto para lidar com a solicitação. As causas comuns são um servidor que está fora do ar para manutenção ou sobrecarregado. Observe que junto com esta resposta deverá ser enviada uma página amigável explicando o problema. 
   - `504 Gateway Timeout` Esta resposta de erro é dada quando o servidor está agindo como um gateway e não consegue obter uma resposta a tempo.
   - `505 HTTP Version Not Supported` A versão HTTP usada na solicitação não é suportada pelo servidor.


Autor do resumo: Rhyan Carlos Da Silva Lima - 4MB - 01539352

