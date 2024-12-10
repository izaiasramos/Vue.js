<template>
    <div class="container">
        <h1>Comentários</h1>
        <hr />
        <div class="form-todo form-group">
        <p>
            <input placeholder="nome" type="text" name="author" 
            class="form-control" v-model="name" />
        </p>
        <p>
            <textarea placeholder="Comentário" name="message"
            class="form-control" v-model="message"></textarea>
        </p>
        <button v-on:click="addComment" type="submit" class="btn btn-primary">Comentar</button>
        </div>
        <div class="list-group">
        <div class="list-group-item" v-for="(comment, index) in allComments" :key="index">
            <span class="comment__author">Autor: <strong>{{comment.name}}</strong></span><!-- sintaxe para quando se quer cuspir um valor {{comments.name}} -->
            <p>{{comment.message}}</p>
            <div>
            <a v-on:click.prevent="removeComment(index)" href="#" title="Excluir">Excluir</a>
            </div>
        </div>
        </div>
        <hr />
    </div>
</template>

<script>    
    export default{ //quando eu exporto assim meu script por deaixo dos panos é feito um new Vue, ée criaddo uma instancia.
        data() { //é um objeto que me retorna objetos, e tudo oque eu inserir aqui estará disponivel para usar no template, ou seja,tudo oqe eu retornar aqui é como se fosse uma variável que poderei usar no template
                return {
                    comments: [],
                    name: '',
                    message: ''
                }
            },
        methods: {
            addComment(){
                // console.log("chamado!");
                // console.log(this.name);
                // console.log(this.message);
                if (this.message.trim() === ''){
                    return;
                }
                this.comments.push({
                    name: this.name,
                    message: this.message
                });

                this.name = '';
                this.message = '';
            },
            removeComment(index){
                // console.log(index);
                this.comments.splice(index, 1);
            }
        },
        computed: {//disponibiliza variáveis/valores para renderizar no template, assim como a propriedade data: {} mas o data é mais voltado para o model e api, já o computed é sobre oque vc quer renderizar na view, com  parte de interface, oque vc quer mostrar de informação
            allComments(){
                return this.comments.map(comment => ({
                    ...comment,
                    name: (comment.name || '').trim() === '' ? 'Anônimo' : comment.name
                }));
            }
        }, 
        watch: {
            comments(val){
                console.log("val", val)
            }
        }
    }    
</script>