<script>
    import Title from "../../components/title.svelte";
    import My_card from "./card.svelte";
    import "@material/typography/mdc-typography.scss";
</script>

<Title />

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