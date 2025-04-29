# ambient-mixer
ambient generador
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ambient Mixer - Solución Definitiva</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    .btn-pulse {
      animation: pulse 2s infinite;
    }
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.05); }
      100% { transform: scale(1); }
    }
  </style>
</head>
<body class="bg-gray-900 text-white font-sans min-h-screen flex items-center justify-center p-4">
  <div class="max-w-md w-full text-center">
    <h1 class="text-4xl font-bold mb-6 text-green-400">Ambient Mixer</h1>
    
    <div class="bg-gray-800 p-8 rounded-lg shadow-xl mb-6">
      <p class="text-lg mb-6">Parece que hay problemas con la reproducción de audio en tu navegador.</p>
      
      <p class="mb-6 text-gray-300">Prueba estas soluciones:</p>
      
      <div class="space-y-4">
        <button id="tryAgainBtn" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-6 rounded-lg">
          Intentar de nuevo
        </button>
        
        <a href="https://tudominio.github.io/ambient-mixer" class="block w-full bg-green-600 hover:bg-green-700 text-white font-bold py-3 px-6 rounded-lg">
          Ir a la versión online
        </a>
        
        <button id="advancedBtn" class="w-full bg-purple-600 hover:bg-purple-700 text-white font-bold py-3 px-6 rounded-lg">
          Solución avanzada
        </button>
      </div>
    </div>
    
    <div id="advancedSolution" class="hidden bg-gray-800 p-6 rounded-lg mt-4 text-left">
      <h3 class="font-bold mb-3">Instrucciones para desarrolladores:</h3>
      <ol class="list-decimal pl-5 space-y-2 text-sm text-gray-300">
        <li>Descarga este <a href="#" id="downloadLink" class="text-blue-400">código completo</a></li>
        <li>Ábrelo en VS Code o tu editor favorito</li>
        <li>Instala la extensión "Live Server"</li>
        <li>Ejecuta con Live Server (normalmente en puerto 5500)</li>
        <li>Haz clic en "Activar Sonidos" cuando se abra en el navegador</li>
      </ol>
    </div>
  </div>

  <script>
    // Elementos del DOM
    const tryAgainBtn = document.getElementById('tryAgainBtn');
    const advancedBtn = document.getElementById('advancedBtn');
    const advancedSolution = document.getElementById('advancedSolution');
    const downloadLink = document.getElementById('downloadLink');
    
    // Crear enlace de descarga
    const fullCode = `<!DOCTYPE html>
<html lang="es">
<!-- [TODO EL CÓDIGO ANTERIOR COMPLETO AQUÍ] -->
</html>`;
    
    const blob = new Blob([fullCode], { type: 'text/html' });
    downloadLink.href = URL.createObjectURL(blob);
    downloadLink.download = 'ambient-mixer-completo.html';
    
    // Event Listeners
    tryAgainBtn.addEventListener('click', () => {
      window.location.reload();
    });
    
    advancedBtn.addEventListener('click', () => {
      advancedSolution.classList.toggle('hidden');
    });
    
    // Intentar inicializar audio al cargar (para algunos navegadores)
    document.addEventListener('DOMContentLoaded', () => {
      // Solo para Chrome/Edge que permiten autoplay con gesto del usuario
      if (navigator.userAgent.includes('Chrome') || navigator.userAgent.includes('Edg')) {
        setTimeout(() => {
          tryAgainBtn.click();
        }, 1000);
      }
    });
  </script>
</body>
</html>
