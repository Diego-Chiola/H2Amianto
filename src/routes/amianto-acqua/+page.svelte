<script>
    import "@material/typography/mdc-typography.scss";
	import Water_card from "./water_card.svelte";
</script>

<Water_card />

<img src="/images/water_background.svg" alt="blue sky" class="img-container">

<style>

    .img-container{
        padding-top: 15px;
        display: block;
        width: 100%;
        height: 600px;
        object-fit: cover;
    }

</style>