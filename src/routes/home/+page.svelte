<script type="ts">

    import "@material/typography/mdc-typography.scss";
    import Earth from './earth.svelte';
    import Cards from './cards.svelte';

</script>

<h1 class="mdc-typography--headline2">H<sub>2</sub>Amianto</h1>

<Earth />

<Cards />

<style>
    h1{
        font-weight: 900;
        text-align: center;
        line-height: 66.8px;
        color: var(--primary-color);
        max-width: 85%;
        margin-left: auto;
        margin-right: auto;
        margin-bottom: 20px;
    }

    sub{
        font-size: 2rem;
    }

</style>
