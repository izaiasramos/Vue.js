<<<<<<< HEAD
README: Aplicação de Lista de Comentários com Vue.js
Este projeto é uma aplicação simples de lista de comentários feita com Vue.js. Abaixo, você encontrará uma explicação detalhada sobre o código, incluindo funcionalidades, problemas resolvidos e como cada recurso foi implementado.

📝 Descrição do Projeto
A aplicação permite que os usuários:

Adicionem comentários com nome e mensagem.
Visualizem uma lista de comentários adicionados.
Excluam comentários individualmente.
🚀 Tecnologias Usadas
Vue.js: Framework JavaScript progressivo para construir interfaces de usuário.
Bootstrap 4.3.1: Para estilização básica.
📂 Estrutura do Código
HTML e Bootstrap: Estrutura e estilização básica da página.
Vue.js: Lógica reativa que gerencia os dados e interações do usuário.
Principais Seções do Código
1. Montando o Vue.js no HTML
No Vue.js, usamos a propriedade el para associar a aplicação a um elemento HTML:


el: '#app'
O Vue controla tudo dentro do elemento com o ID app.

2. Template do Vue
O template contém o HTML dinâmico gerenciado pelo Vue. A sintaxe do Vue (como v-model e v-for) é usada aqui para criar a interface reativa.

🔍 Funcionalidades Detalhadas e Soluções
1. Adicionar um Comentário
Problema: Precisamos capturar o nome e a mensagem do usuário e adicioná-los à lista de comentários.
Solução:
O campo de entrada (input) e a área de texto (textarea) usam a diretiva v-model para criar um binding bidirecional. Isso significa que os valores digitados pelo usuário são automaticamente atualizados no estado do Vue.


<input placeholder="nome" type="text" v-model="name" />
<textarea placeholder="Comentário" v-model="message"></textarea>

O botão "Comentar" chama o método addComment quando clicado, graças à diretiva v-on:click:

<button v-on:click="addComment">Comentar</button>

No método addComment, os valores name e message são validados e adicionados ao array comments:


addComment() {
    if (this.name.trim() === '' || this.message.trim() === '') {
        return;
    }
    this.comments.push({ name: this.name, message: this.message });
    this.name = ''; // Limpa o campo
    this.message = ''; // Limpa o campo
}

2. Exibir Comentários
Problema: Precisamos exibir uma lista de comentários armazenados no array comments.

Solução:
Usamos a diretiva v-for para iterar sobre o array comments e renderizar cada comentário na tela:


<div class="list-group-item" v-for="(comment, index) in comments">
    <span>Autor: <strong>{{ comment.name }}</strong></span>
    <p>{{ comment.message }}</p>
</div>
Cada comentário é exibido com o nome e a mensagem associados.
3. Excluir Comentários
Problema: Permitir a exclusão de comentários específicos da lista.
Solução:
Adicionamos um link "Excluir" a cada comentário. Esse link chama o método removeComment quando clicado, graças à diretiva v-on:click.prevent:


<a v-on:click.prevent="removeComment(index)" href="#">Excluir</a>
O modificador .prevent evita o comportamento padrão do link.
No método removeComment, usamos splice para remover o comentário do array comments com base no índice:
javascript
Copiar código
removeComment(index) {
    this.comments.splice(index, 1);
}

📋 Fluxo da Aplicação
O usuário digita o nome e o comentário nos campos.
Ao clicar em "Comentar":
O método addComment valida os dados e adiciona o comentário à lista.
A lista de comentários é atualizada automaticamente.
Para excluir um comentário, o usuário clica no link "Excluir", que chama o método removeComment.

🔧 Principais Diretivas Usadas
Diretiva	Função
v-model	Cria um binding bidirecional entre campos do formulário e propriedades do Vue.
v-on	Adiciona listeners de eventos do DOM, como cliques, para chamar métodos.
v-for	Itera sobre listas para renderizar elementos dinamicamente.
v-bind	Permite vincular atributos HTML (não usado explicitamente aqui, mas útil para vincular classes e IDs).
=======
README: Aplicação de Lista de Comentários com Vue.js
Este projeto é uma aplicação simples de lista de comentários feita com Vue.js. Abaixo, você encontrará uma explicação detalhada sobre o código, incluindo funcionalidades, problemas resolvidos e como cada recurso foi implementado.

📝 Descrição do Projeto
A aplicação permite que os usuários:

Adicionem comentários com nome e mensagem.
Visualizem uma lista de comentários adicionados.
Excluam comentários individualmente.
🚀 Tecnologias Usadas
Vue.js: Framework JavaScript progressivo para construir interfaces de usuário.
Bootstrap 4.3.1: Para estilização básica.
📂 Estrutura do Código
HTML e Bootstrap: Estrutura e estilização básica da página.
Vue.js: Lógica reativa que gerencia os dados e interações do usuário.
Principais Seções do Código
1. Montando o Vue.js no HTML
No Vue.js, usamos a propriedade el para associar a aplicação a um elemento HTML:


el: '#app'
O Vue controla tudo dentro do elemento com o ID app.

2. Template do Vue
O template contém o HTML dinâmico gerenciado pelo Vue. A sintaxe do Vue (como v-model e v-for) é usada aqui para criar a interface reativa.

🔍 Funcionalidades Detalhadas e Soluções
1. Adicionar um Comentário
Problema: Precisamos capturar o nome e a mensagem do usuário e adicioná-los à lista de comentários.
Solução:
O campo de entrada (input) e a área de texto (textarea) usam a diretiva v-model para criar um binding bidirecional. Isso significa que os valores digitados pelo usuário são automaticamente atualizados no estado do Vue.


<input placeholder="nome" type="text" v-model="name" />
<textarea placeholder="Comentário" v-model="message"></textarea>

O botão "Comentar" chama o método addComment quando clicado, graças à diretiva v-on:click:

<button v-on:click="addComment">Comentar</button>

No método addComment, os valores name e message são validados e adicionados ao array comments:


addComment() {
    if (this.name.trim() === '' || this.message.trim() === '') {
        return;
    }
    this.comments.push({ name: this.name, message: this.message });
    this.name = ''; // Limpa o campo
    this.message = ''; // Limpa o campo
}

2. Exibir Comentários
Problema: Precisamos exibir uma lista de comentários armazenados no array comments.

Solução:
Usamos a diretiva v-for para iterar sobre o array comments e renderizar cada comentário na tela:


<div class="list-group-item" v-for="(comment, index) in comments">
    <span>Autor: <strong>{{ comment.name }}</strong></span>
    <p>{{ comment.message }}</p>
</div>
Cada comentário é exibido com o nome e a mensagem associados.
3. Excluir Comentários
Problema: Permitir a exclusão de comentários específicos da lista.
Solução:
Adicionamos um link "Excluir" a cada comentário. Esse link chama o método removeComment quando clicado, graças à diretiva v-on:click.prevent:


<a v-on:click.prevent="removeComment(index)" href="#">Excluir</a>
O modificador .prevent evita o comportamento padrão do link.
No método removeComment, usamos splice para remover o comentário do array comments com base no índice:
javascript
Copiar código
removeComment(index) {
    this.comments.splice(index, 1);
}

📋 Fluxo da Aplicação
O usuário digita o nome e o comentário nos campos.
Ao clicar em "Comentar":
O método addComment valida os dados e adiciona o comentário à lista.
A lista de comentários é atualizada automaticamente.
Para excluir um comentário, o usuário clica no link "Excluir", que chama o método removeComment.

🔧 Principais Diretivas Usadas
Diretiva	Função
v-model	Cria um binding bidirecional entre campos do formulário e propriedades do Vue.
v-on	Adiciona listeners de eventos do DOM, como cliques, para chamar métodos.
v-for	Itera sobre listas para renderizar elementos dinamicamente.
v-bind	Permite vincular atributos HTML (não usado explicitamente aqui, mas útil para vincular classes e IDs).
>>>>>>> 5a00eed82f9233e8940b29094004afc986cdeaea
.prevent	Modificador que impede o comportamento padrão de um evento (como o recarregamento ao clicar em links).