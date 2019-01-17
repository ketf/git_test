Versionierung mit GIT und Konventionen
=========================================
Autor: K. Fricke (fricke@bafg.de)

Datum: 16.01.2019


Installation von GIT
--------------------
\\mt1.fs.bafg.de\Software\Allgemein\Versionierung\Git\Git-2.15.0-64-bit.exe
- Destination Location: ggf. D:\NutzerProgramme\Git
- Select Components: Windows Explorer integration, Git LFS, Associate .git* configuration files with the default text editor, Associate .sh file to be run with Bash
- Start Menu Folder: Git
- Use Git from the Windows Command Prompt
- Use the OpenSSL library (?)
- Checkout as-is, commit as-is
- Use Windows' default console window
- Enable file system caching
- Enable Git Credetial Manager

Installation von TortoiseGit 
------------------------------------------------------------
(Benutzeroberfläche für Git)

\\mt1.fs.bafg.de\Software\Allgemein\Versionierung\Git\TortoiseGit-2.7.0.0-64bit.msi

folgt...

Erstelle initiales GIT repository auf Server
------------------------------------------------------------
- rMK: Git Create repository here > Uncheck "Make it bare"
- URL / UNC-Pfad speichern/kopieren

Erstelle "lokales" GIT repository
----------------------------------------
(Bsp. https://git-scm.com/docs/gitrepository-layout, 
https://medium.freecodecamp.org/understanding-git-for-real-by-exploring-the-git-directory-1e079c15b807)
- in den gewählten Ordner gehen
- rMK: Git Create repository here... > Check "Make it bare" > vorgegebene Ordner erscheinen 
- rMK > Git > Settings > Edit global .gitconfig: Nutzername und Email aktualisieren
- rMK: Git Sync > 
	- Remote [Manage] URL "\\mt1.fs.bafg.de\fachdaten\AG\Fernerkundung\Intern\_Tools_Entwicklung\git" 
	- [Add New/Save] as "origin"
	- Remote Branch auswählen [...]
	- [Pull]
- rMK Git Add + Commit
- rMK: Git Commit > Message!! > Set author!! > Set author date!! > Commit & Push
- push: ggf. Push all branches > Local: master > Destination remote origin (\\mt1.fs.bafg.de\fachdaten\AG\Fernerkundung\Intern\_Tools_Entwicklung\git) > Uncheck Autoload Putty Key


Ordnerstruktur Programmierskripte
----------------------------------------
(Bsp. https://github.com/andygrunwald/DigitalKanban, https://github.com/kriasoft/Folder-Structure-Conventions)

- lib (Allgemeine Bibliotheken)
- project_1
  - lib_project_1
  - doc (Text- oder Markdowndokumente)
  - res (Dateien wie häufig verwendete Bilder, Logos, Vektordateien, keine Bildergallerie!)
  - conf (Konfigurationsdateien für Skripte, zB. *.yaml, conda-Umgebungskonfigurationen)
  - test (Tests für eigene Skripte)
- project_2
  - [...]
- [...]
- Readme.md

Namens-Konventionen für Skripte in GIT
---------------------------------------
(s. https://docs.python-guide.org/writing/structure/)
- master: stabil, beta getestet, dient als backup und Produkt
- test: stabil, alpha getestet
- feature: im Entwicklungsmodus, nicht stabil, temporär
