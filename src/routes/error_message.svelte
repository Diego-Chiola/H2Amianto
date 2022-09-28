<script>
    import { page } from '$app/stores';
    import Card, { Content, Actions } from '@smui/card';
    import Button, { Label } from '@smui/button';

    function checkError(page_status){
        page_status = page_status + "";
        let error_type = page_status[0];
        let error_code = 0;
        switch (error_type){
            case "4":
                return error_code = 404;
            case "5":
                return error_code = 500;
            default:
            return error_code;
        }
    }

</script>

<div class="card-container">
    <Card class="card-style">
        <Content class="mdc-typography--subtitle1 card-content">
            {#if checkError($page.status) === 404}
            <div class="content-header">
                <h2 class="mdc-typography--headline5">{$page.status}: {$page.error.message}</h2>

                <h2 class="mdc-typography--headline5">Ops!<br>La pagina non è stata trovata!</h2>
            </div>
            <p class="text">
                Non siamo riusciti a trovare quello che stavi cercando... può essere che tu sia arrivato troppo tardi.   
                <br><br>
                Non essere triste, puoi sempre riprovare!
            </p>         
            {:else if checkError($page.status) === 500}
            <div class="content-header">
                <h2 class="mdc-typography--headline5">{$page.status}: {$page.error.message}</h2>

                <h2 class="mdc-typography--headline5">Ops!<br>Sembra che il server non risponda!</h2>
            </div>
            <p class="text">
                Si è verificato un problema interno al server... è probabile che sia temporaneamente fuori uso.   
                <br><br>
                Non essere triste, puoi sempre riprovare più tardi!
            </p>
            {:else}
            <div class="content-header">
                <h2 class="mdc-typography--headline5">{$page.status}: {$page.error.message}</h2>

                <h2 class="mdc-typography--headline5">Ops!<br>Si è verificato un problema!</h2>
            </div>
            <p class="text">
                Per un errore di qualche tipo sei finito su questa pagina... sicuramente non è nulla di grave.   
                <br><br>
                Non essere triste, puoi sempre riprovare!
            </p>
            {/if}
        </Content>
        <Actions class="action">
            <Button href="./home" touch="true" class="read-more">
                <Label class="mdc-typography--button">torna alla home</Label>
            </Button>
        </Actions>
    </Card>
</div>

<style>

    .card-container{
        padding-top: 45vh;
    }

    * :global(.card-style){
        background-color: unset;
        box-shadow: none;
        width: 90%;
        max-width: 350px;
        margin: 0 auto 0 0;
    }

    * :global(.card-content){
        max-width: 90%;
        padding: 18px 24px 0px 24px;
    }

    .content-header{
        text-align: left;
    }

    h2{
        color: var(--text-color);
        margin-top: 0;
        margin-bottom: 15px;
    }

    * :global(.action){
        padding-top: 0;
        padding-bottom: 0;
        padding-left: 10px;
    }   

    * :global(.read-more){
        margin-right: auto;
        margin-left: 6px;
    }

    .text{
        color: rgba(255, 255, 255, 0.6);
        line-height: 20px;
        margin-bottom: 0;
    }

    @media screen and (min-width: 421px){
        .card-container{
            padding-top: 35vh;
        }
    }

    @media screen and (min-width: 600px){
        .card-container{
            padding-top: 50vh;
        }

        * :global(.card-style){
            max-width: 400px;
            margin: 0 0 0 auto;
            margin-bottom: 50px;
        }
    }

    @media screen and (min-width: 960px){
        .card-container{
            padding-top: 50vh;
        }

        * :global(.card-style){
            max-width: 460px;
            margin: 0 100px 0 auto;
            margin-bottom: 50px;
        }

        .content-header{
            text-align: left;
        }

        .text{
            margin-bottom: 50px;
            margin-top: 50px;
        }
    }

    @media screen and (min-width: 1440px){
        .card-container{
            padding-top: 60vh;
        }
    }
</style>