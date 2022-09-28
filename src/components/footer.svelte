<script>
    import Button, { Label } from '@smui/button';
	import { prevent_default } from 'svelte/internal';
    import {petition_path} from '../routes/store';

    function onClick(event){
        prevent_default(event);
        let path;
        petition_path.subscribe(value =>{
            path = value;
        })
        console.log(window.location.host);
        window.location.href = path;
    }
</script>

<footer>
        <Button on:click={(event) => {onClick(event)}} touch="true" class="petition">
            <Label class="mdc-typography--button">firma la petizione</Label>
        </Button>

        <div class="social-list">
            <a href="https://www.youtube.com/watch?v=FnwWaaOoP7c">
                <img src="images/youtube_icon.svg" alt="youtube">
            </a>
            
            <a href="https://www.facebook.com/NOallaminierasulBeigua/">
                <img src="images/facebook_icon.svg" alt="facebook">
            </a>

            <a href="https://www.instagram.com/parcobeigua/?hl=it">
                <img src="images/insta_icon.svg" alt="instagram">
            </a>
            
        </div>
</footer>

<style>
    footer{
        margin-top: auto;
        height: 120px;
        width: 100%;
        background-color: var(--ext-elements-color);
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    * :global(.petition){
        width: 200px;
        text-decoration: none;
    }

    a{
        display: inline-block;
        height: 60px;
        width: 50;
    }

    .social-list{
        width: 100%;
        text-align: center;
    }

    @media screen and (min-width: 600px){

        footer{
            height: 70px;
            flex-direction: row;
            align-items: center;
        }

        * :global(.petition){
            width: 250px;
            margin-left: 10px;
        }

        .social-list{
            text-align: end;
        }
    }
</style>