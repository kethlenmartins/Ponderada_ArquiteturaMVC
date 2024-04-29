# Ponderada de programação
## Arquitetura MVC

<div align="center">

<img src="mvcSails.png" width="100%">

</div>

- Nome do Projeto: Oportuniza
- Descrição: O Oportuniza é será uma aplicação web que visa à integração entre voluntários e organizações sociais, de modo que a cultura do voluntariado seja propagada. Ainda, o Oportuniza dá a oportunidade ao voluntário de tomar as rédeas do processo de aplicação e interagir com outros usuários, criando uma verdadeira comunidade.
- Arquitetura: MVC (Model-View-Controller)
- Ferramenta de Diagramação: draw.io

### Modelos (Models):
As entidades presentes no projeto são os Users (usuários), as preferências e as postagens (Post).

Usuários possuem atributos ID, nome, e-mail, senha, idade, local, gênero, pontos e customização, sendo todos modificáveis, com exceção do ID e gênero, o qual só podem ser deletados com a deleção da conta. Além disso, usuários podem criar posts (1-n) e colocar preferências em seus perfis (1-n).

Os posts possuem atributos ID, título, conteúdo, anexos e User ID, sendo o último a sua chave estrangeira que o relaciona com o usuário que criou o post.

As preferências possuem atributos User ID, descrição, interesses e carga horários, sendo o primeiro a chave estrangeira que as relacionam com o usuário que as escolheu e todas as outras, modificáveis.

### Controladores (Controllers):
- Liste os controladores do seu projeto e suas responsabilidades.
- Descreva as ações (methods) de cada controlador e seus parâmetros de entrada e saída.
- Explique como os controladores interagem com os modelos e views.

Usuários podem fazer login de duas formas: verificando se uma conta já existe ou não, e cadastrando uma nova conta. Para que uma conta seja tida como existente e o login seja verificado, o usuário precisa ter todas as informações de seus atributos no banco de dados - mas somente serão utilizadas o e-mail e senha para a verificação imediata - e receber o aviso verde no campo que preencher. Caso o login não seja possível, uma mensagem aparecerá na tela e o usuário poderá cadastrar uma conta.

Um post pode ser criado, apresentado e/ou deletado. Quando um post é criado, seus atributos são salvos no banco de dados; quando é apresentado, ele se relaciona com o view na página de oportunidades e aparece para os usuários; e quanto é deletado, seus atributos são deletados do banco de dados e ele não é mostrado na página de oportunidades.

Um perfil pode ser apresentado ou atualizado e tais ações só podem ser feitas por usuários. Quando apresentado, o perfil é mostrado na tela principal do dispositivo, e quando é modificado, o usuário consegue atualizar os atributos armazenados no banco de dados, os quais irão aparecer atualizados também na tela do dispositivo.

### Views (Views):
- Tela de login - mostra os campos de formulário necessários para o cadastro ou verificação da existência de uma conta.
- Tela de oportunidades (publicações) - Permite que o usuário veja vagas de voluntariado ou publique uma nova vaga independente.
- Tela de perfil - mostra o perfil do usuário já logado e permite a modificação de atributos.

### Infraestrutura:
O projeto utilizará bancos de dados para armazenamento e atualização dos atributos de cada um dos models, bem como API externas como a API que permite o login diretamente com o Google, e se integrará tanto com o banco de dados quanto com o controller de login.


### Justifique as escolhas feitas e como elas impactam o projeto.
#### Implicações da Arquitetura:

A escolha de fazer um único tipo de usuário recorre à facilidade de utilizar um único tipo de banco de dados, sendo necessário algo adicional para demonstrar no view que usuários específicos fazem parte de ONGs em vez de utilizar mais um banco de dados. Além disso, a utilização de poucas telas e outras em pop-up, como as de criação de posts e atualização de perfil, permite manutenção mais rápida das telas principais e maior escalabilidade pela simplicidade quantitativa de elementos que devem ser trabalhados. Além disso, os atributos que serão salvos e farão a conexão entre model e banco de dados foram pedidos pela organização parceira.
