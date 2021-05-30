<script>
    export let dataset;
</script>

<style>
    .container {
        display: flex;
        align-items: center;
        width: 90vw;
        margin-top: 50px;
        -webkit-box-shadow: 0px 5px 20px 10px rgba(0,0,0,0.2); 
        box-shadow: 0px 5px 20px 10px rgba(0,0,0,0.2);
        background-color: #000;
    }
    .picture {
        max-width: 45vw;
    }
    .infos {
        padding-left: 25px;
        padding-right: 25px;
        word-wrap: break-word;
        color: #eff3f7;
    }

    @media screen and (max-width: 1000px) {
        .container {
            flex-direction: column;
        }
        .picture {
        max-width: 90vw;
        }
    }

</style>

<div class="container">
    <img src={dataset.hdurl} alt={dataset.title} class="picture">
    <div class="infos">
        <h2>{dataset.title}</h2><br>
        <p>{dataset.date}</p><br>
        <p>{dataset.explanation}</p><br>
    </div>
</div>