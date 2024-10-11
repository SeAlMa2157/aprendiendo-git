Readme taller git sebastian albaran maya

inicialice el repositorio: el primer paso fue crear el respositorio local en mi maquina usando el siguiente comando: 
git init "aprendiendo-comandos-git"

Configure mi nombre y correo electronico para los commits con los comandos git config --global user.name y git config --global user.email.
git config --global user.name "Sebastian Albaran Maya"
git config --global user.email sebastian.albaran@correounivalle.edu.co

Creacion de la rama master: pude visualizar que se presento un problema ya que  Git no creo la rama master por defecto, asi que la cree manualmente con el comando: 
git checkout -b master

Crear una rama feature: Cree una nueva rama llamada feature utilizando:
git checkout -b feature

Realice varios commits modificando un archivo llamado archivo.txt:
echo "Texto inicial" > archivo.txt
git add archivo.txt
git commit -m "Commit inicial"

luego realice un segundo commit:
echo "Texto agregado en feature" >> archivo.txt
git commit -am "Segundo commit en feature"

por ultimo cree el ultimo commit:
echo "Tercer cambio" >> archivo.txt
git commit -am "Tercer commit en feature"

Para realizar una correccion urgente, cree la rama hotfix y agregue texto dentro del archivo archivo.txt:

git checkout -b hotfix
echo "Correccion urgente" >> archivo.txt
git commit -am "Hotfix"


Despues, reverti el merge para practicar con rebase:
git reset --hard HEAD~1
git rebase feature


Merge y rebase: Intente hacer un merge de la rama feature en master, pero estaba ya actualizado:
git checkout master
git merge feature

Cherry-pick: Use cherry-pick para aplicar un cambio critico de la rama hotfix a master sin hacer un merge completo:

Cree la rama hotfix:

git checkout -b hotfix
echo "Correccion urgente" >> archivo.txt
git commit -am "Hotfix"


Luego hice cherry-pick de hotfix en master:

git checkout master
git cherry-pick hotfix


Genere un conflicto intencional modificando el mismo archivo conflicto.txt tanto en la rama feature como en master:

En feature:

echo "Cambio en feature" > conflicto.txt
git commit -am "Cambio en feature"


luego pase a master e hice lo mismo

echo "Cambio en master" > conflicto.txt
git commit -am "Cambio en master"

Al intentar fusionar las ramas, se produjo un conflicto. el cual se resolvio manualmente el conflicto en conflicto.txt, 
luego agregue el archivo resuelto al area de preparacion y complete el merge con un commit final.




