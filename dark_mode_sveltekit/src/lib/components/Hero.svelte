<section class="hero">
    <h1 class="hero__h1">
        Rubén Terré
    </h1>
    <p class="hero__p">
        Diseño, desarrollo y formación
    </p>
    <div class="hero__line"></div>
</section>

<style>
    .hero{
        height: 200px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    top: 120px;
    position: relative;
    margin-block-end: 148px;
    }

    .hero__h1{
        font-family: var(--font-primary);
        color: var(--color-primary);
        font-size: 2rem;
    }

    .hero__p{
        font-family: var(--font-primary);
        color: var(--color-primary);
        font-size: 1.2rem;
        text-align: center;
    }

    .hero__line{
        width: 100px;
        height: 3px;
        background-color: var(--color-primary);
        margin-top: 20px;
    }
</style>