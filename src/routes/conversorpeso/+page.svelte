<script>
    let mg = $state(0);
    let g = $state(0);
    let kg = $state(0);
    let t = $state(0);

    function miligrama(){
        g = mg/1000;
        kg = mg/1000000;
        t = mg/1000000000;
    }

    function grama(){
        mg = g * 1000;
        kg = g/1000;
        t = g/1000000;
    }

    function kilograma(){
        mg = kg * 1000000;
        g = kg * 1000;
        t= kg/1000;
    }

    function tonelada(){
        mg = t * 1000000000;
        g = t * 1000000;
        kg = t * 1000;
    }
</script>
<style>
    .container {
      background-color: #ffcbdb;
      padding: 30px;
      border-radius: 10px;
      text-align: center;
      max-width: 620px;
      margin-top: 10%;
      font-family: initial;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
 }

 h1 {
    color: #a3425f;
      text-align: center;
      margin-bottom: 20px;
      font-family: initial;

 }

 .button-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 20vh;
      padding: 20px;
      box-sizing: border-box;
    }

    .styled-button5 {
    width: 260px;
    max-width: 100%;
    padding: 16px;
    margin: 12px 0;
    font-size: 18px;
    color: white;
    background-color: #a3425f;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    transition: transform 0.2s, background-color 0.3s ease;
    }

  </style>
  <center>
<div class="container">
<h1>CONVERSOR DE MASSA</h1>
    <p>MILIGRAMAS(mg): <input type="number" bind:value={mg} onclick = {miligrama} /></p>
    <p>GRAMAS(g): <input type="number" bind:value={g} onclick = {grama} /></p>
    <p>QUILOGRAMAS(kg): <input type="number" bind:value={kg} onclick = {kilograma} /></p>
    <p>TONELADAS(t): <input type="number" bind:value={t} onclick = {tonelada} /></p>
</div>
<div class="button-container">
<a href="/">
    <button class="styled-button5">VOLTAR</button>
  </a>
</div>
</center>