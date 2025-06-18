<script>
    import { dicionario } from '$lib/dicionario';
    import { goto } from '$app/navigation';

    let palavra = $state('');
    let filtradas = $state(dicionario);

    function buscar() {
        if (palavra === '') {
            filtradas = dicionario;
            return;
        }
        filtradas = dicionario.filter(termo =>
            termo.palavra.toLowerCase().startsWith(palavra.toLowerCase())
        );
    }

    function aleatorio() {
        const index = Math.floor(Math.random() * dicionario.length);
        palavra = dicionario[index].palavra;
        goto(`/dicionario/${palavra}`);
    }
</script>

<div class="container my-4">
    <div class="row mb-3">
        <div class="col-md-8">
            <input 
                type="text" 
                class="form-control" 
                placeholder="Digite uma palavra" 
                oninput={buscar} 
                bind:value={palavra}
            />
        </div>
        <div class="col-md-4">
            <button 
                type="button" 
                class="btn btn-info w-100" 
                onclick={aleatorio}>
                Palavra aleatória
            </button>
        </div>
    </div>

    <ul class="list-group">
        {#each filtradas as termo}
            <li class="list-group-item">
                <a href={`/dicionario/${termo.palavra}`} class="text-decoration-none">
                    {termo?.palavra}
                </a>
            </li>
        {/each}
    </ul>
</div>


