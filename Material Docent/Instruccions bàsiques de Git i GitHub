# MANUAL D'INSTRUCCIONS Git + GitHub [^note]
**Git** és un **sistema de control de versions** per a codi font. Està pensat per tal de facilitar el desenvolupament d'aplicacions en equip.
Donat el desenvolupament d'un projecte o aplicació, cada desenvolupador/a que hi participi tindrà una còpia del codi al seu ordinador. A aquesta còpia la anomenarem *repositori local*.
Donat un moment, cada persona de l'equip pot tenir una versió diferent del codi de l'aplicació en el seu PC local.

L'escenari ideal és que cada desenvolupador/a treballi sobre una branch diferent per tal de no trepitjar-se. **No hauriem de treballar mai sobre la branch master o main.** Ja que aquesta branca la considerarem **producció**.

Quan estem desenvolupant canvis, sempre ho fem sobre arxius del repositori local perquè és el nostre entorn de desenvolupament.
Els canvis que fa cada desenvolupador/a sobre el codi només seràn visibles per a ell/a mateix/a i no afectaran a la resta de companys/es de l'equip de desenvolupament.

Al mateix temps, a nivell d'equip de desenvolupadors/es tindrem un únic *repositori remot* a la plataforma GitHub (o una altra) on s'hi guardarà la versió "bona" del codi. 
Dit d'una altra manera, imaginem que el nostre software ja està a està al mercat i la gent el fa servir, doncs la versió que estarà publicada a la branch main o master del GitHub serà l'última versió bona que s'ha pujat a producció.
Podem fer el símil amb Google Docs o OneDrive de Microsoft on hi guardem documents word, power point, excel, etc al núvol i fem treballs conjuntament amb altres persones. Doncs amb git és com si ens decarreguèssim la versió del word que hi ha penjada i l'editem en local fins que la nostra part ja està acabada i aleshores la publiquem de tornada al núvol per tal de que la resta de companys la vegin.
A diferència del funcionament del Google Drive i del OneDrive, no desenvolupem canvis en temps real sobre la versió final que hi ha penjada al núvol.

Si desenvolupèssim sobre el repositori remot, a part de que seria més lent perquè el codi està penjat al núvol, seria delicat perquè estariem fent canvis sobre la versió final que aplicaria sobre el codi de tots els companys i aleshores ens podriem trepitjar la feina.

Cal diferenciar i identificar correctament què és la còpia de fitxers en local ***repositori local*** vs què és la copia de fitxers del ***repositori remot***. Els dos repositoris només coincidiràn quan tots els canvis estiguin en commit i després fer un merge.

Però pot ser que varies persones de l'equip de desenvolupament tinguin versions diferents del mateix fitxer perquè tots l'estant editant al mateix temps. Això causaria un conflicte de versions i s'haurà de gestionar construïnt una versió final del codi entre les línies de codi aportades per cada desenvolupador/a.

# Comandes de Git des de terminal (tots els SO):
## a. Crear nou repositori local i afegir-hi un fitxer:
### Primerament podem comprovar la versió instal·lada de Git al nostre ordinador:
```git --version```

### Set del nom d'usuari de GitHub que usarà el nostre pc editant la variable global user.name (només cal fer-ho un cop)
```git config --global user.name "nomUsuariGitHub"```

### Set de l'email d'usuari que s'usarà el nostre pc editant la variable global user.email (només cal fer-ho un cop)
```git config --global user.email "nomUsuariGitHub@domain.cat"```

### Inicialitza un nou repositori local de git dins del directori actual on estem ubicats amb el terminal
```git init```

### Podem crear un document nou i modificar-lo, el fitxer es estarà en estat "modified" dins del repositori de git.
#### En Windows OS: 
```"hola" > instruccions_git.txt```

#### En MacOS:
```touch instruccions_git.txt```

### Podem comprovar l'estat del versionat de fitxers amb la comanda:
```git status```

### Afegir un document dins del repositori un cop està acabat i apunt per a ser pujat amb la nova versió. Només veiem els canvis en local.
El fitxer es troba en estat **staged** (en zona de proves)
```git add instruccions_git.txt```

### Per desfer un add acabat de fer d'un fitxer en concret podem usar:
Treu el fitxer de la zona de proves
```git reset instruccions_git.txt```

### Per afegir tots els arxius modificats de la carpeta del working directory per a ser pujats al repositori:
```git add .```

### Per desfer tots els add fets:
```git reset .```

### Fer commit
Pujar la  nova versió de codi de tot els fitxers que s'han afegit anteriorment a **staged** per tal de generar un _checkpoint_ o _snapshot_ del codi en local i tenir els canvis segurs i guardats.
Usarem --m per afegir comentaris sobre el commit explicant els canvis que estem pujant. Git ens obliga a posar-hi comentari.
El fitxer es trobarà en estat **commited** (confirmat)

```git commit instruccions_git.txt --m "Commit de la primera versió del fitxer instruccions_git.txt"```

## b. Editar en local un fitxer ja existent dins del repositori:
### Per veure tots els canvis que s'han fet fins a data d'avui fitxers afegits, pujats, modificats...
```git log --stat```

### Per veure l'estat del repositori
```git status```

### Checkout file:
**Abans de començar a editar** un fitxer ja existent, per fer-ho sota control d'errors, pot ser interessant que descarregarem la seva última versió confirmada: (Compte! Si ja hem començat a editar el fitxer i fem checkout, perdrem els nostres canvis).
```git checkout nomFitxer.txt```

### Per marcar només un arxiu i posar-lo a la zona de proves previ a per ser confirmat:
```git add nomFitxer.txt```

### Un cop hem acabat de modificar un fitxer ja existent en local, podem confirmar-lo:
```git commit nomFitxer.txt -m "Comentari"```

### Per marcar tots els arxius modificats per ser pujats. (Els posem a la "staging area", "àrea d'assaig"):
```git add .```

### Commit massiu:
Nota: Només s'afegiran al repositori els fitxers que haguem afegit a la staging area amb add conforme ja estan llestos per a ser guardats com a versió final dins del repositori local.
```git commit . -m "Comentari dels canvis pujats"```

### Si volem fer un add + commit de tots els arxius a la vegada podem usar:
```git commit . -am "Add + commit"```

### Els canvis encara no són visibles per a la resta de desenvolupadors. El commit de la versió final del canvi que hem fet, només aplica al nostre repositori local. Per tal de que es publiqui al repositori remot, haurem de fer ús de:
```git push```

### Extra: Quan tenim un fitxer en edició dins del working directory i es troba en un estat diferent al de l'últim commit del repositori, podem revertir els canvis enrere fins a deixar-lo en l'estat de l'últim commit que es troba dins del repositori:
```git restore nomFitxer```

### Si volem eliminar un fitxer del working directory local i del repositori de la branca on ens trobem (deixa de trackejar els seus canvis i també l'elimina del disc):
#### Primer el marquem per ser eliminat:
```git rm nomFitxer```

#### Confirmem l'eliminació
```git commit . -m "Delete file nomFitxer"```

## c. Concepte de branch (branca):
Dins del repositori de codi, podem crear diferents linies de treball **_branches_** per tal de:
1. Mantenir sempre una versió completa i final del nostre codi a producció ('master' branch o 'main' branch)
2. Tenir una copia de codi de la master branch en desenvolupament (develop branch). Aquesta contindrà un conjunt de noves funcionalitats a ser pujades conjuntament al final d'un sprint i aconseguir així un increment del software a la master branch.
3. Tenir sub-branques que provenen de develop branch amb desenvolupament de subfuncionalitats autoconcloents i independents (feature branch). Això és el que farem típicament per tal de desenvolupar una nova funcionalitat derivada d'un User Story de l'Sprint Backlog.

### Amb la instrucció següent podem veure totes les branques que hi ha dins del repository (ens marcarà amb * sobre la que estem treballant actualment sobre el nostre repositori local):
```git branch```

### Per a crear una nova branca anomenada per exemple "develop" farem:
```git branch develop```

Cada branca del repositori projecte pot tenir diferents estats de desenvolupament i, per tant, tenir diferents versions del codi que s'està desenvolupant.

### Per a treballar a sobre una versió concreta del codi, sel·leccionarem la branca existent sobre la qual volem treballar (equivalent a USE de base de dades):
```git checkout develop```

### Per a esborrar tota una branca del projecte (COMPTE!), primer haurem de sel·leccionar una altre perquè no podem esborrar una branca sobre la qual hi estem treballant.
Tampoc podrem esborrar una branca que tingui canvis pendents de codi de ser pujats a la branca master (o a una altra branca).
```git branch -d develop```

### Si tot i així, volem esborrar una branca amb canvis de codi pendents:
```git branch -D develop```

### Per a crear una nova branca i situar-nos a treballar sobre ella directament:
Fa create i checkout a la vegada.
```git checkout -B develop```

### Per a pujar els canvis d'una branca de desenvolupament sobre a una altra branca. Típicament des d'una branca feature cap a una branca develop quan ja hem acabat de desenvolupar un User Story.
1. Hem de fer add i commit dels canvis a pujar a la branca feature.
	```
	git checkout feature
	git add . 
	git commit . -m "Commit all changes in feature branch"
	```

2. Hem de moure'ns cap a la branca de destí:
	```
	git checkout develop
	```
	
3. Fer merge del codi de feature cap a develop:
	```
	git merge feature
	```

**Nota:** Fins aquí tots els canvis fets, només seràn presents en el nostre repositori local.

## d. Per a clonar (descarregar en local) i sincronitzar un repositori remot del portal github:
Si el repositori que volem descarregar (clonar) es troba **estat _"públic"_**, el podrem clonar sense problemes.
En canvi, si es troba en **estat _"privat"_** pot ser necessari que el propietari/a del repositori remot generi una **personal access token** des de github web Settings/Developer settings/Personal access tokens i ens la comparteixi:
Instruccions sobre com crear [personal access token](https://docs.github.com/en/enterprise-cloud@latest/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token "Creating a personal access token")

### Amb el terminal, navegar fins a una carpeta del nostre PC local on vulguem descarregar el codi del repositori remot. La carpeta escollida es convertirà en la carpeta de la nostra còpia del repositori local.
Per exemple:
```git clone https://github.com/raimonizard/git.git```

Després de clonar, ja hauriem de tenir tot el codi del repositori remot copiat al repositori local.

### Tot i així, podem fer un pull per forçar que es decarreguin al repo local els últims canvis fets al repositori remot:
```git pull```

Més info [aquí](https://juancadh.medium.com/conectar-carpeta-local-con-repositorio-de-github-8d983798998e)


## e. Per afegir una carpeta sencera amb el seu contingutdel repositori local al repositori remot:
1. Iniciar ssh GitHub terminal
2. Anar a la carpeta on es troba la subcarpeta

Pot ser necessari posar el nom de la subcarpeta entre "cometes":
```
git add nomSubCarpeta
git commit nomSubCarpeta -m "Pujada de la carpeta nomSubCarpeta"
git push
```

Més info [aquí](https://stackoverflow.com/questions/44306606/how-to-git-add-a-whole-folder)

## f. Revertir un commit
Si hem fet un commit en local o en remot i el volem desfer, podem usar la comanda **git revert**
Aquesta comanda ens serveix per retornar el nostre repositori a un estat anterior abans de fer un determinat commit.

Per comprovar a quin commit volem tornar, podem veure els commits fets usant:
```
git log --oneline
```

Ens mostrarà el conjunt de commits fets sobre el repositori que estem treballant. Per exemple:
![image](https://user-images.githubusercontent.com/97727989/217358630-ef6a7967-3584-4594-969d-7dd6ff6fe149.png)


Fixem-nos amb els ids de cada commit. Aquests ens permeten identificar un punt del passat del repositori al qual podem tornar.

Per exemple, si volem tornar al commit *8c87bca fix: sprite layer, turbo mode*, ho farem així:
```
git revert 8c87bca
```

Un cop fet, per a confirmar els canvis fets, usarem:
```
git add .
git commit . -m "chore: revert to 8c87bca"
```

Si volem que els canvis apliquin al remot:
```
git push
```

Més info a: https://www.freecodecamp.org/news/git-reverting-to-previous-commit-how-to-revert-to-last-commit/


---

## EXEMPLES:
### Exemple per clonar un repo extern i afegir arxiu:
1. Anar a una carpeta local del nostre PC
2. Al terminal anar a la carpeta i escriure: git clone + la url de https del repositori remot.
Exemple: ```git clone https://github.com/raimonizard/java-basic-examples.git```
3. Ara tenim els arxius del repositori remot al repositori local del nostre PC.
4. Afegim un arxiu a la carpeta del nostre repositori local del PC on hem clonat el repositori. Al terminal escriurem: ```git add NomArxiuNou.java``` (o l'extensió que sigui)
6. Ara tenim l'arxiu nou **pendent de ser confirmat**.
7. Al terminal escriurem: ```git commit NomArxiuNou.java```
8. Ara tenim l'arxiu nou confirmat an el nostre repositori local. **Els canvis encara no són visibles per la resta.**
9. Ara escriurem al terminal: ```git push``` per tal de pujar el nou arxiu al repositori remot. (Per poder fer git push necessitarem loguejar-nos amb l'usuari propietari del repositori remot o tenir un personal access token del propietari o que el repositori remot estigui configurat amb uns permisos publics que permetin editar sense credencials).
10. Ara hem publicat els nostres canvis de codi per a tothom i tenim els dos repositoris (local i remot) iguals. Ho podem comprovar fent: ```git status```

### Exemple per modificar un arxiu del repositori local:
1. Si tenim un repositori remot clonat al local, abans de començar a modificar un arxiu en local, ens hauriem d'assegurar que la còpia del nostre repositori local estigui igual al del repositori remot (ja que la versió del codi que "mana" és la que hi ha en el repositori remot ja que és la versió de la qual la resta de desenvolupadors en tenen visibilitat).
Per a fer-ho, al terminal escriurem: ```git pull``` per comprovar si estem al dia en el repositori local.
	1. Pot ser interessant **crear una nova _branch_** abans de fer canvis per tal de tenir tot el nostre proper desenvolupament agrupat. Per fer-ho: ```git checkout -B nomBranch``` (Això crea el branch i apunta cap a ella, els propers canvis es faran en aquesta branch).
	2. Si hem creat una **nova branch**, per **pujar-la al repo remot** hem de fer: ```git push --set-upstream origin nomBranch```
	3. Per comprovar on estrem treballant: ```git branch``` (la que surt amb * és sobre la qual estem treballant ara)
2. Un cop estem al dia, abans de començar a editar codi en local, al terminal escriurem: ```git checkout NomFitxer.java``` Per tal d'assegurar-nos que la versió del fitxer que tenim en local és la mateixa que l'última versió pujada a la branca del repositori remot on estem treballant.
3. Ara fem els canvis del fitxer que vulguem. Un cop estigui acabat de modificar, fem: ```git add NomFitxer.java``` per tal d'afegir-lo a la propera confirmació de codi (si tinguèssim més d'un fitxer pel qual volem pujar els canvis, també li fariem add).
Podem afegir tots els fitxers modificats estant a la carpeta root del projecte i fer: ```git add .```
4. Un cop fet, pugem els canvis afegits amb git commit i ens demanarà afegir un comentari. Podem fer-ho directament fent: ```git commit NomFitxer -m "Comentari"```
Per fer commit de tots els fitxers podem fer: ```git commit . -m "Comentari del canvi"```
5. Podem comprovar les diferències entre el repo remot i el local fent: ```git status```
6. Per publicar els canvis commitejants al repositori local: ```git push``` pujarà els canvis del local cap al remot.
7. Podem comprovar que local i remot ara estan igual fent: ```git status```
8. Per publicar els canvis a la branch principal, hem de moure'ns cap a la branca de destí: ```git checkout main```
9. Estant a la branch de destí, fer merge del codi de la branch on estàvem treballant cap a la main: ```git merge branchNova```
10. Si tot ha anat bé i no hi ha hagut conflictes de codi amb companys/es del projecte, ara podríem esborrar la branch de desenvolupament amb seguretat.

---

## RESUM DE COMANDES DEL TERMINAL DE GIT:
### Per establir el nom d'usuari de github del desenvolupador/a d'aquest pc és un en concret:
```git config --global user.name "UserName"```

### Per establir que l'email del desenvolupador/a d'aquest pc és un en concret:
```git config --global user.email "username@domain.cat"```

### Per comprovar la versió de git que es troba instal·lada en el nostre pc:
```git --version```

### Per afegir arxius o carpetas a la staging area del repositori local (pendents de ser confirmats):
Escriurem nom de l'arxiu o carpeta que volem passar a la staging area o usarem el punt . per a especificar que volem posar tots els arxius que hagin modificats a la staging area:
```git add .```

### Per confirmar en el repositori local tots els arxius afegits a la stating area:
Especificarem nom de l'arxiu o carperta que volem confirmar o usarem el punt . per a especificar que volem confirmar tots els arxius que es troben a la staging area:
```git commit . -m "Comentari"```

### Per comprovar estat del versionat dels arxius entre repositori local vs repositori remot:
```git status```


### Per actualitzar el repo local des del repo remot:
```git fetch```

### Per actualitzar el repo local i també el workind directory _(els canvis en local sense commit seràn sobre-escrits)_ des del repo remot:
```git pull```

### Per pujar i publicar els canvis commitejats al repositori local cap al repositori remot:
```git push```

### Per tal de que no demani credencials al fer git push:
```git config --local credential.interactive "never"```

### Per visualitzar les ***branches*** disponibles
```git branch```

### Per crear una ***branch*** nova:
```git branch newBranch```

### Per moure'ns cap a una ***branch*** existent:
```git checkout existingBranch```

### Per fer merge d'una ***branch*** cap a merge:
```
git checkout master
git merge existing branch
```

### Per fer retornar el repositori a un commit anterior:
```
git revert id del commit
```

---

[^note]: By [@github/raimonizard](https://github.com/raimonizard "Raimon Izard GitHub") - Jan 2023 
