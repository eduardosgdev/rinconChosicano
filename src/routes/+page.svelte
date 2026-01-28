<script>
    import NavBar from "../components/navBar/navBar.svelte";
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
  <div class="relative z-10 h-[90vh] flex flex-col justify-center mt-12">
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
      <button class="bg-white px-6 py-2 text-red-600 rounded-xl font-bold">
        Ver carta
      </button>
      <button class="bg-red-600 px-6 py-2 text-white rounded-xl font-bold">
        Contactar
      </button>
    </div>
  </div>
</section>
    <section>
        <h2>Hola</h2>
    </section>
    

</main>

