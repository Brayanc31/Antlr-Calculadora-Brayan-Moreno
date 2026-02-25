
# Calculadora con ANTLR

Este repositorio implementa una calculadora simple que evalúa expresiones aritméticas con variables, basada en el ejemplo del libro "The Definitive ANTLR 4 Reference". Permite operaciones de suma, resta, multiplicación, división, paréntesis y asignación de variables.

## Requisitos

- **Java 8 o superior** (OpenJDK u Oracle JDK)
- Conexión a internet para descargar el JAR de ANTLR (opcional, si ya lo tienes)

## Archivos incluidos

- `LabeledExpr.g4` – Gramática de la calculadora
- `Calc.java` – Programa principal
- `EvalVisitor.java` – Visitor que evalúa las expresiones
- `prueba.txt` – Archivo de ejemplo con expresiones

## Instrucciones de uso

### 1. Descargar el JAR completo de ANTLR

En la misma carpeta del proyecto, ejecuta:

```bash
wget https://www.antlr.org/download/antlr-4.13.1-complete.jar
```

Si no tienes `wget`, descarga el archivo manualmente desde [https://www.antlr.org/download/](https://www.antlr.org/download/) y cópialo a la carpeta.

### 2. Generar el parser y el visitor

```bash
java -jar antlr-4.13.1-complete.jar -no-listener -visitor LabeledExpr.g4
```

Esto creará los archivos Java necesarios: lexer, parser, visitor y base visitor.

### 3. Compilar el código

```bash
javac -cp ".:antlr-4.13.1-complete.jar" *.java
```

### 4. Ejecutar con un archivo de prueba

El archivo `prueba.txt` contiene las siguientes líneas:

```
193
a=5
b=6
a+b*2
(1+2)*3
```

Ejecuta el programa con:

```bash
java -cp ".:antlr-4.13.1-complete.jar" Calc prueba.txt
```

La salida esperada es:

```
193
17
9
```

## Uso interactivo

Si ejecutas el programa sin argumentos, leerá desde la entrada estándar:

```bash
java -cp ".:antlr-4.13.1-complete.jar" Calc
```

Luego escribe expresiones (una por línea) y presiona `Ctrl+D` (Linux/macOS) o `Ctrl+Z` (Windows) para terminar.



