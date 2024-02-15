## Código HTML

```html
<header class="p-4 bg-gray-800 text-white text-center">
    <h1>Ejemplo de Menú Suave</h1>
</header>

<nav class="sticky p-3 top-0 bg-gray-700 z-10">
    <a class="my-0 mx-4 no-underline text-white cursor-pointer" href="#seccion1">Sección 1</a>
    <a class="my-0 mx-4 no-underline text-white cursor-pointer" href="#seccion2">Sección 2</a>
    <a class="my-0 mx-4 no-underline text-white cursor-pointer" href="#seccion3">Sección 3</a>
</nav>

<section class="p-14 my-5 mx-0" id="seccion1">
    <h2 class="py-1 text-xl">Sección 1</h2>
    <p class="py-1">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam in lectus eu ligula tincidunt dignissim. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed fermentum ligula ut ligula facilisis, vel aliquam urna laoreet. In hac habitasse platea dictumst. Quisque quis turpis vel mauris tincidunt dignissim non a sem. Vivamus nec efficitur neque. Ut quis velit vel leo feugiat congue non nec nulla. Fusce in leo vitae elit tincidunt cursus non et purus. Nullam ac elit in libero sollicitudin fringilla a id justo. Etiam in justo et mauris tincidunt vestibulum. Integer nec tortor eu arcu fermentum rhoncus at ut libero. Sed vestibulum turpis ut odio venenatis, vitae fringilla quam suscipit.</p>
</section>

<section class="p-14 my-5 mx-0" id="seccion2">
    <h2 class="py-1 text-xl">Sección 2</h2>
    <p class="py-1">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam in lectus eu ligula tincidunt dignissim. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed fermentum ligula ut ligula facilisis, vel aliquam urna laoreet. In hac habitasse platea dictumst. Quisque quis turpis vel mauris tincidunt dignissim non a sem. Vivamus nec efficitur neque. Ut quis velit vel leo feugiat congue non nec nulla. Fusce in leo vitae elit tincidunt cursus non et purus. Nullam ac elit in libero sollicitudin fringilla a id justo. Etiam in justo et mauris tincidunt vestibulum. Integer nec tortor eu arcu fermentum rhoncus at ut libero. Sed vestibulum turpis ut odio venenatis, vitae fringilla quam suscipit.</p>
</section>

<section class="p-14 my-5 mx-0" id="seccion3">
    <h2 class="py-1 text-xl">Sección 3</h2>
    <p class="py-1">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam in lectus eu ligula tincidunt dignissim. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed fermentum ligula ut ligula facilisis, vel aliquam urna laoreet. In hac habitasse platea dictumst. Quisque quis turpis vel mauris tincidunt dignissim non a sem. Vivamus nec efficitur neque. Ut quis velit vel leo feugiat congue non nec nulla. Fusce in leo vitae elit tincidunt cursus non et purus. Nullam ac elit in libero sollicitudin fringilla a id justo. Etiam in justo et mauris tincidunt vestibulum. Integer nec tortor eu arcu fermentum rhoncus at ut libero. Sed vestibulum turpis ut odio venenatis, vitae fringilla quam suscipit.</p>
</section>
```

## Código JS

```js
document.addEventListener("DOMContentLoaded", function() {
    var scrollLinks = document.querySelectorAll('nav a');

    scrollLinks.forEach(function(scrollLink) {
        scrollLink.addEventListener('click', function(this: HTMLAnchorElement, e) {
            e.preventDefault();

            let hrefAttribute = this.getAttribute('href');

            if(hrefAttribute) {
                var targetId = hrefAttribute.substring(1);
            
                var targetElement = document.getElementById(targetId) as HTMLElement;

                targetElement.scrollIntoView({
                    behavior: 'smooth'
                });
            }
        });
    });
});
```