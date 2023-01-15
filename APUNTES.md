# LISTA
d = ["hola", "soy", "paula"]
    - Se pueden mezclar distintos tipos
    - Se pueden editar los valores
    - Hay muchisimas funciones asociadas

# TUPLA
tuple = ("hola", 3, "paula")
    - Se pueden mezclar valores. 
    - Es INMUTABLE, no se puede editar ningun valor
    - Funciones .count para devolver el nuemro de veces que hay un valor
    - Funcion .index te devuelve la primera posición que tiene ese valor

# DICCIONARIO
dic = {"key1": 1, "key2":[1,2,3,4]}
    - Parejas de clave valor
    - La clave suele ser un string
    - Los valores pueden ser de cualquier tipos
    - No sigue un orden
    - Hay muchisimas funciones asociadas (.append, .pop)


# SET
```
my_set = set()
my_set.add(1)
```

- Colección de valores ÚNICOS, no se pueden repetir valores.
Por ejemplo, puedes tener una lista con [1,1,1,1,1,2,2,2,3,3,3], si hacemos un set(), nos va a quedar {1,2,3}


# FILES
- myfile.read() -> te devuelve el contenido del fichero. Si vuelves a llamar a la funcion te lo devuelve vacío porque está apuntando al final.
- myfile.seek(0) -> vuelve al principio asique ya se puede volver a leer el fichero
- myfile.readlines() -> te lo devuelve linea a linea.
- myfile.close()
## Modes
- mode = 'r' is read only
- mode = 'w' is write only
- mode = 'a' is append only
- mode 'r+' is reading and writing
- mode = 'w+' is writing and reading
```
    with open('my_new_file.txt', mode='r') as f:
        print(f.read())
```

# LOGICAL OPERATORS
- and or not
- 2 < 3 > 2 es lo mismo que 2 < 3 and 3 > 2  

# IF STATEMENT
- funciona con identaciones
```
    if condition:
        do this
    elif other_condition:
        do that
    else:
        do this
```

# FOR LOOPS
```
my_iterable=[1,2,3]
for i in my_iterable:
    print(i)
```
## with tupples
```
tup = [(1,2), (3,4), (5,6)]
for i in tup:
    print(i) -> esto va a imprimir la tupla entera
for (a,b) in tup:
    print(a)
    print(b) -> esto va a imprimir el segundo elemento de la tupla
```

## with dictionaries
```
d = {"k1":1, "k2":2, "k3":3}
when you iterate through dictionaries you do it in the keys
for item in d.values():
    print(item) -> imprime los valores
for key,values in d.item()
    print(key)
    print(values)
```

## with string
```
for i in "Hello World": 
    print("hola") -> lo va a imprimir el numero de veces que carácteres tiene el string
for _ in "Hello World": -> hace lo mismo que la de antes
```

# WHILE LOOP
```
    while x < 5:
        print("lo que sea")
    else:
```
Se puede utilizar:
- break: breaks out of the current closests enclosing loop
- continue: goes to the top of the closest enclosing loop
- pass: does nothing at all
```
    for i in x:
        pass -> no se podría dejar el for vacío, con esto deja seguir ejecutando lo siguiente fuera del for
``` 
```
    mystring = "Sammy"
    for i in mystring:
        if letter = "a":
            continue -> con esto conseguimos que cuando la letra sea la "a" el bucle vuelve al ppio asique no la imprime
        print(i)
```   
```
    mystring = "Sammy"
    for i in mystring:
        if letter = "a":
            break -> finaliza el bucle donde se haya quedado
        print(i)
```

# operational commands
range(init, end, steps)
list(range(0,11,2)) -> crea una lista con los valores

```
word = "abcde"
for item in enumerate(word):
    print(item) -> esto va a devolver la posicion y el valor de esa posicion
```
```
word = "abcd"
for index,value in enumerate(word):
```
Con zip solo se junta siguiendo la logitud del mas pequeño
```
mylist1 = [1,2,3]
mylist2 = [a,b,c]
zip(mylist1, mylist2) -> lo junta y te devuelvela posicion de memoria
for item in zip(mylist1, mylist2):
    print(item) -> te va a imprimir tuplas (1,a)....
```
Para buscar se puede utilizar con cualquier tipo
```
"x" in [1,2,3] -> busca el valor x en la lista y te devuele un boolean
```
Para importar funciones de una librería
```
from random import shuffle
```
Para poder meter valores
```
name = input("What is your name ?") -> esto siempre hace un cast a string
```

# Formar listas
Se puede formar una lista de esta forma
```
mystring="Hola"
mylist=[]
for letter in mystring:
    mylist.append(letter)
```
Sería lo mismo hacer:
```
mystring="Hola"
mylist=[letter for letter in mystring]
```

        
# FUNCTIONS
Son como las funciones normales, se pueden tener valores de entrada ydevolver valores
- No se recomienda imprimir cosas dentro de funciones
- todo dentro de la funcion tiene que ir indentado
- a los parámetros se les puede poner un valor por defecto
```
def name_of_function(num1=2, num2):
    return(num1+num2)
```
## Arguments
Qué sucede si queremos pasar muchos parámetros? no podemos darles valores por defecto a tantos, por lo que utlizarmos args y kargs
 - podemos poner el nombre que queramos mientras tenga un * delante para una tupla
 - en el caso del diccionario solo tiene que llevar ** delante
 - con `*args` nos devuelve una tupla
 - con `**kargs` nos devuelve un diccionario
```
def myfunc(*args): -> con esto podemos poner todos los argumentos que queramos
    return sum(args) * 0.05
def myfunc(*args, **kwargs)
```

# LAMBDA FUNCTIONS
## MAP
map (func, *iterations)
si quiero aplicar la funcion de square a una lista de numeros:
```
map(square, my_nums)-> esto te devuelve la dirección de memoria donde se guarda, puedes poner un for para recorrerlos

list(map(square, my_nums)) -> te lo guarda en una lista
```
- esto tambien se puede aplicar a otros tipos, como strings
## FILTER
esto filtra en funcion de una funcion que le pases, por ejemplo
Si tienes una funcion que detecta los numeros pares
```
list(filter(check_even, mynums)) -> te devuelve los numeros pares de tu lista
```
## LAMBDA
una funcion normal sería
```
def square(num): return num ** 2
```
para pasarlo a funcion lambda, lo que quedaría es:
```
lambda num: num ** 2
```
podría asignarse a una variable
```
square = lambda num: num ** 2
square(5)
```
Esto es util si una funcion solo la voy a utlizar una vez, para qué ocupar mucho espacio creando una funcion, pues utilizo lambda. Por ejemplo:
```
list(map(lambda num: num ** 2, mynums))
list(filter(lambda num: num%2 == 0, mynums))
```

## -------------------- CLASS ---------------
Para declarar una clase:
- la funcion __init__ es la que se va a ejecutar cuando declare el objeto
```
class Dog():
    #CLASS ATTRIBUTE
    specie = "mammal"

    def __init__(self,breed):
        self.breed = breed

my_dog = Dog(bredd="Lab")

```
Tambien se pueden heredar funciones de las clases, por ejemplo:
```
class Animal():
    def __init__(self):
        print("animal created)
    def who_am_i().
        print("i am an animal)

class Dog(Animal):
    def __init__(self):
        Animal.__init__(self)
        print("dog created")
```
Haciendo eso, todas las funciones de Animal pueden ser utilizadas por Dog, o se pueden sobreescribir dentro de la clase Dog

## Metodos especiales
Hay metodos especiales, ya que por ejemplo si intentas imprimir un objeto de una clase o quieres ver su longitud, te va a imprimir la dirección de memoria en la que está.
```
class Book():
    def __init__(self,title, pages, author):
        self.title = title
        self.pages = pages
        self.author = author
    def __str__(self):
        return f"{self.title} by {self.author}"
    def __len__(self):
        return self.pages
    def __del__(self)
        print("The object has been deleted")
b = Book("Python rocks", "Jose", 200)
```
Por tanto, cuando hacemos `print(b)`o `str(b)`nos va a imprimir esa frase o podemos imprimir la longitud `len(b)`
- tambien podemos eliminar el objeto `del b`