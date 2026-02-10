# Tutorial 02 - Errores Encontrados

Tarea: Detectar los errores introducidos intencionalmente en el código del tutorial.

---

## Errores

**1. Import case mismatch** : El controlador importa desde books.js (minúscula) pero el archivo se llama Books.ts (mayúscula). En Linux el servidor no arranca por esto.

**2. Category con mayúscula en el modelo** : La clase Book define Category con mayúscula, pero las vistas books.ejs y show.ejs la usan como category en minúscula. La categoría aparece vacía.

**3. Inconsistencia en show.ejs** : En la descripción usa book.category (vacío) y en la tabla de información usa book.Category (funciona). Dos formas distintas en el mismo archivo.

**4. Sin manejo de errores en show** : Visitar /books/999 o /books/abc crashea el servidor porque findById lanza una excepción sin capturar y no se valida el parámetro.

**5. viewData pasado de forma inconsistente** : Los métodos index, about y contact pasan los datos envueltos en un objeto, pero Main_Point los pasa directo. Las vistas reciben estructuras distintas y el header queda sin título.
