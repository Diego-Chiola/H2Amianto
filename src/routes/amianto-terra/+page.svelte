<script>
    import "@material/typography/mdc-typography.scss";
	import Earth_card from "./earth_card.svelte";
</script>

<Earth_card />

<img src="/images/earth_background.svg" alt="blue sky" class="img-container">

<style>

    .img-container{
        padding-top: 15px;
        display: block;
        width: 100%;
        height: 600px;
        object-fit: cover;
    }

</style>