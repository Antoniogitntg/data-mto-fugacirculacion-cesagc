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

> **IMPORTANTE:** Todas las funciones y clases deben documentarse usando el formato [numpydoc](https://numpydoc.readthedocs.io/en/latest/format.html) para facilitar la comprensión y el mantenimiento del código. Ejemplo de docstring numpydoc:
>
> ```python
> def ejemplo_funcion(param1, param2):
>     \"\"\"Resumen breve de la función.
>
>     Parameters
>     ----------
>     param1 : tipo
>         Descripción de param1.
>     param2 : tipo
>         Descripción de param2.
>
>     Returns
>     -------
>     tipo
>         Descripción del valor de retorno.
>     \"\"\"
> ```

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

## Configuración y hooks de pre-commit

Este repositorio utiliza [pre-commit](https://pre-commit.com/) para asegurar la calidad y seguridad del código antes de cada commit. Los hooks están definidos en `.pre-commit-config.yaml` y se instalan automáticamente al ejecutar `pre-commit install`.

### Instalación y uso

1. Instala pre-commit:
   ```bash
   pip install pre-commit
   ```
2. Instala los hooks en el repositorio:
   ```bash
   pre-commit install
   ```
3. Los hooks se ejecutarán automáticamente antes de cada commit. Para ejecutarlos manualmente sobre todos los archivos:
   ```bash
   pre-commit run --all-files
   ```

### Hooks configurados

| Hook                          | Descripción                                                                 |
|-------------------------------|-----------------------------------------------------------------------------|
| check-added-large-files       | Evita agregar archivos grandes (>500KB)                                     |
| check-yaml                    | Valida archivos YAML                                                        |
| check-toml                    | Valida archivos TOML                                                        |
| end-of-file-fixer             | Asegura que los archivos terminen en una línea vacía                        |
| trailing-whitespace           | Elimina espacios al final de línea                                          |
| requirements-txt-fixer        | Ordena y limpia requirements.txt                                            |
| detect-private-key            | Detecta claves privadas en el código                                        |
| double-quote-string-fixer     | Cambia comillas dobles por simples                                          |
| ruff                          | Linter rápido tipo flake8/pycodestyle para Python                           |
| ruff-format                   | Formateador de código Python (estilo black, pero más rápido)                |
| gitleaks                      | Detecta credenciales y secretos en el código                               |
| mypy                          | Análisis estático de tipos (type hints) para Python                         |

**Recomendación:** No ignores los avisos de los hooks. Si un hook falla, revisa el mensaje y corrige el problema antes de hacer commit.

Más información sobre cada hook y su configuración en el archivo `.pre-commit-config.yaml` y en la [documentación oficial de pre-commit](https://pre-commit.com/).
