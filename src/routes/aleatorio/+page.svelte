<script>
    let n = 1;
    let numeroAleatorio1 = "";
    let numeroAleatorio2 = "";
    let numeroAleatorio3 = "";
    let mensagem = "";
    let incluirMinusculas = false;
    let incluirMaiusculas = false;
    let incluirSimbolos = false;
    let incluirNumeros = true;

    function gerarNumeroAleatorio() {
        let caracteres = "";
        if (incluirNumeros) {
            caracteres += "0123456789";
        }
        if (incluirMinusculas) {
            caracteres += "abcdefghijklmnopqrstuvwxyz";
        }
        if (incluirMaiusculas) {
            caracteres += "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
        }
        if (incluirSimbolos) {
            caracteres += "!@#$%^&*()_+-=[]{}|;:,.<>?";
        }

        if (caracteres === "") {
            mensagem = "SELECIONE PELO MENOS UMA OPÇÃO!";
            return;
        }

        numeroAleatorio1 = gerarSenha(caracteres);
        numeroAleatorio2 = gerarSenha(caracteres);
        numeroAleatorio3 = gerarSenha(caracteres);

        mensagem = "SENHAS GERADAS COM SUCESSO!";
    }

    function gerarSenha(caracteres) {
        let senha = "";
        for (let i = 0; i < n; i++) {
            senha += caracteres.charAt(Math.floor(Math.random() * caracteres.length));
        }
        return senha;
    }

    function copiarSenha(senha) {
        navigator.clipboard.writeText(senha)
            .then(() => {
                mensagem = "SENHA COPIADA PARA A ÁREA DE TRANSFERÊNCIA!";
            })
            .catch(() => {
                mensagem = "Erro ao copiar a senha.";
            });
    }
</script>

<style>
    .container {
        background-color: aliceblue;
        padding: 30px;
        border-radius: 10px;
        text-align: center;
        max-width: 620px;
        margin-top: 5%;
        font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    }

    h2 {
        color: #CCA9DD;
        font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    }

    button {
        margin-top: 10px;
    }

    p {
        font-size: 1.1em;
    }

    .message {
        margin-top: 10px;
        font-weight: bold;
        color: #CCA9DD; 
    }

    .error-message {
        margin-top: 10px;
        font-weight: bold;
        color: #CCA9DD; 
    }

    input[type="range"] {
        width: 80%;
        margin: 20px 0;
        color: #CCA9DD;
    }

    .checkbox-group {
        text-align: left;
        margin: 15px 0;
        color: #CCA9DD;
    }

    .checkbox-group label {
        display: block;
        margin: 5px 0;
    }

    .checkbox1 {
        accent-color: #CCA9DD;
    }

    
    .styled-button5 {
    width: 260px;
    max-width: 100%;
    padding: 16px;
    margin: 12px 0;
    font-size: 18px;
    color: white;
    background-color: #7584dc;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    transition: transform 0.2s, background-color 0.3s ease;
    }
</style>
<center>
<div class="container">
    <h2>GERADOR DE SENHA ALEATÓRIA</h2>
    <p style="color:#B19CD9">DIGITE OU ESCOLHA A QUANTIDADE DE DÍGITOS PARA A SENHA:</p>
    
    <input type="range" min="1" max="30" bind:value={n} style="accent-color: #8584db;"/>
    <p style="color:#B19CD9"><strong>{n}</strong> CARACTERES</p>
    
    <div class="checkbox-group">
        <label><input type="checkbox" bind:checked={incluirNumeros} class="checkbox1"/> INCLUIR NÚMEROS</label>
        <label><input type="checkbox" bind:checked={incluirMinusculas} class="checkbox1"/> INCLUIR LETRAS MINÚSCULAS</label>
        <label><input type="checkbox" bind:checked={incluirMaiusculas} class="checkbox1"/> INCLUIR LETRAS MAIÚSCULAS</label>
        <label><input type="checkbox" bind:checked={incluirSimbolos} class="checkbox1"/> INCLUIR SÍMBOLOS</label>
    </div>

    <button type="button" on:click={gerarNumeroAleatorio}>GERAR SENHAS</button>

    {#if numeroAleatorio1 && numeroAleatorio2 && numeroAleatorio3}
        <p style="color:#CCA9DD"><strong>SENHA 1:</strong> {numeroAleatorio1}</p>
        <button type="button"  on:click={() => copiarSenha(numeroAleatorio1)}>COPIAR SENHA 1</button>
        
        <p style="color:#CCA9DD"><strong>SENHA 2:</strong> {numeroAleatorio2}</p>
        <button type="button" on:click={() => copiarSenha(numeroAleatorio2)}>COPIAR SENHA 2</button>
        
        <p style="color:#CCA9DD"><strong>SENHA 3:</strong> {numeroAleatorio3}</p>
        <button type="button" on:click={() => copiarSenha(numeroAleatorio3)}>COPIAR SENHA 3</button>
    {/if}

    {#if mensagem}
        <p class={numeroAleatorio1 || numeroAleatorio2 || numeroAleatorio3 ? 'message' : 'error-message'}>{mensagem}</p>
    {/if}
</div>
<div class="button-container">
    <a href="/">
       <button class="styled-button5">VOLTAR</button>
     </a>
    </div>
</center>

