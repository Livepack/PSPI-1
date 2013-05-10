# <li><a href="http://tao.inf.ug.edu.pl/">dr W.Bzyl</a>

# Notatki z Technologii Internetowych

> Dzień bez kodowania jest dniem straconym :)

Znaczniki:

* p - akapit
* ol, ul - lista uporzadkowana i nieuporzadkowana
  * li
* img - obraz
* h - naglówek (od h1 do h6)

Szablon pliku HTML5:

```html
<!doctype html>
<html lang=pl>
<head>
  <meta charset=utf-8>
  <title>Szablon strony HTML5</title>
</head>
<body>
  <p>ąćęłńóśźż ĄĆĘŁŃÓŚŹŻ</p>
</body>
</html>
```

* **kursywa** to *
np.: *Ania* ma Stuarta :)

* **wytluszczenie** to **
np.: **Ania** ma Stuarta :)
     
* **pochylona kursywa** to ***
np.: ***Ania*** ma Stuarta :)

```html
<!DOCTYPE html>
<html>
<head>
<meta charset=utf-8 />
<title>JS Bin</title>
</head>
<body>
  <p>ala ma kota</p>
  <p class="warning">ola ma kota</p>
  <h3 class="warning">Warning!</h3>
</html>
```

```c
body {
  background:red;
  padding: 38px;
}

html {
  background: yellow;
  margin: 0;
  padding: 0;
}

p {
  background: green;
  padding: 24px;
  margin: 24px;
}
```






```html
akiszel@p137-07:~$ git clone git@github.com:akiszel/PSPI.git
Cloning into 'PSPI'...
Warning: Permanently added the RSA host key for IP address '204.232.175.90' to the list of known hosts.
remote: Counting objects: 150, done.
remote: Compressing objects: 100% (103/103), done.
remote: Total 150 (delta 43), reused 147 (delta 40)
Receiving objects: 100% (150/150), 98.20 KiB | 130 KiB/s, done.
Resolving deltas: 100% (43/43), done.
akiszel@p137-07:~$ ls
Dokumenty  Muzyka   profile.V2 Publiczny  tmp	  Zad-1.c
etc	   Obrazy   PSPI	Pulpit	   Wideo  Zad-1.c~
mail	   Pobrane  PSPI-TI	Szablony   Zad.   Zad.1..c~
akiszel@p137-07:~$ cd PSPI
akiszel@p137-07:~/PSPI$ git status
# On branch master
nothing to commit (working directory clean)
akiszel@p137-07:~/PSPI$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/gh-pages
  remotes/origin/master
akiszel@p137-07:~/PSPI$ git checkout --track origin/gh-pages
Branch gh-pages set up to track remote branch gh-pages from origin.
Switched to a new branch 'gh-pages'
akiszel@p137-07:~/PSPI$ git branch -a
* gh-pages
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/gh-pages
  remotes/origin/master
akiszel@p137-07:~/PSPI$ cd images/
akiszel@p137-07:~/PSPI/images$ mv ~/tort.jpg .
mv: nie można wykonać stat na `/home/studpoz/akiszel/tort.jpg': Nie ma takiego pliku ani katalogu
akiszel@p137-07:~/PSPI/images$ ls ~/Pu
Publiczny/ Pulpit/    
akiszel@p137-07:~/PSPI/images$ mv ~/Pulpit/tort.jpg  .
akiszel@p137-07:~/PSPI/images$ ls
body-bg.jpg	     github-button.png	highlight-bg.jpg  tort.jpg
download-button.png  header-bg.jpg	sidebar-bg.jpg
akiszel@p137-07:~/PSPI/images$ git status
# On branch gh-pages
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#	tort.jpg
nothing added to commit but untracked files present (use "git add" to track)
akiszel@p137-07:~/PSPI/images$ git add tort.jpg
akiszel@p137-07:~/PSPI/images$ git status
# On branch gh-pages
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#	new file:   tort.jpg
#
akiszel@p137-07:~/PSPI/images$ git commit -m "dodałem obrazek tort.jpg"
[gh-pages e75b5ba] dodałem obrazek tort.jpg
 Committer: Anna Kiszel <akiszel@p137-07.labpk.inf.ug.edu.pl>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly:

    git config --global user.name "Your Name"
    git config --global user.email you@example.com

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 images/tort.jpg
akiszel@p137-07:~/PSPI/images$ git status
# On branch gh-pages
# Your branch is ahead of 'origin/gh-pages' by 1 commit.
#
nothing to commit (working directory clean)
akiszel@p137-07:~/PSPI/images$ git push
Counting objects: 6, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 81.76 KiB, done.
Total 4 (delta 2), reused 0 (delta 0)
To git@github.com:akiszel/PSPI.git
   e3c38bc..e75b5ba  gh-pages -> gh-pages
akiszel@p137-07:~/PSPI/images$ 
```
