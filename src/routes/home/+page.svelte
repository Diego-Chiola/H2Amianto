<script type="ts">
	import Button, { Label } from '@smui/button';
  
    let clicked = 0;
</script>

<h1 color="primary">H<sub>2</sub>Amianto</h1>

<div class="tap-box">
    <Button on:click={()=> clicked++} variant="outlined" style="border-color: #595959">
        <Label>Cazzo</Label>
    </Button>
</div>

<style>
    h1{
        font-weight: 900;
        text-align: center;
        line-height: 66.8px;
        color: var(--primary-color);
        font-size: 3rem;
    }

    sub{
        font-size: 2rem;
    }

    .tap-box{
        text-align: center;
    }

</style>
