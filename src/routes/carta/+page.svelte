
<script>
    import { slide } from 'svelte/transition';
    import NavBar from "../../components/navBar/navBar.svelte";
    // Importar todos los JSON
  import desayunos from '$lib/data/desayunos.json';
  import bandejas from '$lib/data/fuentes.json';
  import platos from '$lib/data/platos.json';
  import cervezas from '$lib/data/cervezas.json';
  import tragos from '$lib/data/tragos.json';
  import refrescos from '$lib/data/refrescos.json';
  import postres from '$lib/data/postres.json';

  // Arreglo con todas las categorías
  const menu = [desayunos, bandejas, platos, cervezas, tragos, refrescos, postres];

  // Estado abierto/cerrado por categoría
  let abiertos = menu.map(() => false);

  // Toggle de categoría
  const toggle = (index) => {
    abiertos[index] = !abiertos[index];
  };

  // Colores por categoría (para diferenciar)
  const colores = {
    desayunos: 'from-orange-50 to-white ring-orange-100 text-orange-600',
    bandejas: 'from-yellow-50 to-white ring-yellow-100 text-yellow-600',
    platos_adicionales: 'from-green-50 to-white ring-green-100 text-green-600',
    cervezas: 'from-blue-50 to-white ring-blue-100 text-blue-600',
    tragos: 'from-purple-50 to-white ring-purple-100 text-purple-600',
    refrescos: 'from-pink-50 to-white ring-pink-100 text-pink-600',
    postres: 'from-red-50 to-white ring-red-100 text-red-600'
  };
</script>
<main>
    <NavBar />
    <section>
        <div class="space-y-6">
            {#each menu as categoria, i}
              <div class="rounded-2xl border border-gray-200 bg-white shadow-sm">
                <!-- Header -->
                <button
                  on:click={() => toggle(i)}
                  class="flex w-full items-center justify-between rounded-2xl px-6 py-4 text-left transition hover:bg-gray-50"
                >
                  <h2 class="text-xl font-bold text-gray-900">{categoria.categoria}</h2>
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
                          class={`rounded-2xl bg-gradient-to-br ${colores[categoria.categoria] ?? 'from-gray-50 to-white ring-gray-100'} p-5 text-center ring-1 transition hover:ring-300`}
                        >
                          <p class="text-lg font-bold text-gray-900">{item.nombre}</p>
                          {#if item.descripcion}
                            <p class="mt-1 text-sm text-gray-600">{item.descripcion}</p>
                          {/if}
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