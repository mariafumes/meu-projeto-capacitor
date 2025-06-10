<script>
    let s = $state(0);
    let min = $state(0);
    let h = $state(0);

    function segundos(){
        min = s/60;
        h = s/3600;
    }

    function minutos(){
        s = min * 60;
        h = min/60;
    }

    function horas(){
        s = h * 3600;
        min = h * 60;
    }
</script>
<style>
    .container {
      background-color: #e9cf9c;
      padding: 30px;
      border-radius: 10px;
      text-align: center;

      max-width: 620px;
      margin-top: 10%;
      font-family: initial;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      margin: 100px auto;
 }

 h1 {
    color: #c58608;
      text-align: center;
      margin-bottom: 20px;
      font-family: initial;

 }

 .button {
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
    background-color: #c58608;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    transition: transform 0.2s, background-color 0.3s ease;
  }

  </style>
<div class="container">
<h1>CONVERSOR DE TEMPO</h1>
<p>SEGUNDOS(s): <input type="number" bind:value={s} onclick = {segundos} /></p>
<p>MINUTOS(min): <input type="number" bind:value={min} onclick = {minutos} /></p>
<p>HORAS(h): <input type="number" bind:value={h} onclick = {horas} /></p>
</div>
<div class="button">
  <a href="/">
      <button class="styled-button5">VOLTAR</button>
    </a>
    </div>
