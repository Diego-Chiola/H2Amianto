<script>
    /*Component for pages amianto-acqua, amianto-aria and amianto-terra*/

    import Card, { Content, Actions } from '@smui/card';
    import Button, { Label } from '@smui/button';

    export let card_param = {
        icon_source: "",
        icon_alt: "",
        title: "",
        text: "",
        action_href: ""
    };
</script>

<div>
    <Card variant="raised" class="card-style">
        <Content class="mdc-typography--body2 card-content">
            <div class="content-header">
                <img src="/images/{card_param["icon_source"]}" alt="{card_param["icon_alt"]}" class="icon-style">
                <h2 class="mdc-typography--subtitle1">{card_param["title"]}</h2>
            </div>
            <p class="text">
                {card_param["text"]}
            </p>
        </Content>
        <Actions>
            <Button href="{card_param["action_href"]}" touch="true" class="read-more">
                <Label class="mdc-typography--button">scopri di più</Label>
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

    .icon-style{
        width: 24px;
        height: 20px;
    }

    * :global(.read-more){
        text-decoration: none;
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
        
        .text{
            text-align: center;
        }
    }
</style>