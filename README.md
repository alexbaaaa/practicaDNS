# Práctica DNS

## Creación de las máquinas virtuales

Creamos las máquinas virtuales mediante un archivo `Vagrantfile` con la configuración deseada. 

## Configuración de la provisión

Añadimos una provisión en el archivo para instalar `bind9` en cada una de las máquinas.
Con la siguiente linea: 
```ruby
    apt-get install -y bind9 dnsutils
```
## Comprobación de las máquinas

Iniciamos las maquinas virtuales con:  
```shell
    vagrant init
``` 
Seguido nos conectamos mediante ssh a cada una de ellas

```shell
    vagrant ssh venus
``` 
![Imagen ssh Venus](../img/sshVenus.PNG)

```shell
    vagrant ssh tierra
``` 
![Imagen ssh Tierra](../img/sshTierra.PNG)