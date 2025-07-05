---
title: "Cómo generar interfaces TypeScript desde una respuesta JSON"
description: "Aprende paso a paso a transformar respuestas JSON en interfaces limpias de TypeScript usando Visual Studio Code."
pubDate: "2025-07-04"
author: "Jimmy Osma"
heroImage: '../../assets/json-typescript.jpg'
---

Cuando trabajamos con APIs, es muy común recibir datos en formato JSON. Sin embargo, trabajar con ellos sin estructura puede causar errores. Una solución limpia y profesional es convertir ese JSON en interfaces de **TypeScript**.

Pero antes de comenzar con el paso a paso, hay una herramienta clave que necesitas:

---

## 🔧 ¿Qué es “Paste JSON as Code” y cómo instalarlo?

> La opción `Paste JSON as Code` **no viene incluida por defecto en Visual Studio Code**. Es parte de una extensión muy útil creada por Mads Kristensen.

### 🪜 Cómo instalar la extensión:

1. Abre **Visual Studio Code**
2. Presiona:
   - `Cmd + Shift + X` en Mac  
   - `Ctrl + Shift + X` en Windows/Linux
3. Busca:  
![Cómo instalar Paste JSON as Code](/images/pastejsonascode.png)
4. Haz clic en **Instalar**
5. ¡Listo! Ahora podrás usar la opción desde la paleta de comandos (`Cmd/Ctrl + Shift + P`) o también puedes encontrarla desde el menú de Visual Studio Code en “Vista → Paleta de comandos”.
---

### ✅ ¿Qué hace exactamente?

Esta extensión te permite:

- Pegar un JSON copiado desde una respuesta de una API.
- Generar automáticamente **interfaces de TypeScript, C#, Dart**, y otros formatos

Por ejemplo, si copias este JSON:

```json
{
  "name": "pikachu",
  "level": 25
}

```
Y vas a Visual Studio Code, presionas (`Cmd/Ctrl + Shift + P`), buscas Paste JSON as Code → TypeScript Interface, obtendrás lo siguiente:

```ts
export interface NamePokemon {
    name:  string;
    level: number;
}
```
Una herramienta simple pero muy poderosa para quienes trabajan con APIs.

### 🎯 ¿Por qué es útil esto?
Transformar tus respuestas JSON en interfaces te permite:

- Validar estructuras de datos.

- Evitar errores por propiedades mal escritas.

- Mejorar la experiencia de autocompletado.

- Escribir código más limpio y mantenible.

## 🧑‍💻 Consejo extra
Esta técnica es ideal para aprender cómo se estructura una respuesta de API y cómo tiparla correctamente. Es un excelente hábito profesional.

¿Y tú, ya usaste esta extensión antes?
