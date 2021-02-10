# COMANDOS DE GIT - GITHUB

## Configuracion de Git: Usuario y Correo

- Para configurar el nombre de usuario.
    ```sh
    git config --global user.name "Edincodes"
    ```
- Para configurar el correo que tomara GitHub del usuario.
    ```sh
    git config --global user.email edincodes@spacex.com
    ```

## Comandos para empezar a trabajar con Git.

- Para empezar a utilizar Git e inciar el rastreo de todos los archivos de nuestro proyecto.
    ```sh
    git init
    ```
- Para ver el estado de nuestros archivos.
    ```sh
    git status
    ```
- Existen varias formas de agregar los archivos al entornpo de trabajo:
    - Para agregar archivos por nombres.
        ```sh
        git add nombrearchivo.extension
        ```
    - Para agregar todos los archivos de golpe.
        ```sh
        git add -A (.)
        ``` 
    - Para agregar todos los archivos de golpe.
        ```sh
        git add -A
        ``` 
    - Para agregar todos los archivos de golpe.
        ```sh
        git add .
        ``` 
- Para crear un punto de control de nuestro código. "Un commit" con su descripción
    ```sh
    git commit -m "descripción para tu commit agregado"
    ```
- Existen varias formas de visualizar los commits hechos:

    - Para ver la información de cada commit hecho: Commit, Author, Date
        ```sh
        git log
        ```
    - Para ver en una sola linea los comentarios de cada commit hecho.
        ```sh
        git log --oneline
        ```
    - Para ver los commits con una estrucutura de estrellas
        ```sh
        git log --graph
        ```
    - Esto combina --oneline y --graph
        ```sh
        git log --oneline --graph
        ```
- Personalizar un log con el "Git Alias" es una combinacion de varias caracteristicas que tiene Git.

    - Como lo hacemos? ejecutamos el comando:
        ```sh
        git config --global alias.superlog "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
        ```
        > Este nos creara un alias con el nombre "superlog" teniendo varias caracterisiticas de Git que nos permitira poder vizualizar mejor nuestros commits. Gracias a la personalización.
    - Ahora solo necesitas el siguiente comando:
        ```sh
        git superlog
        ```
- Para revertir los cambios de un archivo.
    ```sh
    git checkout -- files.js
    ```
- Para ver las diferencias en los archivos
    ```sh
    git diff
    ```
- Para ver cuantos ramas tenemos en el proyecto y donde estamos trabajando.
    ```sh
    git branch
    ```
- Es para crear una nueva rama (alternativa del proyecto original).
    ```sh
    git branch nombrederama
    ```
- Para clonar repositorios desde GitHub.
    ```sh
    git clone https://github.com/edincodes/Instalaciones-React.git
    ```
- Para Actualizar repositorios.
    ```sh
    git push -u
    ```
- Para borrar archivos
    ```sh
    git rm -r files.js
    ```


    ## Git reset
- Git reset Soft
    - "Elimina" los commits posteriores al commit al que estas haciendo el reset
    - Conserva los cambios en el stage area
    - Conserva los cambios que tengas en tus archivos (working directory)
    ```sh
    git reset --soft [commit]
    ```
- Git reset mixed
    - "Elimina" los commits posteriores al commit al que estas haciendo el reset
    - Deshace los cambios en el stage area
    - Conserva los cambios que tengas en tus archivos (working directory)
    ```sh
    git reset --mixed [commit]
    ```
- Git reset hard
    - "Elimina" los commits posteriores al commit al que estas haciendo el reset
    - Deshace los cambios en el stage area
    - Deshace los cambios que tengas en tus archivos (working directory)
    ```sh
    git reset --hard [commit]
    ```
    > Cuando usar "git reset --mixed" cuando vemos que tenemos varios commits y que podemos encapsularlo todos ellos en un solo commit, debemos tomar el id del commit base y aparti de alli a los commits posteriores los unira, esto mostrara cambios en el archivo lo que tenemos que agregarlos con un "git add -A" . Y estara listo para hacer el nuevo commit de union.

    >En el caso de "git reset --soft" es similar que el "git reset --mixed" la unica diferencia es que esta No mostrara cambio en los archivos, lo que indica que estaria listo para hacer el nuevo commit de union.
## Ramas
- Para crear una nueva rama y cambiarnos a ella al mismo tiempo.
    ```sh
    git checkout -b nombredelanuevarama
    ```
- Para cambiar de rama, y trabajar en otra.
    ```sh
    git checkout nombredelarama
    ```
- Para cambiar el nombre de una rama.
    ```sh
    git branch -m nombredelaramaacambiar nuevonombreparalarama
    ```
- Elimina una rama, la rama especificada con el nombre.
    ```sh
    git brach -d nombredelarama
    ```
- Este nos permite restaurar los cambios que ya han sido agregados al staged Area
    ```sh
    git restore --staged nombredelarchivo
    ```
- Este nos permite restaurar los cambios que aun no hemos agregados al Staged Area
    ```sh
    git restore nombredelarchivo
    ```
- Esto nos permite fusionar la rama, (Tienes que estar situado en la rama principal)
    ```sh
    git merge nombredelaramaafusionar
    ```
- Este nos permite eliminar una rama que no necesitemos y que podriamos eliminar cuando ayamos hecho el debido merge con la rama principal.
    ```sh
    git branch -d nombredelaramaaeliminar
    ```
## Etiquetas
- Agregar etiquetas: Nombre de etiqueta y una descripcion
    ```sh
    git tag VersionTag -m "Etiqueta Letra G"
    ```
- Subir y actualizar nuestra etiquetas en GitHub
    ```sh
    git push --tags
    ```
- Eliminar etiqueta
    ```sh
    git tag -d nombredeetiqueta
    ```
- Este nos permite colocar etiquetas en commits especificos, podemos escoger el id del commit y hacer una etiqueta en ella.
    ```sh
    git tag -a nombredeetiqueta idcommit
    ```
## Alias en Git
- Para ver las propiedades de nuestras alias creadas
    ```sh
    git config --global alias.superlog
    ```

# Cuando iniciamos un repositorio:
- 
    ```sh
    git init
    git add README.md
    git commit -m "first commit"
    git branch -M main
    git remote add origin https://github.com/edincodes/ComandosGit.git
    git push -u origin main
    ```
Recuerdar revisar los [Fundamentos de Git]

[Fundamentos de Git]: <https://git-scm.com/book/es/v2/Fundamentos-de-Git-Obteniendo-un-repositorio-Git>



