<script lang="ts">
	import Articulo from './Articulo.svelte';
	import Indice from './Indice.svelte';
	export let capitulos: RawCapitulo[];
	import { browser } from '$app/env';

	function sortedArticulos(articulos: RawArticulo[]) {
		return articulos.sort((a, b) => {
			if (a.attributes.numero_de_articulo < b.attributes.numero_de_articulo) {
				return -1;
			}
			if (a.attributes.numero_de_articulo > b.attributes.numero_de_articulo) {
				return 1;
			}
			return 0;
		});
	}

	if (browser) {
		if (window?.location?.href.includes('netlify.app')) {
			window?.location?.replace('https://tabla-constitucional.cl/');
			console.log('window.location.href', window?.location?.href);
		}
	}

	let hasBeenCopied: boolean = false;

	const fullTitle = `La nueva constitución de forma interactiva!
https://tabla-constitucional.cl/
`;
	const fullTitleUrl = `La nueva constitución de forma interactiva!%0Ahttps://tabla-constitucional.cl/%0A`;

	function copyToClipboard() {
		if (browser) {
			navigator.clipboard.writeText(fullTitle);
			hasBeenCopied = true;
		}
	}
</script>

<h1 class="text-4xl md:text-6xl pl-3 md:pl-6 font-extralight text-[#25f8b9db] my-5">
	Tabla periódica de la Nueva Constitución Chilena 🇨🇱
</h1>

<p class="pl-3 md:pl-6 text-white text-lg">
	En esta página se encuentran todos los artículos de la <a
		href="https://www.chileconvencion.cl/"
		class="underline"
		target="blanc">nueva constitución</a
	> separados por capítulos y subcapítulos. Está animado como una tabla periódica y separada en colores
	para hacerla mas entretenida.
</p>

<h1 class="text-3xl md:text-4xl pl-3 md:pl-6 font-extralight text-[#25f8b9db] my-5">
	#SinArticuloNoHayDebate
</h1>
<p class="pl-3 md:pl-6 text-white text-lg">
	Exijamos un debate constructivo, criticar la constitución sin citar artículos no sirve de gran
	cosa.
</p>
<p class="pl-3 md:pl-6 text-white text-lg">
	<strong>#SinArticuloNoHayDebate</strong>, no se caliente la cabeza.
</p>
<h1 class="text-3xl md:text-4xl pl-3 md:pl-6 font-extralight text-[#25f8b9db] my-5">
	Ayúdenos compartiendo esta página 🙏
</h1>
<div class="pl-3 md:pl-6 text-white text-lg ">
	<!-- TWITTER -->
	<div class="inline-block">
		<a
			href={`https://twitter.com/intent/tweet?text=${fullTitleUrl}`}
			target="blanc"
			class="inline-flex text-sm text-white bg-[#1da1f2] hover:bg-[#1da1f2]/90 focus:ring-4 focus:outline-none focus:ring-[#1da1f2]/50 font-medium rounded-lg px-5 py-2.5 text-center items-center dark:focus:ring-[#1da1f2]/55 mr-2 mb-2"
		>
			<svg
				class="mr-2 -ml-1 w-4 h-4"
				aria-hidden="true"
				focusable="false"
				data-prefix="fab"
				data-icon="twitter"
				role="img"
				xmlns="http://www.w3.org/2000/svg"
				viewBox="0 0 512 512"
				><path
					fill="currentColor"
					d="M459.4 151.7c.325 4.548 .325 9.097 .325 13.65 0 138.7-105.6 298.6-298.6 298.6-59.45 0-114.7-17.22-161.1-47.11 8.447 .974 16.57 1.299 25.34 1.299 49.06 0 94.21-16.57 130.3-44.83-46.13-.975-84.79-31.19-98.11-72.77 6.498 .974 12.99 1.624 19.82 1.624 9.421 0 18.84-1.3 27.61-3.573-48.08-9.747-84.14-51.98-84.14-102.1v-1.299c13.97 7.797 30.21 12.67 47.43 13.32-28.26-18.84-46.78-51.01-46.78-87.39 0-19.49 5.197-37.36 14.29-52.95 51.65 63.67 129.3 105.3 216.4 109.8-1.624-7.797-2.599-15.92-2.599-24.04 0-57.83 46.78-104.9 104.9-104.9 30.21 0 57.5 12.67 76.67 33.14 23.72-4.548 46.46-13.32 66.6-25.34-7.798 24.37-24.37 44.83-46.13 57.83 21.12-2.273 41.58-8.122 60.43-16.24-14.29 20.79-32.16 39.31-52.63 54.25z"
				/></svg
			>
			Compartir en Twitter
		</a>
	</div>

	<!-- WHATSAPP -->
	<div class="inline-block">
		<a
			href={`https://wa.me/?text=${fullTitleUrl}`}
			target="blanc"
			class="inline-flex text-sm text-white bg-[#59CE72] hover:bg-[#59CE72]/90 focus:ring-4 focus:outline-none focus:ring-[#59CE72]/50 font-medium rounded-lg px-5 py-2.5 text-center items-center dark:focus:ring-[#59CE72]/55 mr-2 mb-2"
		>
			<svg
				class="mr-2 -ml-1 w-4 h-4"
				xmlns="http://www.w3.org/2000/svg"
				width="16"
				height="16"
				fill="currentColor"
				viewBox="0 0 16 16"
			>
				<path
					d="M13.601 2.326A7.854 7.854 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.057 3.965L0 16l4.204-1.102a7.933 7.933 0 0 0 3.79.965h.004c4.368 0 7.926-3.558 7.93-7.93A7.898 7.898 0 0 0 13.6 2.326zM7.994 14.521a6.573 6.573 0 0 1-3.356-.92l-.24-.144-2.494.654.666-2.433-.156-.251a6.56 6.56 0 0 1-1.007-3.505c0-3.626 2.957-6.584 6.591-6.584a6.56 6.56 0 0 1 4.66 1.931 6.557 6.557 0 0 1 1.928 4.66c-.004 3.639-2.961 6.592-6.592 6.592zm3.615-4.934c-.197-.099-1.17-.578-1.353-.646-.182-.065-.315-.099-.445.099-.133.197-.513.646-.627.775-.114.133-.232.148-.43.05-.197-.1-.836-.308-1.592-.985-.59-.525-.985-1.175-1.103-1.372-.114-.198-.011-.304.088-.403.087-.088.197-.232.296-.346.1-.114.133-.198.198-.33.065-.134.034-.248-.015-.347-.05-.099-.445-1.076-.612-1.47-.16-.389-.323-.335-.445-.34-.114-.007-.247-.007-.38-.007a.729.729 0 0 0-.529.247c-.182.198-.691.677-.691 1.654 0 .977.71 1.916.81 2.049.098.133 1.394 2.132 3.383 2.992.47.205.84.326 1.129.418.475.152.904.129 1.246.08.38-.058 1.171-.48 1.338-.943.164-.464.164-.86.114-.943-.049-.084-.182-.133-.38-.232z"
				/>
			</svg>
			Compartir en WhatsApp
		</a>
	</div>

	<!-- COPIAR -->
	<div class="inline-block">
		<button
			on:click={copyToClipboard}
			type="button"
			class=" inline-flex  text-white bg-[#24292F] hover:bg-[#24292F]/90 focus:ring-4 focus:outline-none focus:ring-[#24292F]/50 font-medium rounded-lg text-sm px-5 py-2.5 text-center items-center dark:focus:ring-gray-500 dark:hover:bg-[#050708]/30 mr-2 mb-2 mt-0"
		>
			Copiar link de la página
		</button>
	</div>

	{#if hasBeenCopied}
		<p>Copiado!</p>
	{/if}
</div>

<br />

<img class="max-w-xl w-full mt-10 m-auto" src="./como-funciona.webp" alt="Como Funciona" />

<Indice {capitulos} />

{#each capitulos as capitulo}
	<h2
		class="text-2xl md:text-3xl pl-3 md:pl-6 text-white font-bold mt-6"
		id={`${capitulo.attributes.Nombre}-capitulo`}
	>
		{capitulo.attributes.Nombre}
	</h2>
	{#each capitulo.attributes.sub_capitulos.data as subCapitulo}
		<div
			class="pl-3 md:pl-6 flex items-center mt-4 mb-2"
			id={`${subCapitulo.attributes.Nombre}-subcapitulo`}
		>
			<span
				class="w-7 h-7 inline-block flex-none shadow-3xl rounded-full"
				style={`background-color: #${subCapitulo.attributes.hex_color}`}
			/>
			<h3 class="text-xl md:text-2xl text-white pl-3">
				{subCapitulo.attributes.Nombre}
			</h3>
		</div>
		<div class="pl-3 md:pl-6 mb-6 md:mb-10">
			{#each sortedArticulos(subCapitulo.attributes.articulos.data) as articulo}
				<Articulo {articulo} hex_color={subCapitulo.attributes.hex_color} />
			{/each}
		</div>
	{/each}
{/each}
