<script>
   let m = $state(0);
   let km = $state(0);
   let mm = $state(0);
   let cm = $state(0);

   function metros(){
    cm = m * 100;
    mm = m * 1000;
    km = m/1000;
   }

   function centimetros(){
    m = cm/100;
    mm = cm * 10;
    km = cm/100000;
   }

   function milimetros(){
    m = mm/1000;
    km = mm/1000000;
    cm = mm/10;
   }

   function quilometros(){
    m = km * 1000
    cm = km * 100000;
    mm= km * 1000000;
   }
</script>

<style>
   .container {
        background-color: rgb(186, 240, 161);
        padding: 30px;
        border-radius: 10px;
        text-align: center;
        max-width: 620px;
        margin-top: 10%;
        font-family: initial;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
   }

   h1 {
      color: #41792b;
        text-align: center;
        margin-bottom: 20px;
        font-family: initial;

   }

   .button-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .styled-button5 {
    width: 260px;
    max-width: 100%;
    padding: 16px;
    margin: 12px 0;
    font-size: 18px;
    color: white;
    background-color: #41792b;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    transition: transform 0.2s, background-color 0.3s ease;
    }



</style>
<center>
<div class="container">
<h1>CONVERSOR DE DISTÂNCIA</h1>
    <p>MILÍMETROS(mm): <input type="number" bind:value={mm} onclick = {milimetros} /></p>
    <p>CENTÍMETROS(cm): <input type="number" bind:value={cm} onclick = {centimetros} /></p>
    <p>METROS(m): <input type="number" bind:value={m} onclick = {metros} /></p>
    <p>QUILÔMETROS(km): <input type="number" bind:value={km} onclick = {quilometros} /></p>
   </div>


   <div class="button-container">
   <a href="/">
      <button class="styled-button5">VOLTAR</button>
    </a>
   </div>
</center>