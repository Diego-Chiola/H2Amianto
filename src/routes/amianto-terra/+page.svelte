<script context="module">
    import { petition_path } from '../store';
    import "@material/typography/mdc-typography.scss";
    import Home from "../../components/btn_home.svelte";
    import Title from "../../components/title.svelte";
    import Card_element from "../../components/card_element.svelte";
    import Media_Card_element from "../../components/card_media_element.svelte";

    petition_path.set("../petizione");

    let home_path = "../home";

    let card_param = {
        icon_source: "earth_icon.svg",
        icon_alt: "earth",
        title: "Amianto nel Suolo",
        text: "... possono contaminare il suolo rovinando i nostri paesaggi...",
        action_href: "https://www.ediltecnico.it/84027/contaminazione-suoli-amianto-come-intervenire-in-questi-casi/"
    };

    let media_cards = {
        first_media_card: {
            icon_source: "water_icon.svg",
            icon_alt: "water",
            title: "Amianto nell'Acqua",
            action_href: "https://www.ausl.mo.it/flex/cm/pages/ServeBLOB.php/L/IT/IDPagina/28623",
            media_url: "/images/water_background_large.svg",
            text: "...o essere ingerite se sciolte nell’acqua."
        },
        second_media_card: {
            icon_source: "air_icon.svg",
            icon_alt: "air",
            title: "Amianto nell'Aria",
            action_href: "http://www.nonsoloaria.com/asbdi.htm",
            media_url: "/images/air_background_large.png",
            text: "Le fibre di Amianto possono essere respirate..."
        }
    }
</script>

<Home {home_path}/>

<Title {home_path}/>

<main data-sveltekit-prefetch>

    <Card_element {card_param}/>

    <img src="/images/earth_background.png" alt="suolo" class="img-container">

    <Media_Card_element {media_cards}/>
    
</main>

<style>

    .img-container{
        padding-top: 15px;
        display: block;
        width: 100%;
        height: 600px;
        object-fit: cover;
    }

    @media screen and (min-width: 601px){
        .img-container{
            content: url("/images/earth_background_large.png");
            height: 600px;
        }
    }

    @media screen and (min-width: 1160px){
        .img-container{
            height: 800px;
        }
    }

</style>