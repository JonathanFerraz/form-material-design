# Material Design form input

#Instalação: Inclua o script após a biblioteca jQuery:

``` html
<script src="/caminho/jquery.material.form.min.js"></script>
```

Inclua o estilo:

``` html
<link rel="stylesheet" type="text/css" href="caminho/jquery.material.form.min.css">
```

##Modo de Usar:
``` html
<form action="" class="material">
 <input type="text" name="name" placeholder="Name">
 <!-- Este label é necessário caso queira uma mensagem de erro -->
 <label id="name-error" class="error" for="name"></label>
 <input id="cpf" type="text" name="cpf" placeholder="CPF">
 <!-- Este label é necessário caso queira uma mensagem de erro -->
 <label id="name-error" class="error" for="cpf"></label>
 <input type="email" name="email" placeholder="E-mail" required>
 <!-- Este label é necessário caso queira uma mensagem de erro -->
 <label id="email-error" class="error" for="email"></label>
 <textarea name="message" placeholder="Message"></textarea>
 <input type="radio" name="gender" value="true" placeholder="Primeira opção">
 <input type="checkbox" name="check[]" value="1" placeholder="Opção 1">
</form>
```

##Para usar o estilo insira em seu arquivo principal JS
``` javascript
$('form .material').materialForm();
```

##Para usar a validação utilizei a biblioteca jQuery validation http://jqueryvalidation.org/

Forma de usar: 

``` javascript
$('form').validate({
rules: {
name: {
 required: true,
 minlength: 3,
 letters: true,
 number: false,
},
cpf: {
 required: true,
 minlength: 14,
},
email: {
 required: true,
 email: true
}
},
messages: {
name: "Precisamos do seu nome completo",
cpf: "Precisamos de um CPF válido",
email: "Precisamos de um email válido"
},
});
```

Utilizando máscara nos campos: 
```javascript
$('#cpf').mask('000.000.000-00')
```

##Ripple effect no botão

Para ativar o efeito, é necessário adicionar a classe "ripple" ao seu button. Para personalizar a cor do ripple adicione o atributo data-ripple-color="#cor-desejada"

```html
<button class="material-btn-raised ripple" data-ripple-color="#fff"> Enviar </button>
```