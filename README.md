# Final – Introducción a la Ciencia de Datos: Adventure Works Cycles

Limpieza y análisis descriptivo de las ventas por internet de **AdventureWorksDW2022**, la base de datos de ejemplo de Microsoft para SQL Server.

## Estructura

```
final-ciencia-de-datos/
├── analisis_ventas_adventureworks.ipynb   # notebook con todo el proceso
├── datos/
│   ├── SL/                                # tablas extraídas de SQL Server, sin limpieza (entrada)
│   │   └── ventas.csv, clientes.csv, productos.csv, geografia.csv, ...
│   ├── imagenes/                          # fotos de los productos con más ingresos (sección 6.12)
│   └── CL/ventas_CL.csv                   # dataset limpio e integrado (salida del notebook)
├── reporte/
│   └── REPORTE_NO_CORREGIDOS.csv          # datos que no se pudieron corregir (salida del notebook)
├── graficos/                              # gráficos en PNG (salida del notebook)
├── .env.example                           # plantilla de las credenciales de la base
├── requirements.txt
└── README.md
```

## Ejecución local

### Linux, macOS o WSL

1. Instalar dependencias (solo la primera vez):

   ```bash
   python3 -m venv .venv
   .venv/bin/pip install -r requirements.txt
   ```

2. *(Opcional)* Para volver a extraer los datos desde SQL Server, restaurar `AdventureWorksDW2022.bak` en SQL Server 2022, copiar `.env.example` como `.env` y completar el usuario y la contraseña. El servidor debe tener habilitados TCP/IP (puerto 1433) y la autenticación de SQL Server. Sin `.env`, el notebook usa los CSV de `datos/SL/`.

3. Abrir el notebook y ejecutar todas las celdas en orden (*Run All*):

   ```bash
   .venv/bin/jupyter notebook analisis_ventas_adventureworks.ipynb
   ```

   También se puede abrir en VS Code eligiendo el intérprete de `.venv`.

4. *(Alternativa)* Ejecutar el notebook completo desde la terminal, sin abrirlo. Es lo mismo que *Run All*: ejecuta todas las celdas en orden, genera los archivos de salida y guarda los resultados de cada celda dentro del mismo `.ipynb`:

   ```bash
   .venv/bin/jupyter nbconvert --to notebook --execute --inplace analisis_ventas_adventureworks.ipynb --ExecutePreprocessor.timeout=600
   ```

### Windows

Los mismos pasos, cambiando `.venv/bin/` por `.venv\Scripts\` y `python3` por `python`:

```powershell
python -m venv .venv
.venv\Scripts\pip install -r requirements.txt
.venv\Scripts\jupyter notebook analisis_ventas_adventureworks.ipynb
.venv\Scripts\jupyter nbconvert --to notebook --execute --inplace analisis_ventas_adventureworks.ipynb --ExecutePreprocessor.timeout=600
```

## Ejecución en Google Colab

1. Subir `analisis_ventas_adventureworks.ipynb` a Colab.
2. Ejecutar todas las celdas. La celda de la sección 2.2 pide subir los `.csv` de `datos/SL/` y las imágenes `.gif` de `datos/imagenes/`.
3. Las salidas (`datos/CL`, `reporte`, `graficos`) se crean en el panel de archivos de Colab.
