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

Usuários podem fazer login de duas formas: verificando se uma conta já existe ou não, e cadastrando uma nova conta. Para que uma conta seja tida como existente e o login seja verificado, o usuário precisa ter todas as informações de seus atributos no banco de dados, mas somente serão utilizadas o e-mail e senha para a verificação imediata. Caso o login não seja possível, o usuário poderá cadastrar uma conta

Um post pode ser criado, apresentado e/ou deletado. Quando um post é criado, seus atributos são salvos no banco de dados; quando é apresentado, ele se relaciona com o view na página de oportunidades e aparece para os usuários; e quanto é deletado, seus atributos são deletados do banco de dados e ele não é mostrado na página de oportunidades.

### Views (Views):
- Tela de login - mostra os campos de formulário necessários para o cadastro ou verificação da existência de uma conta.
- Tela de oportunidades (publicações) - Permite que o usuário veja vagas de voluntariado ou publique uma nova vaga independente.
- Tela de perfil - mostra o perfil do usuário já logado e permite a modificação de atributos.

### Infraestrutura:

- Descreva os componentes de infraestrutura do seu projeto, como bancos de dados, APIs externas e outras dependências.
- Explique como a infraestrutura se integra à arquitetura MVC.


### Justifique as escolhas feitas e como elas impactam o projeto.
#### Implicações da Arquitetura:
Descreva as implicações da arquitetura em termos de escalabilidade, manutenção, testabilidade e outros aspectos importantes.
