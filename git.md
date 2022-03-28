# Apuntes GIT

Aca dejare todos los comandos GIT para evitar buscarlos en google.

- [Apuntes GIT](#apuntes-git)
  - [Branch commands](#branch-commands)
  - [Procedimientos](#procedimientos)
    - [Unir ramas](#unir-ramas)
    - [Unir ramas con conflicto](#unir-ramas-con-conflicto)

## Branch commands

- Ver branches

git branch

- Se cambia de rama a la que se esta mencionando

```powershell
git checkout rama-villanos
```

- Crear rama en repositorio remoto.

```powershell
git push origin rama-capitan-loco
```

- Crear una rama nueva:
  
    ```powershell
    git branch rama-villanos
    ```

- Crea rama y se posiciona en ella
  
    ```powershell
    git checkout -b <branch_name>
    ```

- se cambia de rama a la que se esta mencionando

    ```powershell
    git checkout rama-villanos
    ```

- Eliminar una rama. es una buena practica eliminar la rama una vez que se termina de usar.

    ```powershell
    git branch -d rama-villanos
    ```

- Eliminar una rama del remoto

    ```powershell
    git push <remote_name> --delete <branch_name>
    ```

- Saber diferencia entre dos ramas:

git diff rama-villanos master

- Merge con mensaje

    ```powershell
    git merge --no-f rama -m "mensaje"
    ```

## Procedimientos

### Unir ramas

para unir ramas se tiene que posicionarse e la rama en donde se quiere fucionar algo:

```powershell
git checkout master
```

head = apunta al ultimo commit a la rama de al cual estamos

```powershell
git merge rama-villanos
```

merge ramas con commit de mensaje

```powershell
git merge --no-f rama -m "mensaje"
```

### Unir ramas con conflicto

Cuando se van a unir ramas es probable que salga un mensaje:

```powershell
CONFLICT CONTENT: Merge conflict in archivo.txt
automatic merge failed.
```

Dentro del head y el == es el cambio de la rama actual. Dentro del == y el nombre de la rama es el cambio que esta en la rama.

```powershell
<<<<<< HEAD
hola
======
chao
>>>>>> rama
```

Simplemente se deja el texto que se quiere dejar y el resto se borra

```powershell
chao
```
