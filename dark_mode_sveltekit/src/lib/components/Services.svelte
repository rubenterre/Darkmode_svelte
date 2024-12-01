<script>
import {servicios} from "$lib/services.js"

</script>
<section class="services">
    <div class="services__container">
        <div class="services__title">
            <h3 class="services__h3">
                SERVICIOS
            </h3>
            <p class="services__p">
                Algunos servicios que puedo ofrecerte
            </p>
            <div class="services__line"></div>

        </div>
        <div class="services__cards">
           
           {#each servicios as item }
           <div class="services__card">
            <div class="services__image">
                <img class="services__img" src={item.img} alt={item.title} width="300px" />
            </div>
            <div class="services__details">
                <h4 class="services__h4">{item.title}</h4>
                <p class="services__p">
                    {item.description}
                </p>
                <div class="services__tags">
                    {#each item.tags as tag}
                    <p class="services__tag">{tag}</p>

                    {/each}
                </div>
            </div>
        </div>
           {/each}
        
           
        </div>
    </div>
</section>

<style>
    .services{
        margin: 0px 40px;
    }

    .services__title{
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .services__h3{
        font-family: var(--font-primary);
        color: var(--color-primary);
        font-size: 1.3rem;
    }

    .services__p{
        font-family: var(--font-primary);
        color: var(--color-primary);
        font-size: 1rem;
    }

    .services__line{
        width: 100px;
        height: 3px;
        background-color: var(--color-primary);
        margin-top: 20px;
    }

    .services__cards{
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
        justify-content: center;
        margin: 20px 0px;
    }


    .services__card {
		width: 300px;
		box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.2);
		border-radius: 10px;
        border: .2px solid var(--color-primary);
	}

	.services__img {
		border-top-left-radius: 10px;
		border-top-right-radius: 10px;
		width: 100%;
	}

    .services__details{
        padding: 10px;
    }

    .services__h4{
        font-family: var(--font-secondary);
        font-size: 1.1rem;
        color: var(--color-primary);
        margin-bottom: 5px;
    }

    .services__p{
        font-family: var(--font-primary);
        font-size: .8rem;
        color: var(--color-primary);
        margin-bottom: 5px;
    }

    .services__tags{
        margin: 10px 0px;
        display: flex;
        flex-wrap: wrap;
        gap: 5px;
    }

.services__tag{
    padding: 5px 10px;
    font-family: var(--font-secondary);
    color: var(--color-secondary);
    background-color: var(--color-primary);
    border-radius: 10px;
}

</style>