<script>
    import Card, { Content, Actions } from '@smui/card';
    import Button, { Label } from '@smui/button';
</script>

<div class="card-container">
    <Card variant="raised" style="background-color: var(--eleveted-color);">
        <Content class="mdc-typography--body1 card-content">
            <h2 class="mdc-typography--headline5">Che cos’è l’amianto?</h2>
            <p>
                È un materiale costituito da fibre minerali naturali appartenenti
                ai silicati e alle serie mineralogiche del serpentino (crisotilo o
                amianto bianco) e degli anfiboli (crocidolite o amianto blu).
            </p>
        </Content>
        <Actions>
            <Button variant="raised" touch="true" class="read-more">
                <Label class="mdc-typography--button">leggi di più</Label>
            </Button>
        </Actions>
    </Card>
</div>

<style>
    .card-container{
        display: flex;
        flex-direction: column;
        width: 100vw;
        justify-content: center;
        margin: 20px auto 0 auto;
        max-width: 90%;
    }

    * :global(.card-content){
        margin: 0px 24px 0px 24px;
        width: 100%;
    }

    * :global(.read-more){
        border-radius: 28px;
    }
</style>