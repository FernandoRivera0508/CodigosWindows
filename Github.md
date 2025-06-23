# GUARDAR ACTUALIZACIONES EN GITHUB

- **Crear un repositorio local en la carpeta donde está el archivo**
git init

- **Verificar el estado de los archivos**
git status

- **Añadir el archivo al repositorio**
git add nombre-del-archivo.md 
git add . (Guarda todos los archivos modificados)

- **Hacer un commit**
git commit -m "Primer commit con archivo de apuntes .md"

- **Si ya se creo un repositorio remoto (por ejemplo en GitHub), conectarlo así:**
git initgit remote add origin https://github.com/tu_usuario/tu_repositorio.git

- **Hacer un commit**
git commit -m "Primer commit con archivo de apuntes .md"

- **Enviar el archivo al repositorio remoto**
git push -u origin "rama principal"

- **Si el nombre de la rama es diferente a main (por ejemplo, master o windows-apuntes), se verifica así**
git branch
