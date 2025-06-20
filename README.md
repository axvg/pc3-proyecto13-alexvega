### Informacion personal

Nombre: Alex Vega Bendezu

Correo institucional: alex.vega.b@uni.pe

### Informacion del proyecto

Titulo: Gestión de releases local y versionado semántico con monorepo vs. multirepo

Url del repositorio grupal: [https://github.com/grupo10-CC3S2/Proyecto13-PC3](https://github.com/grupo10-CC3S2/Proyecto13-PC3)



### Instrucciones

- Clonar el repositorio individual

```sh
git clone https://github.com/axvg/pc3-proyecto13-alexvega
cd pc3-proyecto13-alexvega

# para obtener el monorepo y su contenido
git submodule update --init
```

- Para correr scripts `tf` y realizar simulacion de recursos de infraestructura, se debe tener instalado `terraform` y `python3`.

- Para el **sprint 1**, se debe ejecutar:

```sh
cd archivos/sprint1
# para cada modulo, por ejemplo network_module
cd network_module
terraform init
terraform plan
terraform apply -auto-approve
```
Y con esto se simula la creacion de un recurso de infraestructura, en este caso una red y se imprime el nombre de la red creada.

- Para los archivos de **sprint 2**, se debe correr los scripts `python` generadores de archivos `tf.json`, se debe ejecutar:

```sh
cd archivos/sprint2
python3 setup.py
```

Esto generara el archivo `tf.json` y luego se ejecuta comandos terraform:
```sh
terraform init
terraform plan
terraform apply -auto-approve
```

Que hara la misma simulacion de creacion de recursos de infraestructura, en este caso una red y servidores y database.

* Para el **sprint 3**, despues de obtener el submodulo, se va al monorepo y se puede ejecutar los comandos que estan en Makefile:

```sh
cd archivos/sprint3/monorepo
make # esto hara un terraform init
make tf-plan
make tf-aa 
```