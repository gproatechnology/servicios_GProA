# Generación del PDF - Partner Brief GProA Technology

## Método 1: Navegador Web (Recomendado)
1. Abre `partner-brief-print.html` en tu navegador
2. Presiona `Ctrl+P` (o `Cmd+P` en Mac)
3. Selecciona "Guardar como PDF" como destino
4. Configura márgenes: "Ninguno" o "Mínimos"
5. Activa "Gráficos de fondo" si está disponible

## Método 2: wkhtmltopdf (Línea de comandos)
```bash
# Instalar wkhtmltopdf
# macOS: brew install wkhtmltopdf
# Linux: apt-get install wkhtmltopdf
# Windows: descargar desde wkhtmltopdf.org

# Generar PDF
wkhtmltopdf --enable-local-file-access \
  --print-media-type \
  --margin-top 20mm \
  --margin-bottom 20mm \
  --margin-left 15mm \
  --margin-right 15mm \
  partner-brief-print.html partner-brief.pdf
```

## Método 3: Puppeteer (Node.js)
```javascript
const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  
  await page.goto(`file://${__dirname}/partner-brief-print.html`, {
    waitUntil: 'networkidle0'
  });
  
  await page.pdf({
    path: 'partner-brief.pdf',
    format: 'A4',
    printBackground: true,
    margin: {
      top: '20mm',
      bottom: '20mm',
      left: '15mm',
      right: '15mm'
    }
  });
  
  await browser.close();
})();
```

## Notas
- El archivo `partner-brief.pdf` incluido es un placeholder
- Genera el PDF real usando uno de los métodos arriba para obtener resultado profesional
- El HTML print-optimized está diseñado específicamente para impresión PDF
