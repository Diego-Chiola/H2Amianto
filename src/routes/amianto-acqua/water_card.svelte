<script>
    import Card, { Content, Actions } from '@smui/card';
    import Button, { Label } from '@smui/button';
</script>

<div>
    <Card variant="raised" class="card-style">
        <Content class="mdc-typography--body2 card-content">
            <div class="content-header">
                <img src="/images/water_icon.svg" alt="air" class="air-icon">
                <h2 class="mdc-typography--subtitle1">Amianto nell'Acqua</h2>
            </div>
            <p class="text">
                ...o essere ingerite se sciolte nell’acqua.
            </p>
        </Content>
        <Actions>
            <Button touch="true" class="read-more">
                <Label class="mdc-typography--button">scopri di più</Label>
            </Button>
        </Actions>
    </Card>
</div>

<style>
    * :global(.card-style){
        position: relative;
        background-color: var(--eleveted-color);
        width: 80%;
        max-width: 350px;
        margin: 14px auto 0 auto;
        margin-bottom: 50px;
    }

    * :global(.card-content){
        max-width: 90%;
        padding: 18px 24px 13px 24px;
    }

    .content-header{
        text-align: center;
    }

    h2{
        color: var(--text-color);
        margin-top: 0;
        margin-bottom: 15px;
    }

    .air-icon{
        width: 24px;
        height: 20px;
    }

    * :global(.read-more){
        margin-left: auto;
    }

    .text{
        color: rgba(255, 255, 255, 0.6);
        line-height: 20px;
        margin-bottom: 0;
    } 
</style>