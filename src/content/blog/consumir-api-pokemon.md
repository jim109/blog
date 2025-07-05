---
title: "Consumir una API con TypeScript: ejemplo práctico con Pokémon"
description: "Aprende cómo consumir una API y tipar sus respuestas usando interfaces TypeScript. Un ejemplo real con la PokéAPI."
pubDate: "2025-07-06"
heroImage: '../../assets/consumirApiTipescript.png'
---

En el artículo anterior aprendimos a generar interfaces a partir de una respuesta JSON. Hoy vamos a ponerlo en práctica consumiendo una API real: la de Pokémon. Usaremos `fetch` + TypeScript para mostrar una lista de pokémon en consola o en pantalla.

---

### 🧱 Paso 1: Preparar el entorno

Para este ejemplo, puedes crear un archivo `.ts` o usar una página en tu proyecto Astro si ya tienes uno andando.

---

### 📐 Paso 2: Crear la interfaz

Esta es la interfaz basada en la estructura de respuesta de la PokéAPI:

```ts
export interface PokemonListResponse {
  count: number;
  next: string;
  previous: string | null;
  results: Result[];
}

export interface Result {
  name: string;
  url: string;
}
```

---

### 🔄 Paso 3: Hacer el `fetch` con TypeScript

Ahora consumimos la API y tipamos la respuesta:

```ts
async function getPokemonList(): Promise<PokemonListResponse> {
  const response = await fetch('https://pokeapi.co/api/v2/pokemon');
  const data: PokemonListResponse = await response.json();
  return data;
}
```

---

### 🖨️ Paso 4: Mostrar los resultados

Desde consola:

```ts
getPokemonList().then(data => {
  data.results.forEach(pokemon => {
    console.log(pokemon.name);
  });
});
```

Desde una página Astro (ejemplo simple):

```astro
<ul>
  {pokemonData.results.map(p => <li>{p.name}</li>)}
</ul>
```

---

### 🛡️ Bonus: Manejar errores

```ts
try {
  const pokemons = await getPokemonList();
  // mostrar resultados...
} catch (err) {
  console.error("Ocurrió un error al obtener los Pokémon", err);
}
```

---

### ✅ Conclusión

Aprendiste cómo consumir una API en TypeScript usando interfaces para tipar tu respuesta. Esto mejora la calidad de tu código y te prepara para proyectos más grandes.


¿Te animas a probarlo con otra API? 🚀
