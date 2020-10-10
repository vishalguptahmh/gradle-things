# gradle-things


### declaring a variable
```
def x = 5
def vari= "String"
def arr=["hey","buddy"]
```
### calling varible in string
```
def x = 5
def firstString = """Hello World ! ${x}
 my 
first 
string
"""
println firstString
````
output 
```
 Hello World ! 5
 my 
first 
string
```

### String interpolationn
```
def mystring = "hey buddy"
println(firstString.toUpperCase())
```

## closers
```
def echoIt = {}
println echoIt() //invoke the closer
println echoIt // print as string 
```
```
def echoIt = {parameter -> 
println(parameter)
}
echoIt("hey closer")
```

### define type of parameter
```
def echoIt = {String parameter -> 
println(parameter)
}
```
-----
### you can define closer by its name also
```
Closure echoIt = {String parameter -> 
println(parameter)
}
echoIt("hey")
```
-----
```
def multipLyByTwo(Closure){
Closure() *2
}
println multipLyByTwo {6}
```
-----

### pass multiple argument with closer
```
def multipLyByTwo(factor,Closure){
Closure() *factor
}

println multipLyByTwo(5,{6})
or 
multipLyByTwo 5 , {7}
```

### closure : adding things without changing class
```
class Car {
    String engineName
    Car(name){
        engineName = name
     }

    def invokeExternal(Closure c ){
        c.delegate = this
        c()
    }
}

def obj= new Car("Ferari")
println obj.engineName
obj.invokeExternal{ println "my own code with changing class"}
```
