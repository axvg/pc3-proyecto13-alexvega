 Contribuciones de Alex Vega

## Sprint 1
- **2025-06-06 (Dia 1):** Cree la estructura de directorios base para el monorepo (`iac/monorepo/`) y sus módulos (`network_module`, `compute_module`, `storage_module`), incluyendo los archivos terraform iniciales vacios.
  *   **Commit:** `304da566cfab444cb80a22af070f76530393e5ce`
  *   **Tarea en kanban board:** [https://github.com/grupo10-CC3S2/Proyecto13-PC3/issues/1](https://github.com/grupo10-CC3S2/Proyecto13-PC3/issues/1)


- **2025-06-07 (Dia 2):** Se agrega contenido basico para archivos terraform en el modulo `network_module` en los archivos `variables.tf` y `main.tf`, en este modulo se simulara la creacion de un recurso imprimiendo variables con `local-exec` de terraform, tambien se agrega el archivo `main.tf` en directorio raiz para importar este modulo.
  *   **Commits:** `efd1fa171d4f1bdbb4b4e32ca6f3da0cfb546bca`, `c0aba05ed36f6f48b5446aae2944f80a338a6803`, `47ec01c6f7a898eaf49879260ae250008400702f`,
  `d6532d88f02bd8312852c9c66a3daa5941f5aaf9`
  *   **Tarea en kanban board:** [https://github.com/grupo10-CC3S2/Proyecto13-PC3/issues/6](https://github.com/grupo10-CC3S2/Proyecto13-PC3/issues/6)


- **2025-06-08 (Dia 3):** Se agregan archivos iniciales de python para la creacion del archivo `tf.json` que crearan los mismos recursos que el modulo network, Ademas se agrega el archivo `setup.py` en el directorio raiz que importa a la clase factory de network y crea el archivo json.
  *   **Commit:** `abf4fa6aa7050b91dd003eddb89ac3dd8f10c7fc`,`175f330b8267a0e6506615404a122f70ba0b2160`
  *   **Tarea en kanban board:** [https://github.com/grupo10-CC3S2/Proyecto13-PC3/issues/7](https://github.com/grupo10-CC3S2/Proyecto13-PC3/issues/7)

## Sprint 2
- **2025-06-10 (Dia 4):** 
- Se arreglo el nombre del modulo network ya que se usara para imports en python y el caracter `-` no es aceptado.
  - **Commit**: `3b1cea50b940680e121f9f97dd96ac8dd06c0a77`, `8e3cec82a66db7c2ba341653058aec78ad4ba465`

- Se modifican archivos para la simulacion de creacion de servidores usando `compute_module`:
  - **Commit**: `e460439b4696acef94fb609aeedb774b4da694d6`

- Se agregan archivos iniciales para los modulo compute y storage que realizaran la creacion de archivos `tf.json`.
  - **Commit**: `a8688629e77416c89bc975cc6221fdda1261ec25`

- Se agregan archivos de setup inicial usando imports de modulos de `python` para monorepo
  - **Commit**: `dc077d44921a6c29f5389829c429d5b16890f8e9`


- **2025-06-11 (Dia 5)**:

- Agrega variable `instance_count` y logica para crear un numero dado de servers usando `compute_module`
  - **Commit**: `89f43cb82689b4a3ddf3723dd583d7df763d2a72`

- Se agregan valores de output para `storage_module` con la ruta de la db y `name` de network creada
  - **Commit**: `a2e022277dfcde5ad237a2235ec6fc0c86fbca7a`, `5758dc80187ded85e8ecc4ef0baebc0475332556`

- Se crea `main.tf` que realiza el import de modulos de archivos `tf` para simulacion de instancias de infraestructura para monorepo
  - **Commit**: `cce57ea253f73169e6c48cfc5a60b14a6a876883`

- **2025-06-13 (Dia 6)**:

- Usando `local_exec` se simula creacion de db y se imprime el nombre de `db` y dependencias `network` y `server`
- **Commit**: `f0b9df37b7ecc9f29bc224c0e97437b3cdf589f6`

- Usando `depends_on` en el archivo principal `main.tf`, se define la dependencia entre modulos, esto para mostrar aristas de grafo en la imagen generada pro `terraform graph`.
- **Commit**: `eb27c7e32f53a4a4df357dfb5e074fdf81e801f6`

- Agrega `CHANGELOG` inicial con tags iniciales para monorepo.
- **Commit**: `b8215a1a9c1d8e34edea2034d4c69f8691b9bc13`

- **2025-06-14 (Dia 7)**:
- Agrega `instance_count` para crear cierto numero de servidores para clase Factory `ServerFactoryModule`.
- **Commit**: `ee10a3bcdea169b50403f5b00612598848969d9b`

- **Pull request**: [https://github.com/grupo10-CC3S2/Proyecto13-PC3/pull/17](https://github.com/grupo10-CC3S2/Proyecto13-PC3/pull/17)
- **Tarea en kanban board**: [https://github.com/grupo10-CC3S2/Proyecto13-PC3/issues/18](https://github.com/grupo10-CC3S2/Proyecto13-PC3/issues/18)

## Sprint 3
- **2025-06-16 (Dia 8)**:
- Se borra el monorepo del repositorio del proyecto y se agrega como submodulo, esto para obtener un correcto versionamiento de modulos y tener todos los modulos dentro del monorepo.

- **2025-06-17 (Dia 9)**:
- Se agregan archivos de configuracion para pytest, librerias necesarias, se re-estructura los directorios para mayor claridad entre modulos e `imports` de `python` y `terraform`
- **Pull request**: [https://github.com/grupo10-CC3S2/monorepo/pull/2](https://github.com/grupo10-CC3S2/monorepo/pull/2)

- **2025-06-18 (Dia 10)**:
- Se agregan `fixtures` y unit tests para los modulos con validaciones basicas de los metodos de clases factory, estos tests se crean en directorio `tests/unit`, tests para las version `v0.4.0`
- **Pull request**: [https://github.com/grupo10-CC3S2/monorepo/pull/4](https://github.com/grupo10-CC3S2/monorepo/pull/4)

- **2025-06-19 (Dia 11)**:
- Se modifican las variables de los 3 modulos y se modifican los outputs para mostrar info resumida de cada recurso creado usando los archivos `tf`.
- **Pull request**: [https://github.com/grupo10-CC3S2/monorepo/pull/6](https://github.com/grupo10-CC3S2/monorepo/pull/6)

- Se modifican los scripts finales de simulacion de los 3 modulos, esto son: `check_network.sh` que imprime que la configuracion de red es correcta, `compute_tool.py` que imprime informacion de cada servidor creado y usando `random,randint` genera un valor de ID aletario y `backup_storage.sh` que simula backup creando y modificando archivos txt con logs y con conteo de ejecuciones, version de modulos `v0.8.0`
- **Pull request**: [https://github.com/grupo10-CC3S2/monorepo/pull/8](https://github.com/grupo10-CC3S2/monorepo/pull/8)

- Se agregan un test de contrato para el modulo `network_module` que usando una clase `Facade` valida si el otuput de `Factory` es correcto, se modifican test unitarios para test parametrizados.
- Se agregan tests unitarios con validaciones de puertos y numero de instancias usando lenguaje DSL de terraform para los 3 modulos.
- Se modifican los test unitarios para agrega validaciones de puertos y numero de instancias.
- **Pull request**: [https://github.com/grupo10-CC3S2/monorepo/pull/10](https://github.com/grupo10-CC3S2/monorepo/pull/10)

- Se agregan validaciones en modulos python y terraform para puertos y numero de instancias para la version `v1.0.0`
- **Pull request**: [https://github.com/grupo10-CC3S2/monorepo/pull/12](https://github.com/grupo10-CC3S2/monorepo/pull/12)
