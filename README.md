# Constructor de Estrategias de Búsqueda · PUCE Santo Domingo

Pontificia Universidad Católica del Ecuador · Sede Santo Domingo · Dirección de Investigación, Vinculación e Innovación
Docentes: Mg. José Romero · Dr. Fabricio Marcillo Vera

Herramienta web que apoya la construcción de estrategias de búsqueda desde la formulación de la pregunta de investigación. Busca descriptores MeSH y equivalentes DeCS para cada componente y genera la sintaxis para PubMed, Scopus, Web of Science, PROSPERO, Cochrane, BVS/LILACS y ERIC.

## Archivos

| Archivo | Contenido |
|---|---|
| `index.html` | Aplicación completa (HTML + CSS + JS, sin dependencias) |
| `logo-puce-sd.png` | Logo institucional (ya va integrado en `index.html`) |
| `mesh-data.js` | MeSH 2026 (NLM, dominio público) con equivalentes en español de Wikidata (CC0) |
| `scr-data-1…4.js` | Conceptos suplementarios MeSH 2026 (se cargan en segundo plano) |
| `eric-data.js` | ERIC Thesaurus 2025 (IES, dominio público) |

## Publicar en GitHub Pages

1. Crea un repositorio público y sube todos los archivos de esta carpeta.
2. En Settings › Pages, elige la rama `main` y la carpeta raíz.
3. La herramienta queda en `https://<usuario>.github.io/<repositorio>/`.

Para probarla en tu computador, no abras `index.html` con doble clic: usa un servidor local, por ejemplo `python -m http.server`, y entra a `http://localhost:8000`.

## Conexiones

- En vivo, sin clave: NCBI E-utilities (definición MeSH, conteos en PubMed y validación con PMID semilla).
- Solo enlaces: DeCS (decs.bvsalud.org), MeSH Browser, Scopus, WoS, PROSPERO, Cochrane y ERIC.
- Scopus y WoS no se consultan en vivo: requieren el acceso institucional.
- PDF: la librería jsPDF se descarga de cdnjs solo al pulsar «Descargar PDF». El Word (.docx) se genera sin librerías.
- Podcast: usa la síntesis de voz del navegador (Chrome, Edge o Safari); no genera archivo de audio, pero el guion se descarga en .txt.

## Cribado de resultados (Scopus · BibTeX)
- Importa uno o varios archivos .bib exportados desde Scopus (u otra base que exporte BibTeX); elimina duplicados por DOI o título.
- Criterios de inclusión y exclusión libres: se escriben, editan y borran a gusto (con sugerencias opcionales); filtros automáticos por años, idioma, tipo de documento y ausencia de resumen.
- Decisión registro por registro (Incluir, Duda, Excluir con motivo), con resaltado de los términos de la ecuación y atajos de teclado.
- Genera el diagrama de flujo PRISMA 2020 (PNG o SVG), con la fase de texto completo editable; el diagrama también se inserta en el Word y el PDF.
- Exporta los incluidos en .bib y el registro de cribado en .csv.
- Los registros se guardan en el navegador (IndexedDB) y viajan con el proyecto .json.

## Interfaz
- Idioma ES/EN (botones en la franja superior).
- «Nueva revisión»: borra todo y deja la herramienta limpia.
