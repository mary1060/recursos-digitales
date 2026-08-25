# Recursos Digitales — Mary Cardenas

Repositorio de archivos estaticos para regalos digitales en `recursos.marycardenas.ai`.

## Como agregar un archivo nuevo (sin usar la terminal)

1. Ir a `github.com/mary1060/recursos-digitales`
2. Entrar a la carpeta correcta segun el tipo:
   - `guias/` — PDFs de guias y ebooks
   - `plantillas/` — Plantillas descargables
   - `checklists/` — Checklists
   - `webinars/` — Grabaciones o materiales de webinar
3. Clic en **"Add file"** → **"Upload files"**
4. Arrastrar el archivo al area de upload
5. En "Commit changes" escribir una descripcion breve (ej: `agrega guia-de-prompts-2026`)
6. Clic en **"Commit changes"** (asegurarse de estar en la rama `main`)
7. Esperar ~30 segundos → Vercel despliega automaticamente
8. El archivo estara disponible en la URL correspondiente

## Convencion de nombres

- Minusculas, guiones en lugar de espacios, sin tildes ni caracteres especiales
- Incluir el ano si el archivo puede tener versiones futuras

**Ejemplos correctos:**
```
guia-de-prompts-para-ia-2026.pdf
checklist-onboarding-comunidad.pdf
plantilla-propuesta-consultoria.pdf
```

## URLs de los archivos

```
recursos.marycardenas.ai/guias/nombre-del-archivo.pdf
recursos.marycardenas.ai/plantillas/nombre-del-archivo.pdf
recursos.marycardenas.ai/checklists/nombre-del-archivo.pdf
recursos.marycardenas.ai/webinars/nombre-del-archivo.mp4
```

Ese URL va en el campo **"URL del recurso"** al crear o editar un regalo en `app.marycardenas.ai/regalos`.

---

## Por que el cache de `vercel.json` es corto (300 s)

**El orden de las reglas importa: cuando dos casan con la misma ruta, gana la
ultima.** Por eso el comodin `/(.*)` va primero y las reglas concretas despues.
Estuvo al reves hasta el 24-ago-2026 y el comodin pisaba el `Cache-Control` de
los PDF sin que se notara: la regla decia "un ano, immutable" y lo que llegaba
de verdad era `max-age=86400`.

**Los PDF y las portadas se reemplazan en su sitio**, conservando el nombre para
no romper los enlaces ya enviados por correo. Con una cache larga, una guia
actualizada tarda hasta un dia en verse — y no en todas partes a la vez, porque
depende del nodo de la CDN que atienda a cada persona. El 24-ago se actualizo la
guia de Claude Code, el origen y unos nodos servian la nueva, y al abrirla en una
ventana de incognito salia la anterior.

Con **300 s y revalidacion por ETag** la actualizacion se ve enseguida y el
trafico apenas sube: si el archivo no ha cambiado, la respuesta es un 304 vacio.

> Al reemplazar un archivo, comprobarlo con la **URL limpia**, sin `?algo=` al
> final: un parametro cambia la clave de cache y se acaba comprobando una URL
> que nadie usa.
