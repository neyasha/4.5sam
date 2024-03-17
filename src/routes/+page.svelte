<svelte:head>
<title>Палагина Настя</title>
</svelte:head>
<body>
<div class ="container">
    <div class="info">
        <div class = "animate-background">
            <div class="container info-container">
                <div class="info-text">
                    <h1>
                        <p class="animate-text-1">Профессия "программист",</p>
                        <p class="text-2">Виды, обучение и перспективы.</p>
                    </h1>
                </div>
                <h2 class="subtitle">
                    Я думаю вам будет интересно почитать этот сайт, может найдете что-то новенькое для себя.
                </h2>
            </div>
        </div>
    </div>
</div>

<div class="background-div"></div>
</body>
<style>
    body{
        margin:auto;
        display: flex;
        flex-direction: column;
        align-items: center;
        min-height: 100%;
        padding: 5vmin;
        box-sizing: border-box;
        background: antiquewhite;
    }
    .info {
        text-align: center;
        position: relative;
    }

    .info-container {
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        text-align: left;
        align-items: start;
    }

    .container {
        max-width: 1400px;
        margin: 190px 0 0 2.5rem;
    }

    .info h1 {
        font-size: 4rem;
        margin: 0;
    }

    .info h1 p {
        position: relative;
        font: inherit;
        margin: 0;
        text-align: left;
        line-height: 130%;
        width: fit-content;
        font-weight: 800;
        letter-spacing: -0.03em;
    }

    .info h2 {
        max-width: 65ch;
        font-weight: 200;
        margin-top: 0.50rem;
    }
    
    .background-div {
        background-color: #ddc98f;
        width: 100%;
        height: 56vh;
        margin: -205px auto;
    }
    .info .info-text{
        position: relative;
    }
</style>
