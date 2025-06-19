# jojo-S
Le choix dépendra de la complexité de votre projet, de vos besoins en ressources et de votre budget. 
<!DOCTYPE html>
<html>
  <head>
    <title>My app</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta charset="utf-8">
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
      tailwind.config = {
        theme: {
          extend: {
            colors: {
              amber: { 500: '#f59e0b', 400: '#fbbf24' },
              blue: { 500: '#3b82f6', 400: '#60a5fa' },
              green: { 500: '#22c55e', 400: '#4ade80' }
            }
          }
        }
      }
    </script>
  </head>
  <body class="flex justify-center items-center min-h-screen bg-[url('https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=1500&q=80')] bg-cover bg-center font-sans text-center px-6">
    <div class="w-full max-w-2xl mx-auto bg-white/80 rounded-xl p-6 shadow-lg">
      <span class="text-xs rounded-full mb-2 inline-block px-2 py-1 border border-amber-500/15 bg-amber-500/15 text-amber-500">🔥</span>
      <h1 class="text-4xl lg:text-6xl font-bold font-sans">
        <span class="text-2xl lg:text-4xl text-gray-400 block font-medium">Je suis prêt à travailler</span>
        Posez-moi n'importe quelle question
      </h1>
      <div class="mt-8 flex flex-col items-center gap-4">
        <a href="https://chat.openai.com/?model=gpt-4" target="_blank" class="px-4 py-2 bg-amber-500 text-white rounded hover:bg-amber-400 transition">
          Accéder à GPT-4
        </a>
        <button id="btn-google" class="px-4 py-2 bg-green-500 text-white rounded hover:bg-green-400 transition">
          Chercher "hacking cloud" sur Google
        </button>
      </div>
      <!-- Prompt utilisateur -->
     
      <div id="prompt-result" class="mt-2 text-gray-700"></div>
      <!-- Menu spécial liens utiles -->
      <div class="mt-10 max-w-xl mx-auto">
        <button id="toggle-links" class="mb-4 px-4 py-2 bg-gray-800 text-white rounded hover:bg-gray-700 transition w-full flex items-center justify-between">
          <span>🔗 Menu Liens Utiles</span>
          <span id="arrow">▼</span>
        </button>
        <div id="special-links" class="hidden bg-white border rounded-lg shadow p-4">
          <ul class="space-y-3 text-left">
            <li>
                <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub Pages" class="w-6 h-6 rounded" />
                Voir mon site sur GitHub Pages
              </a>
            </li>
            <!-- Ajoute ici d'autres liens si besoin -->
          </ul>
        </div>
      </div>
    </div>
    <img src="https://enzostvs-deepsite.hf.space/arrow.svg" class="absolute bottom-8 left-0 w-[100px] transform rotate-[30deg]" />
    <script>
      // Google "hacking cloud"
      document.getElementById('btn-google').onclick = function() {
        window.open('https://www.google.com/search?q=hacking+cloud', '_blank');
      };
      // Menu liens spéciaux
      const btn = document.getElementById('toggle-links');
      const menu = document.getElementById('special-links');
      const arrow = document.getElementById('arrow');
      btn.onclick = function() {
        menu.classList.toggle('hidden');
        arrow.textContent = menu.classList.contains('hidden') ? '▼' : '▲';
      };
      // Prompt utilisateur
      document.getElementById('prompt-form').onsubmit = function(e) {
        e.preventDefault();
        const value = document.getElementById('prompt-input').value;
        document.getElementById('prompt-result').textContent = "Vous avez saisi : " + value;
        document.getElementById('prompt-input').value = "";
      };
    </script>
  </body>
</html>
