# Guía para Gestión de PDFs

## Estructura de Archivos

```
/workspaces/servicios_GProA/
├── index.html
├── assets/
│   └── pdfs/
│       ├── .gitkeep
│       └── GProA_Partner_Brief.pdf
```

## Cómo Añadir un Nuevo PDF

1. **Coloca el PDF** en la carpeta `assets/pdfs/`

2. **Añade el enlace** en `index.html`:
   ```html
   <a href="assets/pdfs/nombre-del-archivo.pdf" download="nombre-del-archivo.pdf" class="...">
     <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
       <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 10v6m0 0l-3-3m3 3l3-3m2 8H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"/>
     </svg>
     Nombre del PDF
   </a>
   ```

3. **Atributo `download`**: Define el nombre con el que se descargará el archivo

## Atributos del Enlace de Descarga

- `href`: Ruta relativa al archivo PDF
- `download`: Nombre del archivo al descargar (opcional, usa el nombre original si se omite)
- `class`: Estilos Tailwind CSS

## Ejemplo Completo

```html
<a href="assets/pdfs/catalogo-servicios.pdf" download="Catalogo_Servicios_GProA.pdf" 
   class="inline-flex items-center gap-2 px-4 py-2 text-sm font-medium text-slate-600 bg-slate-100 rounded-lg hover:bg-slate-200 hover:text-slate-900 transition-colors">
  <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
          d="M12 10v6m0 0l-3-3m3 3l3-3m2 8H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"/>
  </svg>
  Descargar Catálogo
</a>
```

## Notas

- Los PDFs deben estar en formato PDF válido
- Se recomienda nombrar los archivos con guiones (-) en lugar de espacios
- El atributo `download` asegura que el navegador descargue el archivo en lugar de abrirlo
