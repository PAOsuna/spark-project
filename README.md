#  Spark Scala Docker Environment


Entorno **Docker** para desarrollo y análisis de datos con **Apache Spark** configurado con para realizar análisis de datos utilizando **Scala**.

---

## Características
Apache Spark 3.4.3 con Hadoop 3

Scala 2.12 (compatible con Spark 3.4.3)

Java 11 (Eclipse Temurin JRE)

Optimizado para análisis de CSV y datos estructurados

Configuración lista para múltiples proyectos

Spark Shell interactivo con montaje de volúmenes

---

## Prerrequisitos
### Para WSL2 con Ubuntu
WSL2 instalado y configurado

Distribución Ubuntu (20.04/22.04 recomendado)

Docker Engine instalado en WSL2

---

##  Estructura del Proyecto

spark-projects/
├── docker/
│ └── Dockerfile
├── .gitignore
├── LICENSE.txt
└── README.md

---

## Construcción de la Imagen Docker

Construye la imagen Docker con:


`docker build -t spark-scala .`

Esto creará una imagen Docker llamada spark-scala con Apache Spark 3.4.3 y Hadoop 3.

---

## Ejecutar el Contenedor

Para iniciar un contenedor de Spark Shell:

`docker run -it --rm -p 4040:4040 spark-scala`

Esto abrirá el Spark Shell (`spark-shell`) con soporte local (`--master local[*]`).

---


## Interfaz Web de Spark

Durante la ejecución del contenedor, Spark expone una interfaz de monitoreo accesible en tu navegador:

`http://localhost:4040`

Aquí podrás visualizar información sobre las tareas y trabajos en ejecución.

---

## Licencia

Este proyecto está bajo la licencia especificada en LICENSE.txt.