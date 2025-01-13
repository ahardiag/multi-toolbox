# Shell Bash toolbox

<!-- TOC -->

- [Shell Bash toolbox](#shell-bash-toolbox)
  - [Jupyter Notebook settings](#jupyter-notebook-settings)
      - [Add the extension for Table of Contents](#add-the-extension-for-table-of-contents)
      - [Run a server independently on the terminal window:](#run-a-server-independently-on-the-terminal-window)
      - [Delete a server (method1):](#delete-a-server-method1)
      - [Delete a server (method2):](#delete-a-server-method2)
      - [Delete a server (method3):](#delete-a-server-method3)
  - [BASH Syntax](#bash-syntax)
      - [List last modifications in a file](#list-last-modifications-in-a-file)
      - [Redirect error on output](#redirect-error-on-output)
      - [Connaitre le chemin d’accès d’une application exécutable](#connaitre-le-chemin-daccès-dune-application-exécutable)
      - [Effacer tous les fichiers du répertoire courant sauf fichier1 et fichier2](#effacer-tous-les-fichiers-du-répertoire-courant-sauf-fichier1-et-fichier2)
      - [Affiche un court texte sur le terminal et peut concaténer deux fichiers](#affiche-un-court-texte-sur-le-terminal-et-peut-concaténer-deux-fichiers)
      - [Donne des infos sur nombre de lignes, mots et octets d’un fichier](#donne-des-infos-sur-nombre-de-lignes-mots-et-octets-dun-fichier)
      - [Afficher chemin du répertoire courant](#afficher-chemin-du-répertoire-courant)
      - [Ajouter du texte à la fin d’ un fichier (non) protégé](#ajouter-du-texte-à-la-fin-d-un-fichier-non-protégé)
      - [Afficher le chemin d’un fichier](#afficher-le-chemin-dun-fichier)
      - [Connaitre la taille d’un répertoire](#connaitre-la-taille-dun-répertoire)
      - [Connaitre la taille des fichiers](#connaitre-la-taille-des-fichiers)
      - [Lien symbolique vers .local/bin/](#lien-symbolique-vers-localbin)
      - [Donner la valeur d’une variable d’environnnement](#donner-la-valeur-dune-variable-denvironnnement)
    - [Arguments in bash scripts](#arguments-in-bash-scripts)
      - [Manual usage](#manual-usage)
      - [Getops simple example](#getops-simple-example)
      - [Compulsory arguments](#compulsory-arguments)
      - [Deactivate/Activate wildcard recognition](#deactivateactivate-wildcard-recognition)
    - [Conditions in bash languages](#conditions-in-bash-languages)
      - [Bash yes/no test](#bash-yesno-test)
      - [exit  from a _while_ loop](#exit--from-a-while-loop)
      - [Tester si un fichier,répertoire existe (bash)](#tester-si-un-fichierrépertoire-existe-bash)
      - [Wildcard in bash](#wildcard-in-bash)
      - [Créer des alias sur shell](#créer-des-alias-sur-shell)
      - [Connaître répartition de la mémoire disque](#connaître-répartition-de-la-mémoire-disque)
      - [Suppprimer/insérer les lignes d’un fichier](#suppprimerinsérer-les-lignes-dun-fichier)
    - [Syntax AWK](#syntax-awk)
      - [Pass variables to awk](#pass-variables-to-awk)
      - [Get the string between one/two separator with awk](#get-the-string-between-onetwo-separator-with-awk)
      - [Replace one column of a file f1 with the column of another file f2](#replace-one-column-of-a-file-f1-with-the-column-of-another-file-f2)
      - [Get only the part of a file between two matching term (excluding matching lines and including them)](#get-only-the-part-of-a-file-between-two-matching-term-excluding-matching-lines-and-including-them)
      - [Transform a ouptut in column to a unique row with a white space separation](#transform-a-ouptut-in-column-to-a-unique-row-with-a-white-space-separation)
      - [Récupère des données utilisant la la ligne,colonne, motif avec awk](#récupère-des-données-utilisant-la-la-lignecolonne-motif-avec-awk)
    - [Archive extraction (`tar`)](#archive-extraction-tar)
      - [Updating a existing tar file by adding/updating a subdirectory; create the archive it if not exist](#updating-a-existing-tar-file-by-addingupdating-a-subdirectory-create-the-archive-it-if-not-exist)
      - [Untar an archive folder in another name](#untar-an-archive-folder-in-another-name)
      - [Untar only a sub directory of a compressed file (and forget the first two parents)](#untar-only-a-sub-directory-of-a-compressed-file-and-forget-the-first-two-parents)
      - [Untar by excluding files](#untar-by-excluding-files)
      - [Créer tar/Extraire tar](#créer-tarextraire-tar)
      - [Erase files after extracting](#erase-files-after-extracting)
      - [Extract and exclude a subdirectory or file](#extract-and-exclude-a-subdirectory-or-file)
      - [Extract only a subfolder of a large `.tar` archive](#extract-only-a-subfolder-of-a-large-tar-archive)
      - [Display the size of a subfolder/file inside a `tar` archive without extracting it](#display-the-size-of-a-subfolderfile-inside-a-tar-archive-without-extracting-it)
    - [Command ls](#command-ls)
      - [List all folders in the current directory](#list-all-folders-in-the-current-directory)
    - [Command find](#command-find)
      - [Case sensitive](#case-sensitive)
      - [Case insensitive](#case-insensitive)
      - [Find a file and execute a complex bash command ;](#find-a-file-and-execute-a-complex-bash-command-)
      - [Return name with relative path wrt mydir with all directories and not tar files](#return-name-with-relative-path-wrt-mydir-with-all-directories-and-not-tar-files)
      - [Find a match pattern and replace next line](#find-a-match-pattern-and-replace-next-line)
      - [Find a match pattern and replace next string](#find-a-match-pattern-and-replace-next-string)
      - [Remove files with wildcard except another pattern](#remove-files-with-wildcard-except-another-pattern)
      - [Find a file with a pattern on the filename and a word to search in the file](#find-a-file-with-a-pattern-on-the-filename-and-a-word-to-search-in-the-file)
      - [Find a file matching pattern and find lines in the file where is located a word-to-search](#find-a-file-matching-pattern-and-find-lines-in-the-file-where-is-located-a-word-to-search)
    - [Command grep](#command-grep)
      - [Return lines of a files that (do not) start by ‘ ‘, #, ;](#return-lines-of-a-files-that-do-not-start-by----)
      - [Catch several matching term in any order with grep (through perl)](#catch-several-matching-term-in-any-order-with-grep-through-perl)
      - [Find a filename and the line number where a pattern appears in all directories](#find-a-filename-and-the-line-number-where-a-pattern-appears-in-all-directories)
    - [Command sed](#command-sed)
      - [Delete the lines lying between PATTERN-1 and PATTERN-2 , excluding the lines containing these patterns (from here)](#delete-the-lines-lying-between-pattern-1-and-pattern-2--excluding-the-lines-containing-these-patterns-from-here)
      - [Delete the lines lying between PATTERN-1 and PATTERN-2 , including the lines containing these patterns](#delete-the-lines-lying-between-pattern-1-and-pattern-2--including-the-lines-containing-these-patterns)
      - [Delete all the lines after PATTERN-2, use this](#delete-all-the-lines-after-pattern-2-use-this)
      - [Do sed command (ex add a symbol “\_” in the 17th position) only in a range of rows (between line1 and line2)](#do-sed-command-ex-add-a-symbol-_-in-the-17th-position-only-in-a-range-of-rows-between-line1-and-line2)
      - [Delete 10 lines after matching a term](#delete-10-lines-after-matching-a-term)
      - [Delete all lines before/after a matching term](#delete-all-lines-beforeafter-a-matching-term)
      - [Select lines in a sub-part of a file between two matching terms](#select-lines-in-a-sub-part-of-a-file-between-two-matching-terms)
      - [Select all lines after a matching terms](#select-all-lines-after-a-matching-terms)
      - [Insert several lines after matching a term in a file](#insert-several-lines-after-matching-a-term-in-a-file)
      - [Comment with “;” a line after match one or several term in a line](#comment-with--a-line-after-match-one-or-several-term-in-a-line)
      - [Insert a character at a given column number in all lines with match (17 in the example)](#insert-a-character-at-a-given-column-number-in-all-lines-with-match-17-in-the-example)
      - [Match a string and do a replacement between two strings in the lines where it matchs](#match-a-string-and-do-a-replacement-between-two-strings-in-the-lines-where-it-matchs)
      - [Sort only a part of a file wrt the 2nd column delimited by two lines using matching terms](#sort-only-a-part-of-a-file-wrt-the-2nd-column-delimited-by-two-lines-using-matching-terms)
      - [Insert the content of a file1 in another file2 before the matching term](#insert-the-content-of-a-file1-in-another-file2-before-the-matching-term)
      - [Insert the content of a file1 in another file2 after the matching term](#insert-the-content-of-a-file1-in-another-file2-after-the-matching-term)
      - [Insert the content of a file1 in another file2 at a given line (do not work for line 0)](#insert-the-content-of-a-file1-in-another-file2-at-a-given-line-do-not-work-for-line-0)
      - [Insérer ligne après matcher un motif](#insérer-ligne-après-matcher-un-motif)
      - [Insérer ligne avant matcher un motif](#insérer-ligne-avant-matcher-un-motif)
      - [Replacer toute une line après avoir match un motif](#replacer-toute-une-line-après-avoir-match-un-motif)
    - [command curl](#command-curl)
      - [Zip and download a sub-directory of a github repo](#zip-and-download-a-sub-directory-of-a-github-repo)
    - [Sorting tools](#sorting-tools)
      - [Sort a list of files depending on a part of the string name](#sort-a-list-of-files-depending-on-a-part-of-the-string-name)
      - [Sort a list of filename in the good order including 1-9 numbers](#sort-a-list-of-filename-in-the-good-order-including-1-9-numbers)
    - [Command convert](#command-convert)
      - [Reduce the size of an image](#reduce-the-size-of-an-image)
    - [Other commands](#other-commands)
      - [Récupérer un mot dans une suite de mots](#récupérer-un-mot-dans-une-suite-de-mots)
      - [Change a line into a column](#change-a-line-into-a-column)
      - [Date](#date)
    - [Series of commands](#series-of-commands)
      - [Afficher la ligne d’un fichier en utilisant le numéro de la ligne](#afficher-la-ligne-dun-fichier-en-utilisant-le-numéro-de-la-ligne)
      - [Trouver un programme affiché dans Gnome (touche Windows)](#trouver-un-programme-affiché-dans-gnome-touche-windows)
      - [Renommer plusieurs fichiers avec wildcard](#renommer-plusieurs-fichiers-avec-wildcard)
      - [Vérifier si un argument est fourni avec l’executable en bash](#vérifier-si-un-argument-est-fourni-avec-lexecutable-en-bash)
      - [Remplacer du texte dan un template avec sed](#remplacer-du-texte-dan-un-template-avec-sed)
      - [Changer les couleurs par défaut de la commande ls (LS\_COLORS variable)](#changer-les-couleurs-par-défaut-de-la-commande-ls-ls_colors-variable)
      - [Eviter les avertissements Warning avec GTK sur un terminal](#eviter-les-avertissements-warning-avec-gtk-sur-un-terminal)
      - [Lancer un processus en arrière-plan sans tuer le processus en quittant le terminal](#lancer-un-processus-en-arrière-plan-sans-tuer-le-processus-en-quittant-le-terminal)
  - [History](#history)
    - [Bash](#bash)
    - [Fish](#fish)
  - [Tunnel SSH](#tunnel-ssh)
      - [Create a directory through ssh](#create-a-directory-through-ssh)
    - [Method 1](#method-1)
    - [Method 2](#method-2)
      - [Copier via scp et wildcard \*](#copier-via-scp-et-wildcard-)
  - [Gestion des processus (sur bash shell)](#gestion-des-processus-sur-bash-shell)
    - [Caractéristiques nvidia-smi](#caractéristiques-nvidia-smi)
  - [Permissions de dossier/fichier](#permissions-de-dossierfichier)
    - [Find all files (not directory) to make it readable for everyone](#find-all-files-not-directory-to-make-it-readable-for-everyone)
    - [Find all directories (not simple files) to make it readable and executable](#find-all-directories-not-simple-files-to-make-it-readable-and-executable)
  - [Bash System Settings](#bash-system-settings)
    - [Changer de serveur DNS](#changer-de-serveur-dns)
      - [Generated by NetworkManager](#generated-by-networkmanager)
        - [Generated by NetworkManager](#generated-by-networkmanager-1)
      - [Connaitre la version debian et nom du processeur](#connaitre-la-version-debian-et-nom-du-processeur)
    - [Processus](#processus)
      - [Tuer un processus :](#tuer-un-processus-)
      - [Get more info about current processus](#get-more-info-about-current-processus)
  - [Others](#others)
      - [Chercher les versions de python installées :](#chercher-les-versions-de-python-installées-)
      - [Instal Latex : (debian 7)](#instal-latex--debian-7)
      - [Accéder aux infos processeurs](#accéder-aux-infos-processeurs)
      - [Accéder aux informations de la RAM : (en mode superutilisateur) 2 Go RAM](#accéder-aux-informations-de-la-ram--en-mode-superutilisateur-2-go-ram)
      - [Donne des infos sur nombre de lignes, mots et octets d’un fichier](#donne-des-infos-sur-nombre-de-lignes-mots-et-octets-dun-fichier-1)
  - [PDF](#pdf)
      - [Fusion of pdfs](#fusion-of-pdfs)
    - [Install Settings](#install-settings)
      - [Installer un software sur /opt/ (au lieu de ur/local/) (from here)](#installer-un-software-sur-opt-au-lieu-de-urlocal-from-here)
      - [Changer la longueur du nom de chemin du dossier courant](#changer-la-longueur-du-nom-de-chemin-du-dossier-courant)
      - [Configurer les paramètres d’affichage écran : unity-tweak-tool](#configurer-les-paramètres-daffichage-écran--unity-tweak-tool)
      - [Connaitre si un paquet est installé :](#connaitre-si-un-paquet-est-installé-)
      - [Chercher dans apt :](#chercher-dans-apt-)
  - [Others](#others-1)

<!-- /TOC -->

- [Shell Bash toolbox](#shell-bash-toolbox)
  - [Jupyter Notebook settings](#jupyter-notebook-settings)
      - [Add the extension for Table of Contents](#add-the-extension-for-table-of-contents)
      - [Run a server independently on the terminal window:](#run-a-server-independently-on-the-terminal-window)
      - [Delete a server (method1):](#delete-a-server-method1)
      - [Delete a server (method2):](#delete-a-server-method2)
      - [Delete a server (method3):](#delete-a-server-method3)
  - [BASH Syntax](#bash-syntax)
      - [List last modifications in a file](#list-last-modifications-in-a-file)
      - [Redirect error on output](#redirect-error-on-output)
      - [Connaitre le chemin d’accès d’une application exécutable](#connaitre-le-chemin-daccès-dune-application-exécutable)
      - [Effacer tous les fichiers du répertoire courant sauf fichier1 et fichier2](#effacer-tous-les-fichiers-du-répertoire-courant-sauf-fichier1-et-fichier2)
      - [Affiche un court texte sur le terminal et peut concaténer deux fichiers](#affiche-un-court-texte-sur-le-terminal-et-peut-concaténer-deux-fichiers)
      - [Donne des infos sur nombre de lignes, mots et octets d’un fichier](#donne-des-infos-sur-nombre-de-lignes-mots-et-octets-dun-fichier)
      - [Afficher chemin du répertoire courant](#afficher-chemin-du-répertoire-courant)
      - [Ajouter du texte à la fin d’ un fichier (non) protégé](#ajouter-du-texte-à-la-fin-d-un-fichier-non-protégé)
      - [Afficher le chemin d’un fichier](#afficher-le-chemin-dun-fichier)
      - [Connaitre la taille d’un répertoire](#connaitre-la-taille-dun-répertoire)
      - [Connaitre la taille des fichiers](#connaitre-la-taille-des-fichiers)
      - [Lien symbolique vers .local/bin/](#lien-symbolique-vers-localbin)
      - [Donner la valeur d’une variable d’environnnement](#donner-la-valeur-dune-variable-denvironnnement)
    - [Arguments in bash scripts](#arguments-in-bash-scripts)
      - [Manual usage](#manual-usage)
      - [Getops simple example](#getops-simple-example)
      - [Compulsory arguments](#compulsory-arguments)
      - [Deactivate/Activate wildcard recognition](#deactivateactivate-wildcard-recognition)
    - [Conditions in bash languages](#conditions-in-bash-languages)
      - [Bash yes/no test](#bash-yesno-test)
      - [exit  from a _while_ loop](#exit--from-a-while-loop)
      - [Tester si un fichier,répertoire existe (bash)](#tester-si-un-fichierrépertoire-existe-bash)
      - [Wildcard in bash](#wildcard-in-bash)
      - [Créer des alias sur shell](#créer-des-alias-sur-shell)
      - [Connaître répartition de la mémoire disque](#connaître-répartition-de-la-mémoire-disque)
      - [Suppprimer/insérer les lignes d’un fichier](#suppprimerinsérer-les-lignes-dun-fichier)
    - [Syntax AWK](#syntax-awk)
      - [Pass variables to awk](#pass-variables-to-awk)
      - [Get the string between one/two separator with awk](#get-the-string-between-onetwo-separator-with-awk)
      - [Replace one column of a file f1 with the column of another file f2](#replace-one-column-of-a-file-f1-with-the-column-of-another-file-f2)
      - [Get only the part of a file between two matching term (excluding matching lines and including them)](#get-only-the-part-of-a-file-between-two-matching-term-excluding-matching-lines-and-including-them)
      - [Transform a ouptut in column to a unique row with a white space separation](#transform-a-ouptut-in-column-to-a-unique-row-with-a-white-space-separation)
      - [Récupère des données utilisant la la ligne,colonne, motif avec awk](#récupère-des-données-utilisant-la-la-lignecolonne-motif-avec-awk)
    - [Archive extraction (`tar`)](#archive-extraction-tar)
      - [Updating a existing tar file by adding/updating a subdirectory; create the archive it if not exist](#updating-a-existing-tar-file-by-addingupdating-a-subdirectory-create-the-archive-it-if-not-exist)
      - [Untar an archive folder in another name](#untar-an-archive-folder-in-another-name)
      - [Untar only a sub directory of a compressed file (and forget the first two parents)](#untar-only-a-sub-directory-of-a-compressed-file-and-forget-the-first-two-parents)
      - [Untar by excluding files](#untar-by-excluding-files)
      - [Créer tar/Extraire tar](#créer-tarextraire-tar)
      - [Erase files after extracting](#erase-files-after-extracting)
      - [Extract and exclude a subdirectory or file](#extract-and-exclude-a-subdirectory-or-file)
      - [Extract only a subfolder of a large `.tar` archive](#extract-only-a-subfolder-of-a-large-tar-archive)
      - [Display the size of a subfolder/file inside a `tar` archive without extracting it](#display-the-size-of-a-subfolderfile-inside-a-tar-archive-without-extracting-it)
    - [Command ls](#command-ls)
      - [List all folders in the current directory](#list-all-folders-in-the-current-directory)
    - [Command find](#command-find)
      - [Case sensitive](#case-sensitive)
      - [Case insensitive](#case-insensitive)
      - [Find a file and execute a complex bash command ;](#find-a-file-and-execute-a-complex-bash-command-)
      - [Return name with relative path wrt mydir with all directories and not tar files](#return-name-with-relative-path-wrt-mydir-with-all-directories-and-not-tar-files)
      - [Find a match pattern and replace next line](#find-a-match-pattern-and-replace-next-line)
      - [Find a match pattern and replace next string](#find-a-match-pattern-and-replace-next-string)
      - [Remove files with wildcard except another pattern](#remove-files-with-wildcard-except-another-pattern)
      - [Find a file with a pattern on the filename and a word to search in the file](#find-a-file-with-a-pattern-on-the-filename-and-a-word-to-search-in-the-file)
      - [Find a file matching pattern and find lines in the file where is located a word-to-search](#find-a-file-matching-pattern-and-find-lines-in-the-file-where-is-located-a-word-to-search)
    - [Command grep](#command-grep)
      - [Return lines of a files that (do not) start by ‘ ‘, #, ;](#return-lines-of-a-files-that-do-not-start-by----)
      - [Catch several matching term in any order with grep (through perl)](#catch-several-matching-term-in-any-order-with-grep-through-perl)
      - [Find a filename and the line number where a pattern appears in all directories](#find-a-filename-and-the-line-number-where-a-pattern-appears-in-all-directories)
    - [Command sed](#command-sed)
      - [Delete the lines lying between PATTERN-1 and PATTERN-2 , excluding the lines containing these patterns (from here)](#delete-the-lines-lying-between-pattern-1-and-pattern-2--excluding-the-lines-containing-these-patterns-from-here)
      - [Delete the lines lying between PATTERN-1 and PATTERN-2 , including the lines containing these patterns](#delete-the-lines-lying-between-pattern-1-and-pattern-2--including-the-lines-containing-these-patterns)
      - [Delete all the lines after PATTERN-2, use this](#delete-all-the-lines-after-pattern-2-use-this)
      - [Do sed command (ex add a symbol “\_” in the 17th position) only in a range of rows (between line1 and line2)](#do-sed-command-ex-add-a-symbol-_-in-the-17th-position-only-in-a-range-of-rows-between-line1-and-line2)
      - [Delete 10 lines after matching a term](#delete-10-lines-after-matching-a-term)
      - [Delete all lines before/after a matching term](#delete-all-lines-beforeafter-a-matching-term)
      - [Select lines in a sub-part of a file between two matching terms](#select-lines-in-a-sub-part-of-a-file-between-two-matching-terms)
      - [Select all lines after a matching terms](#select-all-lines-after-a-matching-terms)
      - [Insert several lines after matching a term in a file](#insert-several-lines-after-matching-a-term-in-a-file)
      - [Comment with “;” a line after match one or several term in a line](#comment-with--a-line-after-match-one-or-several-term-in-a-line)
      - [Insert a character at a given column number in all lines with match (17 in the example)](#insert-a-character-at-a-given-column-number-in-all-lines-with-match-17-in-the-example)
      - [Match a string and do a replacement between two strings in the lines where it matchs](#match-a-string-and-do-a-replacement-between-two-strings-in-the-lines-where-it-matchs)
      - [Sort only a part of a file wrt the 2nd column delimited by two lines using matching terms](#sort-only-a-part-of-a-file-wrt-the-2nd-column-delimited-by-two-lines-using-matching-terms)
      - [Insert the content of a file1 in another file2 before the matching term](#insert-the-content-of-a-file1-in-another-file2-before-the-matching-term)
      - [Insert the content of a file1 in another file2 after the matching term](#insert-the-content-of-a-file1-in-another-file2-after-the-matching-term)
      - [Insert the content of a file1 in another file2 at a given line (do not work for line 0)](#insert-the-content-of-a-file1-in-another-file2-at-a-given-line-do-not-work-for-line-0)
      - [Insérer ligne après matcher un motif](#insérer-ligne-après-matcher-un-motif)
      - [Insérer ligne avant matcher un motif](#insérer-ligne-avant-matcher-un-motif)
      - [Replacer toute une line après avoir match un motif](#replacer-toute-une-line-après-avoir-match-un-motif)
    - [command curl](#command-curl)
      - [Zip and download a sub-directory of a github repo](#zip-and-download-a-sub-directory-of-a-github-repo)
    - [Sorting tools](#sorting-tools)
      - [Sort a list of files depending on a part of the string name](#sort-a-list-of-files-depending-on-a-part-of-the-string-name)
      - [Sort a list of filename in the good order including 1-9 numbers](#sort-a-list-of-filename-in-the-good-order-including-1-9-numbers)
    - [Command convert](#command-convert)
      - [Reduce the size of an image](#reduce-the-size-of-an-image)
    - [Other commands](#other-commands)
      - [Récupérer un mot dans une suite de mots](#récupérer-un-mot-dans-une-suite-de-mots)
      - [Change a line into a column](#change-a-line-into-a-column)
      - [Date](#date)
    - [Series of commands](#series-of-commands)
      - [Afficher la ligne d’un fichier en utilisant le numéro de la ligne](#afficher-la-ligne-dun-fichier-en-utilisant-le-numéro-de-la-ligne)
      - [Trouver un programme affiché dans Gnome (touche Windows)](#trouver-un-programme-affiché-dans-gnome-touche-windows)
      - [Renommer plusieurs fichiers avec wildcard](#renommer-plusieurs-fichiers-avec-wildcard)
      - [Vérifier si un argument est fourni avec l’executable en bash](#vérifier-si-un-argument-est-fourni-avec-lexecutable-en-bash)
      - [Remplacer du texte dan un template avec sed](#remplacer-du-texte-dan-un-template-avec-sed)
      - [Changer les couleurs par défaut de la commande ls (LS\_COLORS variable)](#changer-les-couleurs-par-défaut-de-la-commande-ls-ls_colors-variable)
      - [Eviter les avertissements Warning avec GTK sur un terminal](#eviter-les-avertissements-warning-avec-gtk-sur-un-terminal)
      - [Lancer un processus en arrière-plan sans tuer le processus en quittant le terminal](#lancer-un-processus-en-arrière-plan-sans-tuer-le-processus-en-quittant-le-terminal)
  - [History](#history)
    - [Bash](#bash)
    - [Fish](#fish)
  - [Tunnel SSH](#tunnel-ssh)
      - [Create a directory through ssh](#create-a-directory-through-ssh)
    - [Method 1](#method-1)
    - [Method 2](#method-2)
      - [Copier via scp et wildcard \*](#copier-via-scp-et-wildcard-)
  - [Gestion des processus (sur bash shell)](#gestion-des-processus-sur-bash-shell)
    - [Caractéristiques nvidia-smi](#caractéristiques-nvidia-smi)
  - [Permissions de dossier/fichier](#permissions-de-dossierfichier)
    - [Find all files (not directory) to make it readable for everyone](#find-all-files-not-directory-to-make-it-readable-for-everyone)
    - [Find all directories (not simple files) to make it readable and executable](#find-all-directories-not-simple-files-to-make-it-readable-and-executable)
  - [Bash System Settings](#bash-system-settings)
    - [Changer de serveur DNS](#changer-de-serveur-dns)
      - [Generated by NetworkManager](#generated-by-networkmanager)
        - [Generated by NetworkManager](#generated-by-networkmanager-1)
      - [Connaitre la version debian et nom du processeur](#connaitre-la-version-debian-et-nom-du-processeur)
    - [Processus](#processus)
      - [Tuer un processus :](#tuer-un-processus-)
      - [Get more info about current processus](#get-more-info-about-current-processus)
  - [Others](#others)
      - [Chercher les versions de python installées :](#chercher-les-versions-de-python-installées-)
      - [Instal Latex : (debian 7)](#instal-latex--debian-7)
      - [Accéder aux infos processeurs](#accéder-aux-infos-processeurs)
      - [Accéder aux informations de la RAM : (en mode superutilisateur) 2 Go RAM](#accéder-aux-informations-de-la-ram--en-mode-superutilisateur-2-go-ram)
      - [Donne des infos sur nombre de lignes, mots et octets d’un fichier](#donne-des-infos-sur-nombre-de-lignes-mots-et-octets-dun-fichier-1)
  - [PDF](#pdf)
      - [Fusion of pdfs](#fusion-of-pdfs)
    - [Install Settings](#install-settings)
      - [Installer un software sur /opt/ (au lieu de ur/local/) (from here)](#installer-un-software-sur-opt-au-lieu-de-urlocal-from-here)
      - [Changer la longueur du nom de chemin du dossier courant](#changer-la-longueur-du-nom-de-chemin-du-dossier-courant)
      - [Configurer les paramètres d’affichage écran : unity-tweak-tool](#configurer-les-paramètres-daffichage-écran--unity-tweak-tool)
      - [Connaitre si un paquet est installé :](#connaitre-si-un-paquet-est-installé-)
      - [Chercher dans apt :](#chercher-dans-apt-)
  - [Others](#others-1)

<!-- /TOC -->

## Jupyter Notebook settings

#### Add the extension for Table of Contents
In the base environment of Conda :
```Bash
pip install jupyter_contrib_nbextensions && jupyter contrib nbextension install --user
```
Once opening a notebook, activate in the menu nbextensions the item called Table of Contents (2)

#### Run a server independently on the terminal window:
```Bash
nohup jupyter notebook --no-browser --port 9997 & disown
```

#### Delete a server (method1):
```Bash
jupyter notebook stop 9997
```

#### Delete a server (method2):
```Bash
pgrep jupyter -> get PID  
kill PID
```

#### Delete a server (method3):
```Bash
jupyter notebook list # get the port number
lsof -n -i4TCP:[port-number] # get the PIDof the server
kill -9 [PID] # kill the PID and therefore the jupyter server
```

## BASH Syntax

#### List last modifications in a file
```Bash
find -printf "%TY-%Tm-%Td %TT %p\n" | sort -n
```

#### Redirect error on output
```Bash
./run.sh >output.log 2>&1
```

#### Connaitre le chemin d’accès d’une application exécutable
```Bash
which nom_application
```

#### Effacer tous les fichiers du répertoire courant sauf fichier1 et fichier2
```Bash
shopt -s extglob
rm -v !(fichier2"|"fichier1")
```
(`-v` ou `-verbose` explique ce qui est fait)

#### Affiche un court texte sur le terminal et peut concaténer deux fichiers
```Bash
cat fichier1
cat fichier1 fichier2 > fichier3
cat fichier1 >> fichier 3 (ajoute à la suite dans fichier3 le contenu du fichier1)
```

#### Donne des infos sur nombre de lignes, mots et octets d’un fichier
```Bash
wc fichier
```
Ex output : 4 5 12 (4 lignes, 5 caractères, 12octets)
```Bash
cat fichier |wc -l (donne le nombre de lignes dans fichier)
```

#### Afficher chemin du répertoire courant
```Bash
pwd
```

#### Ajouter du texte à la fin d’ un fichier (non) protégé  
```Bash
echo ‘mon_texte’ >> fichier
echo ‘mon_texte’ # écris simplement sur le bash
echo ‘mon_texte \nautre_texte’ #permet d’écrire plusieurs lignes
echo ‘www.nouveau_dépot’ | sudo tee -a /etc/apt/sources.list # our ajouter des sources dans un fichier protégé
printf '%s' "texte a ajouter à la suite de la dernière ligne du fichier” >> fichier.dat
printf “energy= %1.3f temperature= %1;4” $ENERGY $TEMP -> renvoie une ligne avec caractères et nombres (f pour float ,1 pour l’espace, .3 pour 3 chiffres après la virgule)*
echo -n texte_a completer >>fichier.dat -> ecrit dans un fichier et empêche le saut de ligne pour la prochaine entrée
```

#### Afficher le chemin d’un fichier  
```Bash
locate -i nom_du_fichier
Whereis <application> #cherche le chemin d’une application
```

#### Connaitre la taille d’un répertoire
```Bash
du -sh /chemin/répertoire
```

#### Connaitre la taille des fichiers
```Bash
ls -lsha
```

#### Lien symbolique vers .local/bin/
```Bash
ln -s /absolute/path/to/exec/ /absolute/path/to/home/.local/bin/exec_file
```

#### Donner la valeur d’une variable d’environnnement
```Bash
echo $Nom_de_la variable
```

### Arguments in bash scripts

#### Manual usage
```Bash
target=$1
usage() {
    echo "Usage: $0 <fichier>"
    echo "Compte les lignes d'un fichier"
    exit
}
main() {
    ls -l $target
    echo "nombre de lignes : $(wc -l $target)"
    stat $target
}
if [ $# -lt 1 ]; then
    usage
elif [ $# -eq 1 ]; then
    main
else
    usage
fi
exit
```

#### Getops simple example
Invonvenients : it is not able to parse GNU-style long options (```--myoption```) nor XF86-style long options (```-myoption```)
```bash
file=''
print_usage() {
  printf "reorder a pdb file by blocks of the same residues (needed for gromacs topol.top file format).\n\n"
  printf "Usage: pdb_reorder -f filename "
}

while getopts 'f:' flag; do
  case "${flag}" in
    f) file="${OPTARG}" ;;
    *) print_usage
       exit 1 ;;
  esac
done
```


#### Compulsory arguments
```Bash
if [ -z "$stream" ] || [ -z "$pattern" ]; then
        print_usage
        exit 1
fi
```

#### Deactivate/Activate wildcard recognition
```Bash
set -f
set +f
```

### Conditions in bash languages

[https://ryanstutorials.net/bash-scripting-tutorial/bash-if-statements.php](https://ryanstutorials.net/bash-scripting-tutorial/bash-if-statements.php)

#### Bash yes/no test

```Bash
while true; do
read -p " Do you want to do BLABLABLA ? (y/n)" yn
case $yn in
[Yy]* ) break;;
[Nn]* ) exit;;
* ) echo "Please answer yes or no.";;
esac
done
```

#### exit  from a _while_ loop 
```Bash
while …
if [[ TEST = ‘1’ ]] ; then
echo "Condition TEST is 1"
break
fi
done
```

#### Tester si un fichier,répertoire existe (bash)
```Bash
test -f file.txt
echo $? # renvoie 1 si le fichier n’existe pas, 0 si il existe
test -d dir_test
echo $? # renvoie 1 si le répertoire n’existe pas, 0 si il existe
```
Variante : [ ] au lieu de test

Ex: `[ -e file.txt ]` -> vérifie si un fichier existe quelque soit son type (régulier, lien symbolique , …)
  

#### Wildcard in bash
```Bash
rm *.txt #efface tous les fichiers d’extension txt
rm ???.txt #efface tous les fichiers d’extension txt et 3 caractères comme nom de fichier
rm [a-h0-6]*.txt #efface tous les fichiers txt commençant par une lettre entre a et h ou un chiffre entre 0 et 6
```
  

#### Créer des alias sur shell

Dans .bashrc : `alias funcname " <command> "`
In a Fish terminal :
```Bash
alias <funcname>=“<command>”
funcsave <funcname>
```

#### Connaître répartition de la mémoire disque
```Bash
df -h # calcul de mémoire disque de chaque périphérique -h for human readable in Go

du -sh /home/directory # calcul de la taille de chaque répertoire dans le chemin indiqué

df -dh /home/directory #idem
``` 

#### Suppprimer/insérer les lignes d’un fichier

En supprimant par numéro de ligne :
```Bash
sed -i -e '1d' potential.dat (supprime la 1ere ligne du .dat)
sed -i -e '1,24d' potential.dat (supprime les 24 lignes du .dat)
```

En supprimant selon un motif :
```Bash
grep -v type_du_motif fichier1 > fichier2 (motif = nombre ou lettres ou symboles entre ‘’)
```

Rq : l’option -v fait fonction inverse, si on enlève l’option, on n’affiche que les lignes avec le motif

Rq : plusieurs motifs peuvent être recherché en les séparant par \| .

ex:
```Bash
grep -v “motif1\|motif2” fichier1 > fichier2 (OR)

grep -E “motif1.*motif2” fichier1 #(AND)

grep motif1 -A5 fichier1 #affiche le contenu des 5 lignes après le motif1 dans fichier1
```
  
```Bash
sed -i “1idutexteainserer” fichier.txt (insère du texte sur la première ligne du fichier txt )

sed 10q fichier.dat #affiche les 10 premières lignes du fichier

tail -n 100 A.txt >> B.txt #insérer les n dernières lignes du fichier A à la suite du fichier B
```

### Syntax AWK

#### Pass variables to awk
```Bash
echo | awk -v r=$root -v t='truc' 'BEGIN{a=20}{ print "shell variable $root value is " r " and the other value is " t "=" a}'
```

#### Get the string between one/two separator with awk
```Bash
awk -F ‘sep1' '{print $2}' <<< mystring

awk -F ‘sep1|sep2' '{print $2}' <<< mystring
```

#### Replace one column of a file f1 with the column of another file f2
```Bash
awk 'FNR==NR{a[NR]=$3;next}{$2=a[FNR]}1' f2 f1
```

#### Get only the part of a file between two matching term (excluding matching lines and including them)
```Bash

awk '/MATCH1/{flag=1;next}/MATCH2/{flag=0}flag' file

awk '/MATCH1/{a=1}/MATCH2/{print;a=0}a' file
```

#### Transform a ouptut in column to a unique row with a white space separation
```Bash
awk 'BEGIN { ORS = " " } { print $1 }' filename
```

#### Récupère des données utilisant la la ligne,colonne, motif avec awk
```Bash
cat filename| | awk '/MOTIF/ {print $1, $2}'

cat filename| | awk ' FNR == 5 {print $1, $2}'
```

### Archive extraction (`tar`)

#### Updating a existing tar file by adding/updating a subdirectory; create the archive it if not exist
```Bash
tar --update -v -f archive.tar dir2archive/subdir
```

#### Untar an archive folder in another name
```Bash
mkdir -p archive_new && tar -xvf archive.tar -C archive_new --strip-components=1
```

#### Untar only a sub directory of a compressed file (and forget the first two parents)

```Bash
tar --strip-components=2 -xfvz archive.tar.gz folder/in/archive
```

#### Untar by excluding files
Remark : it takes still some time since it reads the disk sequentially.
```Bash
tar -zvxf tarball.tar.gz --exclude='*.xtc' --exclude='*.trr'
```

#### Créer tar/Extraire tar
```Bash
tar xvf mon_archive.tar # dézipper une archive
tar zxvf mon_archive.tar.gz # dézipper une archive compressée
tar -cvf archive.tar spencel1 fichierarchive2… #créer une archive à partir de plusieurs fichiers
tar -zcvf archivedossier.tar dossier/ # créer une archive compressée à partir d’un dossier
tar cvf - path/to/dir/ | pigz > archive.tar.gz # allow to use all cores in the machine to zip and tar
```

#### Erase files after extracting
This is useful when we extract in the wrong directory
```Bash
tar tf <file.tar.gz> | sort -r | while read file; do if [ -d "$file" ]; then rmdir "$file"; else rm -f "$file"; fi; done
```

#### Extract and exclude a subdirectory or file
```Bash
tar --exclude="PATTERN" -zxcf tarball.tar.gz
```

#### Extract only a subfolder of a large `.tar` archive
```bash
tar -xvf <archive>.tar -C <path/to/output>
<./relative/folder/> --strip-components=2
```
e.g. `strip-components`=2 will only create the architecture tree from the locatio of the realtive path folder in the tar achive.

#### Display the size of a subfolder/file inside a `tar` archive without extracting it

```bash
tar -tvf <archive>.tar | grep "<relative/path/to/folder/(file)>" | awk '{sum += $3} END {print sum}' | numfmt --to=iec
```

### Command ls

#### List all folders in the current directory
```Bash
ls -d */
ls -d */ | grep -v PATTERN # to exclude with a pattern
```

### Command find

#### Case sensitive
```Bash
Find /path/to/search -name “*Keyword*"
```

#### Case insensitive
```Bash
Find /path/to/search -iname “*keyword*"
```

Combine multiple matching/unmatching patterns to find files (-not -name options must be always called before -name options, otherwise the combinatory rule is lost )
```Bash
find ./ -maxdepth 1 -not -name "NOMATCH1” -not -name "NOMATCH2” -name "MATCH1” -o -name "MATCH2"
```

#### Find a file and execute a complex bash command ;
```Bash
find ./ -type f -name "*.txt" -exec sh -c 'grep -EiH something "$1" | grep -E somethingelse | grep -E other' sh {} \;
```

#### Return name with relative path wrt mydir with all directories and not tar files
```Bash
find mydir -maxdepth 1 -type f
```

#### Find a match pattern and replace next line
```Bash
​sed -i '/MATCH/{n;s/.*/NEW_NEXT_LINE/}' file
```

#### Find a match pattern and replace next string
```Bash
sed -i 's/MATCH [^ ]*/MATCH newString/' file
```

#### Remove files with wildcard except another pattern
```Bash
find . -iname "pattern1*" -not -iname "*pattern2*" -delete
```

#### Find a file with a pattern on the filename and a word to search in the file

```Bash
find /dir/to/search -type f -iname "pattern" -print0 | xargs -0 grep --color 'word-to-search' "{}"
```

#### Find a file matching pattern and find lines in the file where is located a word-to-search
```Bash
find . -type f -name "*.txt" -exec grep -H --color "word" {} \;
find /dir/to/search -type f -iname "pattern" -print0 | xargs -I {} -0 grep --color 'word-to-search' "{}"
```

### Command grep

#### Return lines of a files that (do not) start by ‘ ‘, #, ;
```Bash
grep "^[#; ]" file

grep "^[^#; ]" file
```

#### Catch several matching term in any order with grep (through perl)
```Bash
grep -P '(?=.*?MATCH1)(?=.*?MATCH2)(?=.*?MATCH3)(?=.*MATCH4)^.*$'
```

Récupérer les éléments de la 5e colonne d’un fichier en sélectionnant un ligne suivant un motif et les placer dans un autre fichier

```Bash
grep <motif> file | awk '{print $5}' >>outfile
```
Récupérer la première coccurence d’un motif dans un fichier
```Bash
grep -m1 <motif> file
```

#### Find a filename and the line number where a pattern appears in all directories 
```Bash
grep -rnw 'pattern' '/path/to/somewhere/'
```

### Command sed

#### Delete the lines lying between PATTERN-1 and PATTERN-2 , excluding the lines containing these patterns (from [here](https://nixtricks.wordpress.com/2013/01/09/sed-delete-the-lines-lying-in-between-two-patterns/))
```Bash
sed '/PATTERN-1/,/PATTERN-2/{//!d}' input.txt
```

#### Delete the lines lying between PATTERN-1 and PATTERN-2 , including the lines containing these patterns
```Bash
sed '/PATTERN-1/,/PATTERN-2/d' input.txt
```

#### Delete all the lines after PATTERN-2, use this
```Bash
sed '/PATTERN-1/,$d' input.txt
```

#### Do sed command (ex add a symbol “_” in the 17th position) only in a range of rows (between line1 and line2)
```Bash
sed -i -E 'line1,line2s/^(.{17}) /\1_/' file
```

#### Delete 10 lines after matching a term
```Bash
sed -e '/MATCH/,+10d' file
``` 

#### Delete all lines before/after a matching term
```Bash
sed -n '/MATCH/,$p' file
sed -e '/MATCH/,$d' file
```

#### Select lines in a sub-part of a file between two matching terms
```Bash
sed -n '/^pattern1/,${p;/^pattern2/q}' file
```

#### Select all lines after a matching terms
```Bash
sed -n '/^pattern/,$p' file
```

#### Insert several lines after matching a term in a file
```Bash
sed -i '/MATCH/a \
Ceci est mon texte\
En plusieurs lignes \
' file
```

#### Comment with “;” a line after match one or several term in a line
```Bash
sed -i '/MATCH1.*MATCH2/s/./;&/' file
```

#### Insert a character at a given column number in all lines with match (17 in the example)
```Bash
sed -i -E '/MATCH/s/^(.{17}) /\1CHAR/' file
```

#### Match a string and do a replacement between two strings in the lines where it matchs
```Bash
sed -i '/MATCH/{ s/string1/string2/g }' file
```

#### Sort only a part of a file wrt the 2nd column delimited by two lines using matching terms
```Bash
{
sed '1,/^.*MATCH1.*$/!d' file

sed '/^.*MATCH1.*$/,/^.*MATCH2.*$/!d' file | head -n-1 | tail -n+2 | sort -k2

sed '/^.*MATCH2.*$/,$!d' file

} > new_file
``` 

#### Insert the content of a file1 in another file2 before the matching term
```Bash
sed -i '/.*MATCH1.*/e cat file1' file2
```

#### Insert the content of a file1 in another file2 after the matching term
```Bash
sed -i '/MATCH/ r file1' file2
```

#### Insert the content of a file1 in another file2 at a given line (do not work for line 0)
```Bash
line=2
sed -e '${line}r file1' file2
```

#### Insérer ligne après matcher un motif
```Bash
sed -i '/.*MOTIF.*/a NEWLINE' file
```

#### Insérer ligne avant matcher un motif
```Bash
sed -i '/.*MOTIF.*/i NEWLINE' file
```

#### Replacer toute une line après avoir match un motif
```Bash
sed -i 's/.*MOTIF.*/WHOLE LINE/' file
```
### command curl

#### Zip and download a sub-directory of a github repo
```bash
curl -L -o myfolder.zip https://github.com/gitlogin/path/to/myfolder.zip \
&& unzip -j myfolder.zip "gitlogin-main/path/to/myfolder" -d myfolder
```
> To unzip the file properly, one need to now the local architecture

> Once unzipping the first repo is gitlogin-main or gitlogin-branch with the branch it has been taken from
 
### Sorting tools 

#### Sort a list of files depending on a part of the string name
Use a delimiter after `-t` and select with `-k` the number nth field to use 
e.g. `.` as a delimiter and the second field :
```Bash
$ ls * | sort -t. -k2
```

#### Sort a list of filename in the good order including 1-9 numbers
```Bash
ls *1000* | sort --version-sort
ls -v1 *png
```
With output in a single line :
```Bash
ls -v1 *png | xargs
```
Use the result as input for a command COMMAND :
```Bash
ls -v1 *png | xargs COMMAND
```

### Command convert

#### Reduce the size of an image
```Bash
convert old.png -resize 50%  new.png
```


### Other commands

#### Récupérer un mot dans une suite de mots
```Bash
N=3  
STRING="one two three four"  
arr=($STRING)  
echo ${arr[N-1]}
```

#### Change a line into a column
```Bash
echo $line | tr -s ' '  '\n'
```

#### Date
```Bash
date +%Y-%m-%d-%H:%M
date +%F
```

### Series of commands

#### Afficher la ligne d’un fichier en utilisant le numéro de la ligne
```Bash
sed -n 3p file

awk '{if(NR==3) print $0}' file
```

#### Trouver un programme affiché dans Gnome (touche Windows)
Aller dans usr/share/applications et chercher le fichier <nom_du_programme>.desktop

#### Renommer plusieurs fichiers avec wildcard
```Bash
mmv old_filename\* new_filename\#1
```

#### Vérifier si un argument est fourni avec l’executable en bash
```Bash
if [ $# -eq 0 ]
then
echo "No arguments supplied"
fi
```
Ou avec un test de type string vide
```Bash
if [ -z "$1" ]
then
echo "No argument supplied"
fi
```

#### Remplacer du texte dan un template avec sed
```Bash
sed -e 's/TEMPLATE/value_of_template/g' input_file.dat > output_file.dat
```

#### Changer les couleurs par défaut de la commande ls (LS_COLORS variable)
```Bash
dircolors -p > ~/.dircolors # créer un fichier à partie des paramètres par défaut
```
Dans le .bashrc:
```Bash
if [ -x /usr/bin/dircolors ]; then
test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dircolors -b)"
alias ls='ls --color=auto'
fi
```
```Bash
dircolors -b ~/.dircolors # applique les changements sur la variable LS_COLORS
```
```Bash
eval ( dircolors --c-shell $HOME/.dircolors) #à ajouter dans .config/fish.config.fish pour appliquer les changements dans le terminal fish
```

#### Eviter les avertissements Warning avec GTK sur un terminal
Dans le .bashrc ou ~/.config/fish/config.fish:
```Bash
export NO_AT_BRIDGE=1 
```


#### Lancer un processus en arrière-plan sans tuer le processus en quittant le terminal
```Bash
nohup <command> & disown
```

## History

### Bash
Print lines of the history of bash 
```Bash
history | grep <word-to-search>
```

Delete a specific line given the line ID in the history :
```Bash
history -d <ID>
```

### Fish 
Delete the part of the history where a word appears
```Bash
history clear <word-to-search>
```
Then tap the number of the item to delete


## Tunnel SSH

#### Create a directory through ssh
```Bash
DIR="/archive/baaden_team/hardiagon/test"
if [ ! -d "$DIR" ]; then
Take action if $DIR exists ###
echo "Directory ${DIR} do not exist !"
while true; do
read -p " Do you want to create it ? (y/n)" yn
case $yn in
[Yy]* ) break;;
[Nn]* ) exit;;
* ) echo "Please answer yes or no.";;
esac
done
ssh baal "mkdir -p $DIR"
else
echo "$DIR found ."
exit 1
fi
```

### Method 1 
1.  Se connecter sur Etablir un tunnel
```Bash
ssh -L 8000:hardiagon@telesto.lbt.ibpc.fr:22 hardiagon@sage.ibpc.fr cat - #cat - laisse le canal ouvert, dans tous les cas un terminal reste ouvert dans le serveur (sage)
```
2.  Se connecter à la machine locale du serveur distant redirigée sur le port 8000
```Bash
ssh hardiagon@localhost -p 8000
```
3.  Copier le fichier test en local dans le serveur sur la machine distante (ordi portable par ex) à partir d’un terminal sur l’ordi portable
```Bash
scp -P 8000 hardiagon@localhost:~/test ./
```

### Method 2
En utilisant le fichier .ssh/config en local (ordi portable)

1.  Copier ceci dans .ssh/config
```Bash
Host sage
Hostname sage.ibpc.fr
User hardiagon
Port 22
LocalForward 8000 telesto.lbt.ibpc.fr:22
LocalForward 8001 baal.lbt.ibpc.fr:22

Host telesto
Hostname localhost
User hardiagon
Port 8000

Host baal
Hostname localhost
User hardiagon
Port 8001
```
2.  Ouvrir un 1er terminal et se connecter par tunnel
```Bash
ssh sage
```
(entrer mot de passe serveur)
3.  Ouvrir un 2eme terminal et se connecter à une machine connectée au serveur
```Bash
ssh telesto
```
(entrer mot de passe machine)

#### Copier via scp et wildcard *
```Bash
scp "telesto:/data/hardiagon/SHC8/memb541/12_channels/data/step7_*.gro" ./
``` 
Ouvrir une connexion ssh en passant une variable d’environnement
```Bash
ssh -t telesto 'export HOME=/home/hardiagon; bash'
```

## Gestion des processus (sur bash shell)
```Bash
nvidia -smi # affiche dans le shell l’état et caractéristiques des cartes nvidia

nvidia-smi -l 10 > state_nvidia # envoie toutes les 10 secondes les caractéristiques du GPU dans un fichier

top | grep nvidia-smi -m 5 #envoie sur le terminal les caractéristiques d’un processus 5 fois

pid=$(pgrep firefox) #écris la valeur d’un PID du processus firefox dans une variable
```

### Caractéristiques nvidia-smi

-   GPU Volatil
-   Memory used
-   GPU Fan

## Permissions de dossier/fichier
```Bash
sudo chmod o+rwx nom_du_fichier_courant
```
“+” autorise, “r” pour lecture, “w” pour écriture, “x” pour éxécuter, “o”pour tous autres utilisateurs (others)

Pour appliquer à un dossier, utiliser -R : 
```Bash 
sudo chmod -R o+rwx nom_du_dossier
```

```Bash
find ./ -not -name "*.*" -exec chmod 700 {} + # autorise rwx pour tous les fichiers n’ayant pas d’extension

find ./ -type f -exec chmod 600 {} + # autorise rw pour tous les fichiers réguliers (sans les répertoires)
```
0 == --- == no access
1 == --x == execute
2 == -w- == write
3 == -wx == write / execute
4 == r-- == read
5 == r-x == read / execute
6 == rw- == read / write
7 == rwx == read / write / execute

### Find all files (not directory) to make it readable for everyone 
```Bash
find ./ -type f -exec chmod 644 {} \;
```

### Find all directories (not simple files) to make it readable and executable 
```Bash
find ./ -type d -exec chmod 755 {} \;
```

## Bash System Settings

### Changer de serveur DNS
```Bash
/etc/resolv.conf
```
-> Un fichier texte modifiable doit afficher l’adresse DNS utilisé pour le serveur actuel :

#### Generated by NetworkManager
```Bash
nameserver 192.168.1.1
```
-> Ajouter deux lignes avant le DNS actuel pour permettre la navigation avec les DNS de Google :

##### Generated by NetworkManager

```bash
nameserver 8.8.8.8
nameserver 8.8.4.4
nameserver 192.168.1.1
```

-> quitter (ctrl X) en enregistrant (O) et lancer scihub sur un navigateur de recherche, normalement la page d’accueil s’affiche !

#### Connaitre la version debian et nom du processeur
```Bash
cat /etc/debian_version #version de debian

uname -a #pour la version du kernel

cat /etc/issue #autre possibilité pour la version debian

lsb_release -a #version ubuntu; release
```

### Processus

#### Tuer un processus :
```Bash
top #affiche tous les processus ouverts

kill SIGNAL PID #ferme le processus en utilisant l’adresse PID (4 chiffres)

killall NOM_DU_PROGRAMME #ferme tous les processus associé au programme utilisé
```

#### Get more info about current processus
Print architecture and specific outputs with ` -o` 
```Bash
ps -efo pid,comm
``` 
Catch a specific keyword
```Bash
ps -ef pid,comm
``` 

## Others

#### Chercher les versions de python installées :
```Bash
ls -l /usr/bin/python*
```

#### Instal Latex : (debian 7)
Chercher paquets textlive-full via Synaptic

#### Accéder aux infos processeurs
```Bash
cat /proc/cpuinfo

cat /proc/cpuinfo|grep -i "^processor" |wc -l (nombre de coeurs)
```

#### Accéder aux informations de la RAM : (en mode superutilisateur) 2 Go RAM
```Bash
dmidecode --type 17
```

#### Donne des infos sur nombre de lignes, mots et octets d’un fichier
```Bash
wc fichier
```
Ex output : 4 5 12 (4 lignes, 5 caractères, 12octets)
```
cat fichier |wc -l (donne le nombre de lignes dans fichier)
```  

## PDF

#### Fusion of pdfs
```Bash
pdfunite fichier1.pdf fichier2.pdf pdf_fusionné.pdf
```

### Install Settings

#### Installer un software sur /opt/ (au lieu de ur/local/) (from [here](https://itsfoss.com/install-software-from-source-code/))

1.  Créer un dossier source dans /opt et un lien symbolique
```Bash
sudo mkdir /opt/nom_software-versionXXX #dossier qu’il faudra rm pour désinstaller le software
sudo ln -sT nom_software-versionXXX /opt/nom_software #chercher à quoi ça sert ???
```
2.  Dans le répertoire source téléchargé
```Bash
./configure --prefix=/opt/nom_sofware-versionXXX
make -j5 | echo ok #5 = 4+1 puisque j’ai 4 coeursTtgz size
sudo make install
```
3.  Faire un lien symbolique de l’executable
```Bash
sudo ln -sT /opt/nom_sofware/bin/nom_software /usr/local/bin/nom_sofware
```

#### Changer la longueur du nom de chemin du dossier courant
```
cd ~/ | sudo nano ./basrc #puis changer /W par /w dans la variable SP1
```

#### Configurer les paramètres d’affichage écran : unity-tweak-tool

#### Connaitre si un paquet est installé :
```
apt-cache policy name_of_package
```

#### Chercher dans apt :
```
apt searcch mot-clé
apt-cache policy nom_programme
```

## Others

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNzUwNDk0NV19
-->