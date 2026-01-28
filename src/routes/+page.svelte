<script>
    import NavBar from "../components/navBar/navBar.svelte";
    import { goto } from "$app/navigation";
</script>
<main>
    <NavBar />
    <section
      class="relative p-2 min-h-screen bg-cover bg-center"
      style="background-image: url('/img/cristo.jpg');"
    >
  <!-- overlay oscuro SOLO para el fondo -->
    <div class="absolute inset-1 bg-black/50"></div>

    <!-- contenido encima -->
    <div class="relative z-10 h-[60vh] flex flex-col justify-center mt-12">
      <div class="mb-4">
        <h1 class="p-2 font-bold text-[45px] text-white">
          EL MEJOR RINCÓN PARA CONSENTIR EL PALADAR
        </h1>

        <p class="p-2 font-bold text-gray-200 text-[12px] max-w-xl">
          En el rincón chosicano trabajamos cada día para brindarte una experiencia
          llena de sabor y tradición, combinando años de experiencia de nuestros chefs
          con el exquisito toque norteño que potencia los sabores
        </p>
      </div>

      <div class="flex justify-around mt-8">
        <a  href="/carta"  class="bg-white px-6 py-2 text-red-600 rounded-xl font-bold inline-block">
          Ver carta
        </a>
        <a
        href="https://wa.me/615239092"
        target="_blank"
        rel="noopener noreferrer"
        class="bg-red-600 px-6 py-2 text-white rounded-xl font-bold"
        >
        Contactar
      </a>
      </div> 
    </div>
    </section>
    <section class="mt-8 px-4">
      <div class="max-w-md mx-auto bg-white rounded-2xl shadow-lg p-6 flex flex-col gap-4">
        
        <h1 class="text-center text-3xl font-extrabold text-gray-800">
          📍 Ubicación
        </h1>
    
        <p class="text-center text-gray-600 font-semibold">
          C. Vía Carpetana, 83<br />
          Madrid
        </p>
    
        <a
          href="https://www.google.com/maps?q=40.3959959,-3.7378373"
          target="_blank"
          rel="noopener noreferrer"
          class="mt-2 flex items-center justify-center gap-2 rounded-xl bg-red-600 px-4 py-3 font-bold text-white hover:bg-red-700 transition"
        >
          <!-- Icono mapa -->
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            stroke-width="2"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M17.657 16.657L13.414 20.9a2 2 0 01-2.828 0l-4.243-4.243a8 8 0 1111.314 0z"
            />
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"
            />
          </svg>
    
          Ver en Google Maps
        </a>
    
      </div>
    </section>
    

</main>

