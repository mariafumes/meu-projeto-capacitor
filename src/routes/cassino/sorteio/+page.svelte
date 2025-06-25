<script> 
let n = 60; 
let quantidade = 6;
let sorteados = [];

function sortear(){
    sorteados=[];
    for (let j= 0; j < quantidade; j++){
        let numero = Math.trunc(Math.random()*n);

        sorteados.push(numero);
    }
}
</script>
<style>
     .styled-button5 {
    width: 260px;
    max-width: 100%;
    padding: 16px;
    margin: 12px 0;
    font-size: 18px;
    color: white;
    background-color: #797d93;
    border: none;
    border-radius: 20px;
    cursor: pointer;
    transition: transform 0.2s, background-color 0.3s ease;

    }

</style>
<div class="container text-center mt-5">
    <h3>Sorteando números para Mega-Sena</h3>
    <br/>
    <button class="styled-button5" onclick={sortear}><h1>🎰</h1></button>
    <br/>
    <br/>
    <h5>Os números sorteados são:</h5>
    <br/>
    <h3>{sorteados}</h3>
</div>