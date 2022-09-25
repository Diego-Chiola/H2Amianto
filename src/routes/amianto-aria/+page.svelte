<script>
    import "@material/typography/mdc-typography.scss";
	import AirCard from "./air_card.svelte";
</script>

<AirCard />

<img src="/images/air_background.svg" alt="blue sky" class="img-container">

<style>

    .img-container{
        padding-top: 15px;
        display: block;
        width: 100%;
        height: 600px;
        object-fit: cover;
    }

</style>