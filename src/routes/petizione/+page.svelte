<script context="module">
    import { petition_path } from '../store';
    import Home from "../../components/btn_home.svelte";
    import Title from "../../components/title.svelte";
    import My_card from "./card.svelte";
    import "@material/typography/mdc-typography.scss";

    petition_path.set("./petizione");
    let home_path = "../home";
</script>

<Home {home_path}/>

<Title {home_path}/>

<main data-sveltekit-prefetch>

    <My_card />

    <img src="/images/petition.svg" alt="La terra nelle tue mani" class="img-container">

</main>

<style>
    .img-container{
        padding-top: 15px;
        display: block;
        width: 100%;
        height: 450px;
        object-fit: cover;
    }

    @media screen and (min-width: 601px){
        .img-container{
            content: url("/images/petition_large.svg");
            height: 600px;
        }
    }

    @media screen and (min-width: 1160px){
        .img-container{
            height: 800px;
        }
    }

    @media screen and (min-width: 1440px){
        .img-container{
            height: 900px;
        }
    }
</style>