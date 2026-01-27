<script>
    import { goto } from "$app/navigation";
    import "../../app.css"
    let isOpen = false;
    const logo = "/img/logo/logo.png    "
  
    function toggleMenu() {
      isOpen = !isOpen;
    }
  </script>
  <main class=" text-white px-2 py-2 bg-red-600 ">
    <!-- Contenedor principal de la navbar -->
    <nav class="flex items-center justify-between">
        <img src={logo} alt="logo" class="w-36 h-24 object-scale-cover">
      <!-- Menú hamburguesa -->
        <button class="p-1 text-white hover:bg-gray-800 rounded" on:click={toggleMenu}>
          <!-- Ícono de menú (hamburguesa) -->
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
        </button>      
    </nav>
  
    <!-- Menú desplegable en dispositivos móviles -->
    <div class={`lg:hidden ${isOpen ? 'block' : 'hidden'}  text-white  ml-2 text-[16px] font-semibold`}>
      <a href="/" class="block py-2 hover:bg-gray-800">Inicio</a>
      <a href="/escaparate" class="block py-2 hover:bg-gray-800">Escaparate</a>  
    </div>
    
  </main>
  