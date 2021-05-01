__Protocolo:__

+ Daniel Felipe Villa Rengifo

+ Lenguaje Utilizado: R

+ Tema: Creación, documentación e invocación de funciones en R.

+ Fuentes Consultadas:
  [function: Function Definition](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/function)
  [Function Documentation](https://campus.datacamp.com/courses/intermediate-r/chapter-3-functions?ex=2)


# Creación de Funciones:

Podemos crear funciones definidas por el usuario en R. Son específicas para lo que un usuario quiere y una vez creadas pueden ser utilizadas como las funciones incorporadas.

Con el comando `function(args){body function}`

```{r}
# Definimos una función que muestre un mensaje que reibe como argumento:
message("Podemos crear funciones definidas por el usuario en R. Son específicas para lo que un usuario quiere y una vez creadas pueden ser utilizadas como las funciones incorporadas. A continuación se muestra un ejemplo de cómo se crea y utiliza una función.")

crear <- function(post){
  cat("\n", post)
}

crear("Hola vengo desde la función en R")

# Mi segunda Functión:
message("\n# Mi segunda Función:")


## Calculemos la hipotenusa de un triangulo rectangulo:
message("'\n## Calculemos la hipotenusa de un triangulo rectangulo:")

h <- function(ca,co){
  # Calcula según dado los catetos ca = adyacentes y co = opuestos
  hipo = sqrt((ca^2)+(co^2))
  cat("\n", "La Hipotenusa de", "ca:",ca,"\n", "co:",co, "\n", "Es...", hipo)
  
}

h(1,2)
```


# Documentar una función:

La verdad busque mucha información al respecto y lo unico que hallé fueron metodos más avanzador para documentar (PAQUETES). 

+ https://mauriciogtec.github.io/rGallery/entries/tutoriales/crear_paquetes/crear_paq    ete.html


```{r}
# Documentar una función:
message("\n# Documentar una función:")

## definiremos como no se docuemnta una función:

recorrido <- function(x){
  # Esta función recorre los valores a X & sacar inmediantamente imprime el valorde cada value de la lista:
  for(i in x){
    b <- i^2
    print(i)
  }
}
  
print(recorrido)

# con comillas podrias de igual manera presentar un tipo de documentación:
message("\n#con comillas podrias de igual manera presentar un tipo de documentación:")

## Encontrar en un vector el min y max de una muestra:
message("\n## Encontrar en un vector el min, media, ordenado y max de una muestra:")

s <- sample(30, size = 20, replace = TRUE)

## efinimos nuestra función:
message("\n## efinimos nuestra función:")

f <- function(vec){
  cat("\nMedia:", mean(vec))
  cat("\nValor maximo ", max(vec))
  cat("\nValor minimo ", min(vec))
  cat("\nDe menor a mayor", sort(vec, decreasing = FALSE))
  cat("\nDe mayor a menor", sort(vec, decreasing = TRUE))
}

print(f)

f(s)
```

# Invocación:

podemos llamar a una función de varias maneras:

+ Supliendo el argumento:

```{r}
# utilizamos a crear para invocar a la función en un argumento especifico:
message("\n# utilizamos a crear para invocar a la función en un argumento especifico:")

print(crear)

crear("Invocar por argumento")
```
+ Llamando funciones sin argumento

```{r}
# Definimos una función sin argumento:
message("\n# Definimos una función sin argumento:")

sin_arg <- function(){
  # Como podemos evidenciar no tenemos una entrada,(en este caso) solo una salida
  c <- 0
  while(c<=25){
    print("No a la Reforma Tributaria")
    c = c + 1
  }
}

sin_arg()
```



+ Invocar funciones con valores de los argumentos:

```{r}
# Extrapolamos l función h:
message("\n# Extrapolamos l función h:")
print(h)


# Asi se ponen valores a una función:
message("\n# Asi se ponen valores a una función:")

print("h(5, 10), cateto adyasente, cateto opuesto")

h(5,10)

# tambien podemos definirlas como:
message("\n# tambien podemos definirlas como:")

h(ca= 4, co = 5)

# Vemos que podriamos hacerlo de forma contrario y ver si son iguales:
message("\n# Vemos que podriamos hacerlo de forma contrario y ver si son iguales:")

h(co = 5, ca= 4)

"Nota: le cuesta más al sistema dar la respuesta."
h(co = 0.5,  ca = 2)



```

