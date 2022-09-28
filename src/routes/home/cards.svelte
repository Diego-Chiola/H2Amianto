<script>
    import Card, { Content, Actions } from '@smui/card';
    import Button, { Label } from '@smui/button';
    import { onMount } from 'svelte';

    const read_more = ["", "", ""];
    const resize_margin = ["", ""];
    const read_more_label = [false, false, false];
    
    function resize_manage(){
        if(window.matchMedia("screen and (max-width: 1200px) and (min-width: 1160px), (min-width: 1366px)").matches){
            resize_margin[0] = "20px";
            resize_margin[1] = "20px";
        } else if(window.matchMedia("screen and (max-width: 1365px) and (min-width: 1201px)").matches){
            resize_margin[0] = "20px";
            resize_margin[1] = "40px";
        }
        else{
            resize_margin[0] = "0px";
            resize_margin[1] = "0px";      
        }
    }

    onMount(() => {
        resize_manage();
    })

    function read_more_show(clicked_read_more){
        switch (clicked_read_more){
            case 0:
                read_more[0] = (read_more[0] === "") ? "read-more-show" : "";
                read_more_label[0] = !read_more_label[0];    
                break;
            case 1:
                read_more[1] = (read_more[1] === "") ? "read-more-show" : "";
                read_more_label[1] = !read_more_label[1];  
                break;
            default:
                read_more[2] = (read_more[2] === "") ? "read-more-show" : "";
                read_more_label[2] = !read_more_label[2];      
        }
    }
</script>

<svelte:window on:resize={resize_manage}/>

<div class="card-container">
    <Card variant="raised" class="card-style">
        <Content class="mdc-typography--body2 card-content">
            <h2 class="mdc-typography--subtitle1">Che cos’è l’amianto?</h2>
            <p class="text">
                È un materiale costituito da fibre minerali naturali appartenenti
                ai silicati e alle serie mineralogiche del serpentino (crisotilo o
                amianto bianco) e degli anfiboli (crocidolite o amianto blu).
                <span class="text read-more-hidden {read_more[0]}">
                    Ha trovato un vasto impiego come isolante o coibente e come materiale di rinforzo e supporto per altri manufatti sintetici.
                    L’amianto di solito si ritrova in forma compatta, inglobato in una matrice cementizia (cementoamianto in copertura, canne fumarie ecc.)
                    o in altre matrici (pavimenti in linoleum, pareti, pannelli ecc.), ma è possibile trovarlo anche in forma friabile, più pericolosa, nel
                    caso di utilizzo come insonorizzante o isolante sui controsoffitti e/o sulle pareti.
                    <br>
                    <a href="https://www.issalute.it/index.php/la-salute-dalla-a-alla-z-menu/a/amianto#esposizione-all-amianto">Leggi tutto l'articolo</a>
                </span>
            </p>
        </Content>
        <Actions class="btn-container">
            <Button on:click={() => read_more_show(0)} variant="raised" touch="true" class="mdc-elevation--z2 read-more">
                {#if read_more_label[0]}
                <Label class="mdc-typography--button">nascondi</Label>
                {:else}
                <Label class="mdc-typography--button">leggi di più</Label>
                {/if}
            </Button>
        </Actions>
    </Card>

    <Card variant="raised" class="card-style">
        <Content class="mdc-typography--body2 card-content">
            <h2 class="mdc-typography--subtitle1">Ambiente e salute</h2>
            <p class="text">
                La presenza delle fibre di amianto nell’ambiente comporta
                inevitabilmente dei danni a carico della salute, anche in
                presenza di pochi elementi fibrosi.
                <span class="text read-more-hidden {read_more[1]}">
                    Le fibre presenti nell’aria, una volta inalate, si possono depositare
                    all’interno delle vie aeree e sulle cellule polmonari rimanendoci per
                    diversi anni, anche per tutta la vita e questo può comportare l’insorgenza
                    di malattie come l’asbestosi, il mesotelioma e il tumore dei polmoni.
                    <br>
                    <a href="https://www.salute.gov.it/imgs/C_17_opuscoliPoster_283_ulterioriallegati_ulterioreallegato_9_alleg.pdf">Leggi tutto l'articolo</a>
                </span>
            </p>
        </Content>
        <Actions class="btn-container" style="margin-top:{resize_margin[0]}">
            <Button on:click={() => read_more_show(1)} variant="raised" touch="true" class="mdc-elevation--z2 read-more">
                {#if read_more_label[1]}
                <Label class="mdc-typography--button">nascondi</Label>
                {:else}
                <Label class="mdc-typography--button">leggi di più</Label>
                {/if}
            </Button>
        </Actions>
    </Card>

    <Card variant="raised" class="card-style">
        <Content class="mdc-typography--body2 card-content">
            <h2 class="mdc-typography--subtitle1">Amianto in Italia</h2>
            <p class="text">
                “A trent’anni dalla messa al bando in Italia della fibra
                minerale cancerogena, uno dei più pericolosi inquinanti,
                cosa è stato fatto?”
            </p>
            <span class="text read-more-hidden {read_more[2]}">   
                Per aver respirato le sue fibre, disperse dentro e fuori le abitazioni, scuole, ospedali,
                nei luoghi di lavoro, in Europa muoiono ogni anno almeno 80mila persone.
                In Italia, tra il 2010 e il 2016, sono stati 4.410 decessi all’anno, secondo quanto
                elaborato dall'Istituto superiore di sanità (Iss), attribuibili all’esposizione da amianto.
                Secondo i dati storici raccolti da Inail nel registro nazionale sui mesoteliomi (Renam) sono stati diagnosticati
                tra il 1993 e il 2018, ben 31.572 casi. Il 56,7% dei quali è concentrato in Lombardia (6653), Piemonte (5084),
                Liguria (3263) ed Emilia-Romagna (2873).
                <br>
                <a href="https://www.wired.it/article/amianto-bonifica-italia-eternit-dati-malati-mesotelioma/?fbclid=IwAR1PTv46uqoWLM6BJ-oTbnTnjT3TQC2GO85nrF5KnY6GxElEy6C3fm796hY">Leggi tutto l'articolo</a>
            </span>
        </Content>
        <Actions class="btn-container" style="margin-top:{resize_margin[1]}">
            <Button on:click={() => read_more_show(2)} variant="raised" touch="true" class="mdc-elevation--z2 read-more">
                {#if read_more_label[2]}
                <Label class="mdc-typography--button">nascondi</Label>
                {:else}
                <Label class="mdc-typography--button">leggi di più</Label>
                {/if}
            </Button>
        </Actions>
    </Card>
</div>

<style>

    .card-container{
        display: flex;
        flex-direction: column;
        width: 100%;
        margin: 20px auto 0 auto;
        align-items: center;
        align-content: center;
    }

    * :global(.card-style){
        position: relative;
        background-color: var(--eleveted-color);
        width: 80%;
        max-width: 350px;
        margin-bottom: 50px;
    }

    * :global(.card-content){
        max-width: 90%;
        padding: 20px 24px 13px 24px;
    }

    * :global(.btn-container){
        position: unset;
    }

    .read-more-hidden{
        display: block;
        line-height: 0;
        overflow: hidden;
        max-height: 0;
        transition: max-height 0.6s linear;
    }

    .read-more-show{
        max-height: 20rem;
    }

    * :global(.read-more){
        border-radius: 28px;
        margin: 0 auto 20px auto;
        padding: 20px 15px 20px 15px;
        transition: all 0.5s;
    }

    h2{
        color: var(--text-color);
        margin-top: 0;
    }

    .text{
        color: rgba(255, 255, 255, 0.6);
        line-height: 20px;
        margin-bottom: 0;
    }

    @media screen and (min-width: 601px){
        * :global(.card-style){
            max-width: 500px;
        }   
    }

    @media screen and (min-width: 1160px){

        .card-container{
            flex-direction: row;
            align-items: flex-start;
            max-width: 95%;
            justify-content: center;
            margin-bottom: 50px;
        }

        * :global(.card-style){
            max-width: 350px;
            min-height: 250px;
            margin: 0 20px 0 20px;
        }

        /*.read-more-hidden{
            min-height: 0;
            transition: min-height 0.6s linear;
        }

        .read-more-show{
            max-height: 0;
            min-height: 20rem;
        }*/
    }

    @media screen and (min-width: 1366px){
        * :global(.card-style){
            max-width: 400px;
            min-height: 250px;
        } 
    }

</style>