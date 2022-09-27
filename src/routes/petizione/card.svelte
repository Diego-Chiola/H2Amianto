<script>
    import Card, { Content, Actions } from '@smui/card';
    import Button, { Label } from '@smui/button';
</script>

<div>
    <Card variant="raised" class="card-style">
        <Content class="mdc-typography--body2 card-content">
            <div class="content-header">
                <h2 class="mdc-typography--subtitle1">Firma la petizione</h2>
            </div>
            <p class="text">
                La terra è in pericolo.
                <br>
                Firma la petizione per salvare il pianeta dall’Amianto! Salvando lui, salvi anche te stess*.
            </p>
        </Content>
        <Actions class="action">
            <Button touch="true" class="read-more">
                <Label class="mdc-typography--button">firma qui</Label>
            </Button>
        </Actions>
    </Card>
</div>

<style>
    * :global(.card-style){
        position: relative;
        background-color: var(--eleveted-color);
        width: 90%;
        max-width: 350px;
        margin: 14px auto 0 auto;
        margin-bottom: 50px;
    }

    * :global(.card-content){
        max-width: 90%;
        padding: 18px 24px 0px 24px;
    }

    .content-header{
        text-align: center;
    }

    h2{
        color: var(--text-color);
        margin-top: 0;
        margin-bottom: 15px;
    }

    * :global(.action){
        padding-top: 0;
        padding-bottom: 0;
    }   

    * :global(.read-more){
        margin-left: auto;
    }

    .text{
        color: rgba(255, 255, 255, 0.6);
        line-height: 20px;
        margin-bottom: 0;
    }
    
    @media screen and (min-width: 601px){
        * :global(.card-style){
            max-width: 480px;
        }
    }
</style>