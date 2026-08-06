# Bioestadística SPAB305 · clases para celular

Diapositivas interactivas adaptadas a pantallas de celular y tablet. Cada archivo es autocontenido: no requiere conexión ni archivos adjuntos una vez abierto.

- `index.html` reúne las doce clases con un selector en la barra inferior.
- Los archivos `clase-NN-*.html` abren cada clase por separado.

Su publicación en línea busca facilitar el acceso desde el celular. No reemplaza al material oficial de la asignatura ni constituye una publicación institucional. Las marcas y los contenidos oficiales pertenecen a sus titulares.

## Clases

| N.º | Clase | Archivo |
|---|---|---|
| 1 | Introducción a la Bioestadística | `clase-01-introduccion-a-la-bioestadistica.html` |
| 2 | Método estadístico y escalas de medición | `clase-02-metodo-estadistico-y-escalas-de-medicion.html` |
| 3 | Representación gráfica | `clase-03-representacion-grafica.html` |
| 4 | Tendencia central y dispersión | `clase-04-tendencia-central-y-dispersion.html` |
| 5 | Posición, asimetría y curtosis | `clase-05-posicion-asimetria-y-curtosis.html` |
| 6 | Probabilidad aplicada a la salud | `clase-06-probabilidad-aplicada-a-la-salud.html` |
| 7 | Distribuciones, Bayes y pruebas diagnósticas | `clase-07-distribuciones-bayes-y-pruebas-diagnosticas.html` |
| 8 | Binomial, Poisson, Normal y distribuciones asociadas | `clase-08-binomial-poisson-normal-y-distribuciones-asociadas.html` |
| 9 | Inferencia estadística, estimación e intervalos de confianza | `clase-09-inferencia-estadistica-estimacion-e-intervalos-de-confianza.html` |
| 10 | Pruebas de hipótesis y valor-p | `clase-10-pruebas-de-hipotesis-y-valor-p.html` |
| 11 | Correlación y regresión lineal | `clase-11-correlacion-y-regresion-lineal.html` |
| 12 | Pruebas no paramétricas y análisis de sobrevida | `clase-12-pruebas-no-parametricas-y-analisis-de-sobrevida.html` |

Todas incluyen la diapositiva de cronograma del semestre, construida sobre el **syllabus final de sede Santiago para el segundo semestre de 2026**: fechas de las tres evaluaciones, examen final del viernes 4 de diciembre, examen de repetición del lunes 14 de diciembre, semana de consolidación y el feriado del 18 de septiembre.

---

# Cómo publicarlo en GitHub Pages

Repositorio: `https://github.com/javierverabravo/bioestadistica-spab305_2026` · público · rama `main`.

Dirección publicada, una vez activado Pages:

```
https://javierverabravo.github.io/bioestadistica-spab305_2026/
```

## Requisitos, una sola vez

Comprobar si git está instalado. En PowerShell:

```powershell
git --version
```

Si responde con un número de versión, está listo. Si no, se instala desde `https://git-scm.com/download/win` aceptando las opciones por omisión.

Identificarse. Estos datos quedan registrados en cada publicación:

```powershell
git config --global user.name "Javier Vera"
git config --global user.email "javerab@gmail.com"
```

## Publicar

El repositorio se creó con un README automático, de modo que ya tiene un commit. El contenido de esta carpeta lo reemplaza por completo. Ejecutar en PowerShell, línea por línea:

```powershell
cd "E:\Clases Bioestadística\MEDICINA UNAB\Material UNAB actualizado\_publicar en GitHub"

git init
git branch -M main
git add .
git commit -m "Clases de Bioestadistica SPAB305 para celular"
git remote add origin https://github.com/javierverabravo/bioestadistica-spab305_2026.git
git push -u --force origin main
```

La primera vez se abre una ventana del navegador para iniciar sesión y autorizar. Conviene elegir la opción de autenticarse con el navegador; git guarda la credencial y no vuelve a pedirla.

El `--force` es necesario solo en esta primera subida, porque sustituye el README automático que quedó al crear el repositorio. En las actualizaciones posteriores no se usa.

## Activar Pages

En el repositorio, **Settings** → **Pages**:

- **Source**: `Deploy from a branch`.
- **Branch**: `main`, carpeta `/ (root)`.
- **Save**.

La publicación tarda entre uno y tres minutos. Para abrir una clase suelta se agrega el nombre del archivo:

```
https://javierverabravo.github.io/bioestadistica-spab305_2026/clase-01-introduccion-a-la-bioestadistica.html
```

## Actualizar el material más adelante

Cuando cambie una clase, se copia el archivo nuevo a esta carpeta con el mismo nombre y se repiten tres líneas, ahora sin `--force`:

```powershell
cd "E:\Clases Bioestadística\MEDICINA UNAB\Material UNAB actualizado\_publicar en GitHub"

git add .
git commit -m "Actualiza el cronograma segun el syllabus final"
git push
```

El sitio se regenera solo, en un par de minutos. Conviene recargar con `Ctrl + F5` la primera vez, porque el navegador guarda la versión anterior en caché.

## Si algo falla

**`fatal: not a git repository`.** No se ejecutó `git init`, o la terminal no está en esta carpeta. Repetir el `cd`.

**`remote origin already exists`.** Se corrige con `git remote set-url origin https://github.com/javierverabravo/bioestadistica-spab305_2026.git`.

**`Updates were rejected because the remote contains work`.** Falta el `--force` de la primera subida.

**`src refspec main does not match any`.** No se alcanzó a crear el commit. Repetir `git add .` y `git commit`.

**El sitio muestra error 404.** Suele ser que Pages todavía no termina, o que en Settings → Pages quedó seleccionada una rama distinta de `main`. También conviene verificar que `index.html` esté en la raíz del repositorio y no dentro de una subcarpeta.

**Los archivos aparecen pero se ven sin estilo.** Falta el archivo `.nojekyll`, que impide que GitHub procese el sitio con Jekyll. Está incluido en esta carpeta; al ser un archivo oculto, algunos programas de copia lo omiten.

## Sobre esta carpeta

`.nojekyll` evita el procesamiento con Jekyll. `.gitignore` excluye archivos de sistema de Windows. Ninguno de los dos se ve en el sitio publicado.
