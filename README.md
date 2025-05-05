<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Pokédex</title>
  <link rel="icon" href="https://i.pinimg.com/originals/1b/41/20/1b412053a7b59ab47149a3eb59e5804d.png" type="image/png">
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #131255;
      margin: 0;
      padding: 20px;
    }
    h1 {
      text-align: center;
      color: white;
      font-size: 40px;
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 10px;
    }
    h1 img {
      height: 60px;
    }
    #search-bar {
      display: flex;
      justify-content: center;
      margin-bottom: 50px;
    }
    #search {
      width: 300px;
      padding: 10px;
      font-size: 18px;
      border-radius: 8px;
      border: 4px solid #0b257c;
      background-color: #e0e0e0;
    }
    .pokedex {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }
    .pokemon {
      background: white;
      border: 4px solid #092580;
      border-radius: 39px;
      padding: 5px;
      margin: 9px;
      width: 170px;
      text-align: center;
      box-shadow: 0 2px 0px rgba(0,0,0,0.1);
    }
    .pokemon img {
      width: 96px;
      height: 89px;
    }
    .pokemon span {
      font-weight: bold;
      display: block;
      margin-top: 1px;
      font-size: 16px;
    }
  </style>
</head>
<body>
  <h1>
    <img src="https://emoji.discadia.com/emojis/fb04d933-42ba-4710-acb3-32f0399872fa.PNG" alt="Pikachu" style="height: 90px;">
    <img src="https://th.bing.com/th/id/R.d37b9bbf1550320f5d20423a5f862b52?rik=4kEHYdP%2bC0B5RA&riu=http%3a%2f%2fpixelartmaker.com%2fart%2f698b0a431a499bc.png&ehk=4e%2bMuvlFJmms37XExxWTtDMTqg7DYC%2b9%2fRygFCzjNQQ%3d&risl=&pid=ImgRaw&r=0&sres=1&sresct=1"alt= "Pokémon Logo" style="height: 170px;">
  </h1>
  <div id="search-bar">
    <input type="text" id="search" placeholder="Pesquisar por nome ou número...">
  </div>
  <div class="pokedex" id="pokedex"></div>
  <script>
    const pokedex = document.getElementById("pokedex");
    const searchInput = document.getElementById("search");
    const pokemonNames = ["", "bulbasaur", "ivysaur", "venusaur", "charmander", "charmeleon", "charizard", "squirtle", "wartortle", "blastoise", "caterpie", "metapod", "butterfree", "weedle", "kakuna", "beedrill", "pidgey", "pidgeotto", "pidgeot", "rattata", "raticate", "spearow", "fearow", "ekans", "arbok", "pikachu", "raichu", "sandshrew", "sandslash", "nidoran♀", "nidorina", "nidoqueen", "nidoran♂", "nidorino", "nidoking", "clefairy", "clefable", "vulpix", "ninetales", "jigglypuff", "wigglytuff", "zubat", "golbat", "oddish", "gloom", "vileplume", "paras", "parasect", "venonat", "venomoth", "diglett", "dugtrio", "meowth", "persian", "psyduck", "golduck", "mankey", "primeape", "growlithe", "arcanine", "poliwag", "poliwhirl", "poliwrath", "abra", "kadabra", "alakazam", "machop", "machoke", "machamp", "bellsprout", "weepinbell", "victreebel", "tentacool", "tentacruel", "geodude", "graveler", "golem", "ponyta", "rapidash", "slowpoke", "slowbro", "magnemite", "magneton", "farfetch'd", "doduo", "dodrio", "seel", "dewgong", "grimer", "muk", "shellder", "cloyster", "gastly", "haunter", "gengar", "onix", "drowzee", "hypno", "krabby", "kingler", "voltorb", "electrode", "exeggcute", "exeggutor", "cubone", "marowak", "hitmonlee", "hitmonchan", "lickitung", "koffing", "weezing", "rhyhorn", "rhydon", "chansey", "tangela", "kangaskhan", "horsea", "seadra", "goldeen", "seaking", "staryu", "starmie", "mr. mime", "scyther", "jynx", "electabuzz", "magmar", "pinsir", "tauros", "magikarp", "gyarados", "lapras", "ditto", "eevee", "vaporeon", "jolteon", "flareon", "porygon", "omanyte", "omastar", "kabuto", "kabutops", "aerodactyl", "snorlax", "articuno", "zapdos", "moltres", "dratini", "dragonair", "dragonite", "mewtwo", "mew"];
    pokemonNames.slice(1).forEach((name, i) => {
      pokedex.innerHTML += `
        <div class="pokemon" data-id="${i + 1}" data-name="${name}">
          <img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${i + 1}.png" alt="${name}">
          <span>#${i + 1} ${name}</span>
        </div>
      `;
    });
    searchInput.addEventListener("input", () => {
      const search = searchInput.value.toLowerCase();
      document.querySelectorAll(".pokemon").forEach(p => {
        const id = p.dataset.id;
        const name = p.dataset.name;
        p.style.display = name.includes(search) || id.includes(search) ? "block" : "none";
      });
    });
  </script>
</body>
</html>
