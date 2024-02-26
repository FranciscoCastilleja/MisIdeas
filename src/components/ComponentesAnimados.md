## Código HTML - Componente

```html
<section id="sec">
    <h2>Contenido del Componente</h2>
    <button>¡Click me!</button>
</section>

<style>
    #sec {
        display: grid;
        width: 100%;
        height: 500px;
        border: 1px solid black;
        background-color: #555;
        place-items: center;
    }

    button {
        opacity: 0;
        padding: 10px 20px;
        border: 1px solid white;
    }

    @keyframes fadeIn {
        from {
            opacity: 0;
            transform: translateY(20px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    #btn_1 {
        animation: fadeIn 1s ease-out;
        animation-delay: 300ms;
        animation-fill-mode: forwards;
    }

    #btn_2 {
        animation: fadeIn 1s ease-out;
        animation-delay: 300ms;
        animation-fill-mode: forwards;
    }

    #btn_3 {
        animation: fadeIn 1s ease-out;
        animation-delay: 300ms;
        animation-fill-mode: forwards;
    }

    #btn_4 {
        animation: fadeIn 1s ease-out;
        animation-delay: 300ms;
        animation-fill-mode: forwards;
    }
</style>
```

## Código HTML - index

```html
<header class="p-4 bg-gray-800 text-white text-center">
    <h2>Ejemplo de Componentes Animados</h2>
</header>
<EjemploComponente/>
<EjemploComponente/>
<EjemploComponente/>
<EjemploComponente/>
<footer class="p-4 bg-gray-800 text-white text-center">
    <p>Footer</p>
</footer>
```

## Código JS

```js
const sections = document.querySelectorAll('#sec');
	
sections.forEach(function (section, index) {
    let button = section.querySelector('button') as HTMLButtonElement;

    const estaEnViewport = () => {
        const rect = button.getBoundingClientRect();

        return (
            rect.top >= 0 &&
            rect.left >= 0 &&
            rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &&
            rect.right <= (window.innerWidth || document.documentElement.clientWidth)
        );
    };

    if (estaEnViewport()) {
        button.id = "btn_"+(index+1).toString();
    }

    document.addEventListener('scroll', () => {
        if (estaEnViewport()) {
            button.id = "btn_"+(index+1).toString();
        }
    });
})
```