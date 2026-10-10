<script>
  import "../../app.css";

  const logo = "/img/logo/logo.png";

  const anioActual = new Date().getFullYear();
</script>

<footer class="bg-red-600 text-white px-4 py-6 mt-auto">
  <div class="max-w-7xl mx-auto">

    <!-- Contenido principal del footer -->
    <div class="flex flex-col md:flex-row items-center justify-between gap-6">

      <!-- Logo -->
      <a href="/" aria-label="Ir al inicio">
        <img
          src={logo}
          alt="Logo"
          class="w-32 h-auto object-contain"
        />
      </a>

      <!-- Enlaces -->
      <nav
        class="flex flex-wrap justify-center gap-6 text-sm font-semibold"
        aria-label="Navegación del pie de página"
      >
        <a href="/" class="hover:text-gray-200 transition-colors">
          Inicio
        </a>

        <a href="/carta" class="hover:text-gray-200 transition-colors">
          Carta
        </a>

        <a href="/redes" class="hover:text-gray-200 transition-colors">
          Nuestras redes
        </a>
      </nav>

    </div>

    <!-- Separador -->
    <div class="border-t border-red-400 mt-6 pt-4 text-center">
      <p class="text-sm text-white/90">
        © {anioActual} Todos los derechos reservados.
      </p>
    </div>

  </div>
</footer>
