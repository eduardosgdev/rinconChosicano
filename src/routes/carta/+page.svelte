
<script>
    import { slide } from 'svelte/transition';
    import NavBar from "../../components/navBar/navBar.svelte";
    // Importar todos los JSON
  import Desayunos from '$lib/data/desayunos.json';
  import Entrantes from '$lib/data/fuentes.json';
  import Platos from '$lib/data/platos.json';
  import Cervezas from '$lib/data/cervezas.json';
  import Tragos from '$lib/data/tragos.json';
  import Refrescos from '$lib/data/refrescos.json';
  import Postres from '$lib/data/postres.json';

  // Arreglo con todas las categorías
  const menu = [Desayunos, Entrantes, Platos , Cervezas, Tragos, Refrescos, Postres];

  // Estado abierto/cerrado por categoría
  let abiertos = menu.map(() => false);

  // Toggle de categoría
  const toggle = (index) => {
    abiertos[index] = !abiertos[index];
  };

  // Colores por categoría (para diferenciar)
  const colores = {
    Desayunos: 'from-orange-100 to-white ring-orange-100 text-orange-600',
    Entrantes: 'from-yellow-100 to-white ring-yellow-100 text-yellow-600',
    Principales: 'from-green-100 to-white ring-green-100 text-green-600',
    Cervezas: 'from-blue-100 to-white ring-blue-100 text-blue-600',
    Tragos: 'from-purple-100 to-white ring-purple-100 text-purple-600',
    Refrescos: 'from-pink-100 to-white ring-pink-100 text-pink-600',
    Postres: 'from-red-100 to-white ring-red-100 text-red-600'
  };
</script>
<main>
    <NavBar />
    <section class="mt-4 p-2 ">
        <div class="space-y-6">
            {#each menu as categoria, i}
              <div class="rounded-2xl border  border-gray-400 bg-white shadow-sm">
                <!-- Header -->
                <button
                  on:click={() => toggle(i)}
                  class="flex w-full items-center justify-between rounded-2xl px-6 py-4 text-left transition hover:bg-gray-50"
                >
                  <h2 class="text-xl font-bold text-red-700">{categoria.categoria}</h2>
                  <svg
                    class="h-5 w-5 transform transition-transform duration-300"
                    class:rotate-180={abiertos[i]}
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                  >
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                      d="M19 9l-7 7-7-7" />
                  </svg>
                </button>
          
                <!-- Contenido desplegable -->
                {#if abiertos[i]}
                  <div class="px-6 pb-6" transition:slide>
                    <ul class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                      {#each categoria.items as item (item.nombre)}
                        <li
                          class={`rounded-2xl bg-linear-to-br ${colores[categoria.categoria] ?? 'from-gray-50 to-white ring-gray-100'} p-5 text-center ring-1 transition hover:ring-300`}
                        >
                          <p class="text-lg font-bold text-gray-900">{item.nombre}</p>
                          <p class={`mt-3 text-xl font-semibold ${colores[categoria.categoria]?.split(' ').pop() ?? 'text-gray-600'}`}>
                            €{item.precio.toFixed(2)}
                          </p>
                        </li>
                      {/each}
                    </ul>
                  </div>
                {/if}
              </div>
            {/each}
          </div>
    </section>
</main>