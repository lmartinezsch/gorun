# gorun
Gorunx is a small tool to watch a directory and rerun a command when certain files change. It's great for automatically running compile/lint/test tasks and for reloading your application when the code changes.


### Reflex - Mantener activa la ejecución de go run

Debe estar instalado Reflex, en caso de que no lo esté:

```
go install github.com/cespare/reflex@latest
```


Luego podremos ejectuar el watch con el siguiente comando:
```
reflex -r '\.go$' go run pkg/cmd/main.go --start-service
```

También podemos crear un script para que el comando sea más simple:
Dentro de la carpeta ~/go/bin creamos el archivo "gorun" con el siguiente contenido:

```
#!/bin/sh

reflex -r '\.go$' go run pkg/cmd/main.go --start-service
```

Luego nos paramos en el directorio del proyecto y ejecutamos "gorun"
