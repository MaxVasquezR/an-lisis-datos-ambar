# Final – Introducción a la Ciencia de Datos: Ambar Company

## Estructura

```
final-ciencia-de-datos/
├── analisis_ventas_ambar.ipynb      # notebook con todo el proceso
├── datos/
│   ├── SL/ARCHIVO_SL.csv            # datos sin limpieza (entrada)
│   └── CL/ARCHIVO_CL.csv            # datos con limpieza (salida del notebook)
├── reporte/
│   └── REPORTE_NO_CORREGIDOS.csv    # datos que no se pudieron corregir (salida del notebook)
├── graficos/                        # gráficos en PNG (salida del notebook)
├── requirements.txt
└── README.md
```

## Ejecución local

1. Instalar dependencias (solo la primera vez):

   ```bash
   python3 -m venv .venv
   .venv/bin/pip install -r requirements.txt
   ```

2. Abrir el notebook y ejecutar todas las celdas en orden (*Run All*):

   ```bash
   .venv/bin/jupyter notebook analisis_ventas_ambar.ipynb
   ```

   También se puede abrir en VS Code eligiendo el intérprete de `.venv`.

En Windows, reemplazar `.venv/bin/` por `.venv\Scripts\` y `python3` por `python`.

## Ejecución en Google Colab

1. Subir `analisis_ventas_ambar.ipynb` a Colab.
2. Ejecutar todas las celdas. La primera celda de código pide subir `datos/SL/ARCHIVO_SL.csv`.
3. Las salidas (`datos/CL`, `reporte`, `graficos`) se crean en el panel de archivos de Colab.
