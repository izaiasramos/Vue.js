<template>
    <br/><br/>
    <h1>Testando criando rotas:</h1>
    <ul>
        <li>1º crio um arquivo dentro de <strong>componentes</strong> com <strong>template</strong>, posso ter também um <strong>script, style</strong></li>
        <li>no script exporto meu arquivo para importar no App.vue export default { name: 'testStructure' }</li>
        <li>3º no App.vue no template crio um tag com o nome do meu arquivo, importo, exporto para mandar para o arquivo html que renderizará,</li>
        
    </ul>
</template>

<script>
export default{
   name: 'testStructure',
   props:{
    msg: String
   } 
}
</script>