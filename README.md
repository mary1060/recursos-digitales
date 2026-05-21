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
