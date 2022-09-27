<script type="ts">

    import "@material/typography/mdc-typography.scss";
    import Earth from './earth.svelte';
    import Cards from './cards.svelte';
    import '@material/elevation/mdc-elevation.scss';
    import Title from "../components/title.svelte";
    import Button from '@smui/button';

</script>

<Title />

<main data-sveltekit-prefetch>

<Earth />

<Cards />

</main>

<div class="btn-container">
    <Button on:click={() => scrollTo(0, 0)} variant="raised" class="mdc-elevation--z2 btn-backup" style="border-radius: 50%; height: 64px; width: 48px">
        <img src="/images/vector_backup.png" alt="torna su">
    </Button>
</div>

<style>

    .btn-container{
        width: 64px;
        margin: 20px 15px 15px auto;
    }

    * :global(.btn-backup){
        display: block;
        background-color: var(--primary-color);
        border-radius: 50%;
    }

    @media screen and (min-width: 1160px){
        .btn-container{
            display: none;
        }
    }

</style>
