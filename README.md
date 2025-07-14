# Introduction
Este repositorio es una plantilla base para proyectos de ciencia de datos y machine learning en Data GC Naturgy. Proporciona una estructura modular y organizada que facilita el desarrollo, entrenamiento, evaluación y despliegue de modelos, así como la gestión de experimentos y análisis exploratorios. Su objetivo es servir como punto de partida para nuevos proyectos, promoviendo buenas prácticas y reutilización de código.

# Repository Structure

La estructura del repositorio es la siguiente:

```
├── notebooks/
│   ├── general_analysis_template.ipynb
│   └── model_dev_template.ipynb
├── src/
│   ├── config/
│   │   └── config_file.py
│   ├── evaluate/
│   │   └── evaluate.py
│   ├── predict/
│   │   └── predict.py
│   ├── prep/
│   │   └── prep.py
│   ├── register/
│   │   └── register.py
│   ├── train/
│   │   └── train.py
│   └── utils/
│       └── common.py
├── test/
├── requirements.txt
└── README.md
```

- **notebooks/**: Plantillas de notebooks para análisis exploratorio y desarrollo de modelos.
- **src/**: Código fuente principal, organizado en módulos:
  - **config/**: Configuración y parámetros del proyecto.
  - **evaluate/**: Scripts para evaluación de modelos.
  - **predict/**: Scripts para predicción con modelos entrenados.
  - **prep/**: Scripts para preparación y limpieza de datos.
  - **register/**: Registro y gestión de modelos.
  - **train/**: Entrenamiento de modelos.
  - **utils/**: Funciones utilitarias y comunes.
- **test/**: Espacio para tests automatizados.
- **requirements.txt**: Dependencias del proyecto.
- **README.md**: Documentación principal del repositorio.

# Buenas Prácticas de Desarrollo

## Uso de Git

- Trabaja en ramas feature/ o fix/ para nuevas funcionalidades o correcciones.
- Realiza commits atómicos y con mensajes descriptivos (en español o inglés, pero consistentes).
- Antes de hacer push, asegúrate de que el código pasa los tests (esto opcional por ahora) y cumple con las convenciones del proyecto.
- Utiliza pull requests para revisión de código y evita hacer push directo a la rama principal.

## Uso de etiquetas en el código

Utiliza comentarios especiales para marcar tareas pendientes o problemas conocidos:
- `# TODO: descripción de la tarea pendiente`
- `# FIXME: descripción del problema a corregir`
- `# NOTE: información relevante o advertencias`
- `# HACK: soluciones temporales o poco elegantes`

Ejemplo:
```python
# TODO: Añadir validación de datos de entrada
# FIXME: Esta función falla si el archivo no existe
```

## Configuración de pre-commit

Se recomienda usar pre-commit para asegurar la calidad del código antes de cada commit.

1. Instala pre-commit:
   ```
   pip install pre-commit
   ```
2. Añade un archivo `.pre-commit-config.yaml` en la raíz del repositorio con los hooks deseados (por ejemplo, black, flake8, isort, etc.).
3. Instala los hooks en el repositorio:
   ```
   pre-commit install
   ```
4. Los hooks se ejecutarán automáticamente antes de cada commit.

Más información y ejemplos de configuración en: [https://pre-commit.com/](https://pre-commit.com/)
