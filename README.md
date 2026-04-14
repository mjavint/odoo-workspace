# Odoo DevContainer

> Esta plantilla es para instalar, configurar y desplegar un entorno de desarrollo de odoo con DevContainer

## Uso de la plantilla con Copier

Esta plantilla utiliza [Copier](https://copier.readthedocs.io/) para generar proyectos personalizados de Odoo.

### Instalación de Copier

```shell
pip install copier
# o con uv
uv tool install copier
```

### Crear un nuevo proyecto

```shell
copier copy /ruta/a/esta/plantilla /ruta/destino/nuevo-proyecto
```

O si la plantilla está en GitHub:

```shell
copier copy gh:usuario/repo /ruta/destino/nuevo-proyecto
```

### Variables de la plantilla

Durante la creación del proyecto, se te preguntará:

1. **project_name**: Nombre del proyecto (se usará para el nombre del contenedor)
   - Valor por defecto: `odoo-project`

2. **odoo_version**: Versión de Odoo a utilizar
   - Opciones: `19.0`, `18.0`, `17.0`
   - Valor por defecto: `19.0`

3. **python_version**: Versión de Python a utilizar
   - Opciones: `3.12`, `3.10`
   - Valor por defecto: `3.12`

### Actualizar un proyecto existente

Para actualizar un proyecto con cambios de la plantilla:

```shell
copier update /ruta/destino/proyecto
```

## Configuración inicial

* Crear la network(`shared-net`) si es la primera vez o no existe en el sistema

```shell
docker network create shared-net
```

* Crear el volumen(`odoo-data`) si es la primera vez o no existe en el sistema

```shell
docker volume create odoo-data
```

* Ajustar la ruta de `ODOO_SERVER` en `.devcontainer/.env` según tu instalación local de Odoo
