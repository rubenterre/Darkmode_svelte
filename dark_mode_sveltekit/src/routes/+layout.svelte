<script>
 import { onMount } from 'svelte';


  let theme = 'light'; 

  const toggleTheme = () => {
    theme = theme === 'light' ? 'dark' : 'light';
    document.documentElement.setAttribute('data-theme', theme);
    localStorage.setItem('theme', theme); 
  };

  // Cargar el tema almacenado en localStorage (si existe)
  onMount(() => {
    const savedTheme = localStorage.getItem('theme');
    if (savedTheme) {
      theme = savedTheme;
      document.documentElement.setAttribute('data-theme', theme);
    }
  });
  </script>
<header class="header">
    <nav class="header__nav">
        <a class="header__a" href="#services">Servicios</a>
        <a href="/" class="header__a"> 
            <img class="header__img" src="./LOGO_RT.png" alt="Logo de Rubén Terré" width="60px">
        </a>
        <a class="header__a" href="#contact">Contacto</a>
    </nav>
    <button class="header__button" onclick={toggleTheme}>
        {theme === 'light' ? 'Cambiar a modo oscuro' : 'Cambiar a modo claro'}
    </button>
</header>

    <slot />
    



<style>
@font-face{
    font-family: 'Poppins-Regular';
    src: url('./fonts/Poppins-Regular.ttf') format('ttf');
}

@font-face{
    font-family: 'Poppins-SemiBold';
    src: url('./fonts/Poppins-SemiBold.ttf') format('ttf');
}
    
     :global(:root){
        --color-primary: black;
        --color-secondary: whitesmoke;
        --font-primary: 'Poppins-Regular';
        --font-secondary: 'Poppins-SemiBold';
    } 

    :global([data-theme="dark"]) {
        --color-primary: whitesmoke;
        --color-secondary: black;
        --font-primary: 'Poppins-Regular';
        --font-secondary: 'Poppins-SemiBold';
    }


    :global(*) {
      margin: 0;
      padding: 0;
      outline: 0;
      box-sizing: border-box;
    }
    
    :global(body) {
     background: var(--color-secondary);
     color: var(--color-primary);
     -webkit-font-smoothing: antialiased;
     transition: all 0.5s ease, color 0.5s ease;
    }
    
    :global(body, input, button){
     font-size: 14px;
     font-family: var(--font-primary);
    }
    
    :global(button) {
     cursor: pointer;
    }


    /*/ Header /*/

    .header{
        width: 100%;
        height: 135px;
        position: fixed;
        background-color: var(--color-secondary);
        /* box-shadow: 0px 5px 10px var(--color-primary); */
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        gap: 20px;
    }

    .header__nav{
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 20px;
    }

    .header__a{
        font-family: var(--font-primary);
        color: var(--color-primary);
        font-size: 1rem;
        text-decoration: none;
    }

    .header__a:hover{
        text-decoration: underline;
    }

    .header__button{
        background-color: var(--color-primary);
        color: var(--color-secondary);
        padding: 5px 8px;
        border-radius: 10px;
    }

</style>