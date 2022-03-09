# Angular-Security-XSS
Entenda como funciona a vúlnerabilidade do XSS e como o Angular previne esses ataques.


Como o Angular previne sua aplicação contra ataques XSS?

 1 - Entendendo a Vúlnerabilidade XSS:

  Antes de tudo, precisamos saber o que é uma vulnerabilidade XSS. Uma vulnerabilidade do tipo XSS permite que o atacante injete códigos maliciosos na sua página ou sistema. Com isso, ele pode ( e vai ) comprometer as interações do usuário com sua aplicação. Dessa forma, a vulnerabilidade XSS permite a inserção de códigos JavaScript que retornem dados sensíveis como Cookies e credenciais do usuário. O tipo principal de ataques XSS é o do DOM, onde a vulnerabilidade existe do lado do cliente, ao invés do servidor.

Agora que já sabemos os riscos dessa falha, como podemos explorá-la?

2 - Explorando a vúlnerabilidade XSS:

Para o bom funcionamento de aplicações e sistemas em geral, faz-se necessário o compartilhamento de dados entre componentes, serviços e métodos. Dessa forma, para a dinamicidade da aplicação, muitos dados são exibidos do lado do Cliente (no front). Por outro lado, informações do Cliente também são passadas para a aplicação. Diante disso, como podemos garantir que nada que venha do Cliente afete a aplicação? 

Para responder a essa pergunta devemos criar um cenário hipotético, no qual dados inseridos pelo Cliente são exibidos diretamente na tela. Para mostrar essa informação na tela, é necessário acessar a árvore de elementos DOM ( Document Object Model ). Se tal dado for do tipo string, temos que atribuí-lo a um elemento do nosso ( Uma tag HTML ). Dessa forma, temos que acessar a propriedade innerHTML desse elemento e, por fim, atribuir ao innerHTML do elemento, a informação fornecida pelo Cliente. 

3 - Como o Angular previne essa vúlnerabilidade?

A grande problemática está em atribuir ao innerHTML de um elemento as informações passadas pelo Cliente sem uma verificação. Dessa forma, se tal informação conter um método malicioso, toda a aplicação estará em “xeque”. 

Diante dessa problemática, o Angular disponibiliza métodos nativos que previnem aos ataques do tipo XSS. Além disso, por padrão, o Angular impede que o Cliente insira tags HTML ou métodos JavaScript em inputs. Dessa forma, torna-se mais difícil que uma aplicação Angular esteja vulnerável a ataques do tipo XSS.
