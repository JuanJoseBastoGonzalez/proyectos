Esta trabajando en un proyecto Git colaborativo y necesitas obtener una visión gráfica y
detallada del historial de commits. Tu tarea es utilizar el comando git log con opciones
específicas para personalizar el formato y presentación de la salida. La salida debe tener
las siguientes especificaciones:

Muestra una representación gráfica del historial de commits

Muestra el hash corto del commit en color rojo

Muestra las referencias (ramas o tags) en las que está involucrado el commit en color
amarillo

Muestra el mensaje del commit.

Muestra la fecha relativa del commit en color verde.

Muestra el hash del commit como un identificador abreviado.

Muestra las fechas de los commits de forma relativa



```
git config --global alias.graph 'log --graph --pretty=format:"%Cred%h%Creset %C(yellow)%d%Creset %s %Cgreen(%ar)%Creset %C(auto)%h%Creset"'

```

con el git config --global hacemos que los cambios se realicen de manera global.

con el alias .graph le agregamos un nombre de ejecución en este caso seria git graph

con el (') indican el inicio y el final de de una cadena de texto. para definir como quieres que se precente la información de cada commit.

con el --pretty=format: permite personalizar la información del commit



 %Cred: Cambia el color del texto que le sigue a rojo.
%h: Muestra el hash corto del commit.
%Creset: Restablece el color del texto a su estado original.
%C(yellow): Cambia el color del texto que le sigue a amarillo.
%d: Muestra las referencias (ramas o tags) en las que está involucrado el commit.
%s: Muestra el mensaje del commit.
%Cgreen: Cambia el color del texto que le sigue a verde.
(%ar): Muestra la fecha relativa del commit.
%C(auto): Configura automáticamente el color del texto según las configuraciones del terminal. En este caso, se utiliza para mostrar el hash del commit en un color predeterminado.
%h: Muestra nuevamente el hash corto del commit.
%Creset: Restablece el color del texto a su estado original.



Estas trabajas frecuentemente con el comando git log -1 HEAD para obtener detalles sobre
el último commit en la rama actual. Sin embargo, encuentras que escribir este comando
completo es un poco tedioso. Quieres simplificarlo creando un alias personalizado.

Tu tarea es utilizar el comando git config para crear un alias llamado last que represente el
comando git log -1 HEAD.



```
git config --global alias.last 'log -1 HEAD'

```

alias.last: Estás creando un alias llamado last.

'log -1 HEAD': Esta es la definición del alias. Indica que cuando escribas git last, Git ejecutará el comando git log -1 HEAD. Vamos a desglosar esta parte:

log: Es el comando principal de registro de Git, que muestra el historial de commits.
-1: Limita el número de commits a mostrar a solo el último.
HEAD: Se refiere al commit actual en la rama actual

### 

Imagina que deseas simplificar el proceso de editar la configuración global de Git. Tu tarea
es utilizar el comando git config para crear un alias que te permita abrir fácilmente la
configuración global en tu editor de texto preferido. Ejecuta el comando para crear un alias
llamado ec que cumpla con la especificación dada.

```
git config --global alias.ec '!git config --global --edit'

```

para este usamos (!) para ejecutar comandos de la shell 

--global: Indica que la configuración se aplicará a nivel global, afectando a todos los repositorios de Git en tu sistema.

alias.ec: Estamos definiendo un alias llamado ec.

'!git config --global --edit': Este es el comando que se ejecutará cuando escribas git ec. Aquí tienes una explicación detallada:

!: En Git, el símbolo de exclamación ! indica que se debe ejecutar un comando de la shell. En este caso, el comando de la shell es git config --global --edit.

git config --global --edit: Este comando abre tu archivo de configuración global de Git en el editor de texto predeterminado. La opción --edit se utiliza para editar la configuración.



```
git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(auto)%h%C(white)%s%C(reset)-%C(dim blue)-%an%C(reset)'"
```

se llama con un git lg

el %c(auto)%h = genera una abreviación del has

el %C(white)%s%C(reset) le pone color blanco a los comentarios 

el %C(dim blue)-%an%C(reset) pone en azul el nombre del usuario 