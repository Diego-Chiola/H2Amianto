<script>
    import { petition_path } from './store';
    import "@material/typography/mdc-typography.scss";
    import ErrorMessage from './error_message.svelte';

    petition_path.set("./petizione");
</script>

<main class="img-container">

    <ErrorMessage />

</main>

<style>

    .img-container{
        display: block;
        width: 100%;
        height: 120vh;
        background-image: url("/images/error.svg");
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center;
    }

    @media screen and (min-width: 421px){
        .img-container{
            background-image: url("/images/error_large.svg");
            height: 100vh;
        }
    }

    @media screen and (min-width: 600px){
        .img-container{
            background-image: url("/images/error_medium.svg");
        }
    }

    @media screen and (min-width: 960px){
        .img-container{
            height: 120vh;
            background-image: url("/images/error_large.svg");
        }
    }

    @media screen and (min-width: 1440px){
        .img-container{
            height: 120vh;
        }
    }

</style>