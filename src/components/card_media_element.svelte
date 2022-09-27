<script>
    import Card, { Content, PrimaryAction, Media} from '@smui/card';
    import Button, { Label } from '@smui/button';

    export let media_cards = {
        first_media_card: {
            icon_source: "",
            icon_alt: "",
            title: "",
            action_href: "",
            media_url: "",
            text: ""
        },
        second_media_card: {
            icon_source: "",
            icon_alt: "",
            title: "",
            action_href: "",
            media_url: "",
            text: ""
        }
    }
</script>

<div class="card-container">
    <Card variant="raised" class="card-style">
        <div class="content-header">
            <img src="/images/{media_cards.first_media_card["icon_source"]}" alt="{media_cards.first_media_card["icon_alt"]}" class="icon-style">
            <h2 class="mdc-typography--headline5">{media_cards.first_media_card["title"]}</h2>
        </div>
        <PrimaryAction on:click={() => console.log("ciao")} class="primary-action">
            <Media class="card-media-16x9" aspectRatio="16x9" style="background-image: url({media_cards.first_media_card["media_url"]})">
                <Content touch="true" class="mdc-typography--body1">
                    <p class="text">
                        {media_cards.first_media_card["text"]}
                    </p>
                    <Button href="http://www.nonsoloaria.com/asbdi.htm" touch="true" class="read-more">
                        <Label class="mdc-typography--button">scopri di più</Label>
                    </Button>
                </Content>
            </Media>
        </PrimaryAction>
    </Card>

    <Card variant="raised" class="card-style">
        <div class="content-header">
            <img src="/images/{media_cards.second_media_card["icon_source"]}" alt="{media_cards.second_media_card["icon_alt"]}" class="icon-style">
            <h2 class="mdc-typography--headline5">{media_cards.second_media_card["title"]}</h2>
        </div>
        <PrimaryAction on:click={() => console.log("ciao")} class="primary-action">
            <Media class="card-media-16x9" aspectRatio="16x9" style="background-image: url({media_cards.second_media_card["media_url"]})">
                <Content touch="true" class="mdc-typography--body1">
                    <p class="text">
                        {media_cards.second_media_card["text"]}
                    </p>
                    <Button touch="true" class="read-more">
                        <Label class="mdc-typography--button">scopri di più</Label>
                    </Button>
                </Content>
            </Media>
        </PrimaryAction>
    </Card>
</div>

<style>
    .card-container{
        display: none;
        flex-direction: row;
        justify-content: center;
        margin-bottom: 50px;
    }

    * :global(.card-style){
        background-color: var(--eleveted-color);
        width: 500px;
        height: 360px;
        margin: 100px auto 0 auto;
        margin-bottom: 50px;
    }

    .content-header{
        display: flex;
        flex-direction: row;
        height: 72px;
    }

    h2{
        color: var(--text-color);
        margin-top: 24px;
    }

    .icon-style{
        width: 24px;
        height: 20px;
        margin: 30px 27px 0px 25px;
    }

    * :global(.primary-action){
        overflow: visible;
    }

    * :global(.card-media-16x9){
        height: 194px;
    }

    * :global(.card-media-16x9)::before{
        margin-top: 33%;
    }

    * :global(.read-more){
        margin-left: auto;
    }

    .text{
        color: rgba(255, 255, 255, 0.6);
        margin-bottom: 7px;
    } 

    @media screen and (min-width: 1160px){

        .card-container{
            display: flex;
        }

        * :global(.card-style){
            width: 540px;
            height: 360px;
        }    
    }

    @media screen and (min-width: 1440px){
        * :global(.card-style){
            width: 640px;
            height: 360px;
        }

        * :global(.card-media-16x9)::before{
            margin-top: 27.5%;
        }
    }
</style>