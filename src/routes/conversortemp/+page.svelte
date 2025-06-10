<script>
    let celsius = $state(0);
    let kelvin = $state(0);
    let fahrenheit = $state(0);

    function Celsius() {
		fahrenheit = celsius * 1.8 + 32;
        kelvin = celsius + 273; 
    }

	function Fahrenheit() {
		celsius = ((fahrenheit - 32) * 5) / 9;
        kelvin = (((fahrenheit - 32) * 5)/9) + 273; 
    }

    function Kelvin() {
        celsius = kelvin - 273;
        fahrenheit = ((kelvin - 273) * 1,8) + 32;
    }
    </script>
      <style>
      .container {
        background-color: #ADD8E6;
        padding: 30px;
        border-radius: 10px;
        text-align: center;
        max-width: 620px;
        margin-top: 10%;
        font-family: initial;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
   }

   h1 {
      color: #1a768d;
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
    background-color: #1a768d;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    transition: transform 0.2s, background-color 0.3s ease;
    }

    </style>
    <center>
    <div class="container">
    <h1>CONVERSOR DE TEMPERATURA</h1>
    <p>CELSIUS: <input type="number" bind:value={celsius} onclick = {Celsius} /></p>
    <p>FAHRENHEIT: <input type="number" bind:value={fahrenheit} onclick = {Fahrenheit} /></p>
    <p>KELVIN: <input type="number" bind:value={kelvin} onclick = {Kelvin} /></p>
    </div>
    <div class="button-container">
    <a href="/">
      <button class="styled-button5">VOLTAR</button>
    </a>
    </div>
  </center>
