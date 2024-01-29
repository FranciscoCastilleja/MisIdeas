## Código HTML

```html
<div class="inline-block py-5 w-full h-52 scroll-smooth whitespace-nowrap overflow-hidden">
  <div class="flex my-0 mx-auto w-full max-w-3xl overflow-x-scroll snap-mandatory snap-x scrolling-touch c c1">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
    <div class="item">5</div>
    <div class="item">6</div>
    <div class="item">7</div>
    <div class="item">8</div>
    <div class="item">9</div>
    <div class="item">10</div>
    <div class="item">11</div>
    <div class="item">12</div>
    <div class="item">13</div>
    <div class="item">14</div>
    <div class="item"><a class="c2">15</a></div>
  </div>
  <div class="flex my-0 mx-auto w-full max-w-3xl overflow-x-scroll snap-mandatory snap-x scrolling-touch c c2">
    <div class="item">16</div>
    <div class="item">17</div>
    <div class="item">18</div>
    <div class="item">19</div>
    <div class="item">20</div>
    <div class="item">21</div>
    <div class="item">22</div>
    <div class="item">23</div>
    <div class="item">24</div>
    <div class="item">25</div>
    <div class="item">26</div>
    <div class="item">27</div>
    <div class="item">28</div>
    <div class="item">29</div>
    <div class="item"><a class="c1">30</a></div>
  </div>
</div>
<div class="w-auto h-auto p-10">
  <button id="prev" class="my-0 mx-1 py-1 px-3 bg-cyan-700 text-white cursor-pointer rounded">Anterior</button>
  <button id="next" class="my-0 mx-1 py-1 px-3 bg-cyan-700 text-white cursor-pointer rounded">Siguiente</button>
</div>

<style>
	.item {
		scroll-snap-align: start;
		flex: 0 0 10%;
		position: relative;
		background-color: #2495ab;
		text-align: center;
		line-height: 200px;
		font-size: 24px;
    }
    
    .item a {
    	color: black;
    }

    .item:nth-child(even) {
    	background-color: #1b5466;
    }

	#c1::-webkit-scrollbar,
	#c2::-webkit-scrollbar {
    	display: none;
    }
</style>
```

## Código JS

```js
const prevButton = document.getElementById('prev') as HTMLInputElement;
const nextButton = document.getElementById('next') as HTMLInputElement;
let container = document.querySelector('.c') as HTMLElement;
const containers = [document.querySelector('.c.c1') as HTMLElement, document.querySelector('.c.c2') as HTMLElement]

function scrollContainers(direction: number) {
  container.scrollBy({
    left: direction * container.clientWidth,
    behavior: 'smooth'
  });
}

prevButton.addEventListener('click', () => {
  scrollContainers(-1);
});

nextButton.addEventListener('click', () => {
  scrollContainers(1);
});

document.querySelectorAll('.item a').forEach(link => {
  link.addEventListener('click', event => {
    const allClasses = link.classList;

    if (allClasses[0] == "c2") {
      containers[0].style.display = "none";
      containers[1].style.display = "flex";
      container = containers[1];
    } else {
      containers[0].style.display = "flex";
      containers[1].style.display = "none";
      container = containers[0];
    }
  });
});
```