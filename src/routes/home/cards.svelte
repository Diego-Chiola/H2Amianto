<script>
    import Card, { Content, Actions } from '@smui/card';
    import Button, { Label } from '@smui/button';

    let read_more1 = "";
    let read_more2 = "";
    let read_more3 = "";

    function read_more_show(read_more){
        switch (read_more){
            case 1:
                if(read_more1 === "")
                    read_more1 = "read-more-show";
                else
                    read_more1 = "";
                break;
            case 2:
                if(read_more2 === "")
                    read_more2 = "read-more-show";
                else
                    read_more2 = "";
                break;
            default:
                if(read_more3 === "")
                    read_more3 = "read-more-show";
                else
                    read_more3 = "";
        }
    }
</script>

<div class="card-container">
    <Card variant="raised" class="card-style">
        <Content class="mdc-typography--body2 card-content">
            <h2 class="mdc-typography--subtitle1">Che cos’è l’amianto?</h2>
            <p class="text">
                È un materiale costituito da fibre minerali naturali appartenenti
                ai silicati e alle serie mineralogiche del serpentino (crisotilo o
                amianto bianco) e degli anfiboli (crocidolite o amianto blu).
                <span class="text read-more-hidden {read_more1}">
                    Ha trovato un vasto impiego come isolante o coibente e come materiale di rinforzo e supporto per altri manufatti sintetici.
                    L’amianto di solito si ritrova in forma compatta, inglobato in una matrice cementizia (cementoamianto in copertura, canne fumarie ecc.)
                    o in altre matrici (pavimenti in linoleum, pareti, pannelli ecc.), ma è possibile trovarlo anche in forma friabile, più pericolosa, nel
                    caso di utilizzo come insonorizzante o isolante sui controsoffitti e/o sulle pareti.
                </span>
            </p>
        </Content>
        <Actions>
            <Button on:click={() => read_more_show(1)} variant="raised" touch="true" class="mdc-elevation--z2 read-more">
                <Label class="mdc-typography--button">leggi di più</Label>
            </Button>
        </Actions>
    </Card>

    <Card variant="raised" class="card-style">
        <Content class="mdc-typography--body2 card-content">
            <h2 class="mdc-typography--subtitle1">Ambiente e salute</h2>
            <p class="text">
                La presenza delle fibre di amianto nell’ambiente comporta
                inevitabilmente dei danni a carico della salute, anche in
                presenzadi pochi elementi fibrosi.
                <span class="text read-more-hidden {read_more2}">
                    Le fibre presenti nell’aria, una volta inalate, si possono depositare
                    all’interno delle vie aeree e sulle cellule polmonari rimanendoci per
                    diversi anni, anche per tutta la vita e questo può comportare l’insorgenza
                    di malattie come l’asbestosi, il mesotelioma e il tumore dei polmoni.
                </span>
            </p>
        </Content>
        <Actions>
            <Button on:click={() => read_more_show(2)} variant="raised" touch="true" class="mdc-elevation--z2 read-more">
                <Label class="mdc-typography--button">leggi di più</Label>
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
            <span class="text read-more-hidden {read_more3}">   
                Per aver respirato le sue fibre, disperse dentro e fuori le abitazioni, scuole, ospedali,
                nei luoghi di lavoro, in Europa muoiono ogni anno almeno 80mila persone.
                In Italia, tra il 2010 e il 2016, sono stati 4.410 decessi all’anno, secondo quanto
                elaborato dall'Istituto superiore di sanità (Iss), attribuibili all’esposizione da amianto.
                Secondo i dati storici raccolti da Inail nel registro nazionale sui mesoteliomi (Renam) sono stati diagnosticati
                tra il 1993 e il 2018, ben 31.572 casi. Il 56,7% dei quali è concentrato in Lombardia (6653), Piemonte (5084),
                Liguria (3263) ed Emilia-Romagna (2873).
            </span>
        </Content>
        <Actions>
            <Button on:click={() => read_more_show(3)} variant="raised" touch="true" class="mdc-elevation--z2 read-more">
                <Label class="mdc-typography--button">leggi di più</Label>
            </Button>
        </Actions>
    </Card>
</div>

<style>
    .card-container{
        display: flex;
        flex-direction: column;
        width: 100%;
        align-items: center;
        align-content: center;
        margin: 20px auto 0 auto;
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

    * :global(.card-style){
        position: relative;
        background-color: var(--eleveted-color);
        width: 80%;
        margin-bottom: 50px;
    }

    * :global(.card-content){
        max-width: 90%;
        padding: 20px 24px 13px 24px;
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
            width: 500px;
        }   
    }
</style>