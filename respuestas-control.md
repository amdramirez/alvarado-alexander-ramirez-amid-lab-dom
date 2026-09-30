# Preguntas de control

**1. ¿Qué devuelve `document.querySelector('.inexistente')` y qué pasa si luego escribes `.textContent = 'x'`?**
Devuelve `null`. Asignar una propiedad a `null` lanza `TypeError: Cannot set properties of null`. Conviene verificar el resultado (`if (el)`) o usar `?.` al leer.

**2. Si agregas 100 tareas nuevas, ¿cuántos manejadores de clic hay con delegación? ¿Y sin delegación?**
Con delegación, uno solo (en el `<ul>`), porque los eventos burbujean y `closest()` identifica el elemento pulsado, incluso si se creó después. Sin delegación habría que registrar uno por cada botón nuevo (100 más los existentes).

**3. ¿Por qué el manejador de `blur` se registra con `true` como tercer argumento?**
Porque `blur` no burbujea. Con `true` el `<form>` lo escucha en la fase de captura y un solo manejador sirve para todos los campos. Alternativa: `focusout`, que sí burbujea.
