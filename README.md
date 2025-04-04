Отчет по лабораторной работе № 2 "Система контроля версий Git"

Выполнил: Климова Н.К.
Группа:   А-02-24
Проверил: 

Примечание: работа выполнялась на Windows.

1. Создала на рабочем столе каталог lab02 и запустила в нем Git Bash, приглашение:

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02
$

2. Просмотрела файлы в рабочем каталоге можно командой "ls" --- пусто:

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02
$ ls
---

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02
$

3. Создала каталоги Алисы и Боба, создала каталог "project",
изучил команду "cd" в процессе:

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02
$ mkdir alice

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02
$ mkdir bob

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02
$ cd bob

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/lab02/bob
$ cd ..

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02
$ cd alice

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice
$ mkdir project

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice
$ ls
project

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice
$ cd project


4. Инициализировала репозитарий:

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project
$ git init
Initialized empty Git repository in C:/Users/user/Desktop/lab02/alice/project/.git/

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (master)
$ git branch -m main

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ ls -A
.git/

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ cd .git

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project/.git (GIT_DIR!)
$ git config user.name 'Alice (KlimovaNK)'

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project/.git (GIT_DIR!)
$ git config user.email 'natusyaklimova25@gmail.com'



5. Создание коммитов

Создала проект project в CodeBlocks. Путь: C:\Users\user\Desktop\lab02\alice

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git status
On branch main - Мы внаходимся в главной ветке
No commits yet - Нет коммитов
Untracked files: - Неотслеживаемые файлы:
  (use "git add <file>..." to include in what will be committed) - Git Bash предлагает добавить файлы в проект
        main.cpp
        project.cbp
nothing added to commit but untracked files present (use "git add" to track) - Git Bash уведомляет, что в проект ничего не добавлено


user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git add main.cpp


user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git status
On branch main
No commits yet
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   main.cpp
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        project.cbp


user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git commit -m 'code: заготовка программы'
[main (root-commit) dd324b6] code: заготовка программы
 1 file changed, 9 insertions(+)
 create mode 100644 main.cpp


user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git add project.cbp
warning: in the working copy of 'project.cbp', LF will be replaced by CRLF the n
ext time Git touches it

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git commit -m 'build: add project file'
[main 728fcbd] build: add project file
 1 file changed, 40 insertions(+)
 create mode 100644 project.cbp


6. Создание коммитов с изменениями

Изменим тело функции main и просмотрим статус

$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   main.cpp
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        bin/
        obj/
no changes added to commit (use "git add" and/or "git commit -a")

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git add main.cpp

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git commit -m 'change file main'
[main 8c1d657] change file main
 1 file changed, 3 insertions(+), 1 deletion(-)

Добавим выво суммы и разницы и сохраним

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git add -u

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git commit -m 'change added functions betwen digits'
[main 10ae2b4] change added functions betwen digits
 1 file changed, 1 insertion(+)


7. Игнорирование файлов

Создадим в проекте файл .gitignore и добавим в него /bin и /obj и *.layout

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git add .gitignore

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$  git commit -m 'git: added ignored paths'
[main abadbb7] git: added ignored paths
 1 file changed, 3 insertions(+)
 create mode 100644 .gitignore


8. Просмотр истории

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git log --stat
commit abadbb7dc21bb6ddd0d804be31e697e00be9ac66 (HEAD -> main) - Подробный хешкод
Author: Alice (KlimovaNK) <natusyaklimova25@gmail.com> - Автор
Date:   Fri Apr 4 00:37:15 2025 +0300 - Дата и время создания коммита
    git: added ignored paths - Сообщение при коммите
 .gitignore | 3 +++ - Что добавили
 1 file changed, 3 insertions(+) - Что добавили

commit 10ae2b40550f1766b7096cf765e6a2e7437c945c
Author: Alice (KlimovaNK) <natusyaklimova25@gmail.com>
Date:   Fri Apr 4 00:03:38 2025 +0300
    change added functions betwen digits
 main.cpp | 1 +
 1 file changed, 1 insertion(+)

commit 8c1d6579b42ccc28709ca9201449bc0ef8b7d84e
Author: Alice (KlimovaNK) <natusyaklimova25@gmail.com>
Date:   Thu Apr 3 23:53:56 2025 +0300
    change file main
 main.cpp | 4 +++-
 1 file changed, 3 insertions(+), 1 deletion(-)

commit 728fcbdc9aed7008732eeaca855429c3ba36785a
Author: Alice (KlimovaNK) <natusyaklimova25@gmail.com>
Date:   Thu Apr 3 23:48:20 2025 +0300
    build: add project file
 project.cbp | 40 ++++++++++++++++++++++++++++++++++++++++
 1 file changed, 40 insertions(+)

commit dd324b6968bd0aaf7dd3cfef044ccb1bdac955c6
Author: Alice (KlimovaNK) <natusyaklimova25@gmail.com>
Date:   Thu Apr 3 23:41:17 2025 +0300
    code: заготовка программы
 main.cpp | 9 +++++++++
 1 file changed, 9 insertions(+)
(END)

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git log --oneline --decorate
user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git show HEAD~1
commit 10ae2b40550f1766b7096cf765e6a2e7437c945c
Author: Alice (KlimovaNK) <natusyaklimova25@gmail.com>
Date:   Fri Apr 4 00:03:38 2025 +0300

    change added functions betwen digits

diff --git a/main.cpp b/main.cpp
index 03b22ce..5a29d68 100644
--- a/main.cpp
+++ b/main.cpp
@@ -7,5 +7,6 @@ int main()
     cout << "Enter A and B: ";
     int a, b;
     cin >> a >> b;
+    cout << "A + B = " << a + b << '\n'<< "A - B = " << a - b << '\n';
     return 0;
 }

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git show main~1
commit 10ae2b40550f1766b7096cf765e6a2e7437c945c
Author: Alice (KlimovaNK) <natusyaklimova25@gmail.com>
Date:   Fri Apr 4 00:03:38 2025 +0300

    change added functions betwen digits

diff --git a/main.cpp b/main.cpp
index 03b22ce..5a29d68 100644
--- a/main.cpp
+++ b/main.cpp
@@ -7,5 +7,6 @@ int main()
     cout << "Enter A and B: ";
     int a, b;
     cin >> a >> b;
+    cout << "A + B = " << a + b << '\n'<< "A - B = " << a - b << '\n';
     return 0;
 }

 (HEAD -> main) git: added ignored paths
10ae2b4 change added functions betwen digits
8c1d657 change file main
728fcbd build: add project file
dd324b6 code: заготовка программы

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git log --oneline --decorate --all --graph
* abadbb7 (HEAD -> main) git: added ignored paths
* 10ae2b4 change added functions betwen digits
* 8c1d657 change file main
* 728fcbd build: add project file
* dd324b6 code: заготовка программы

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git log --grep build
commit 728fcbdc9aed7008732eeaca855429c3ba36785a
Author: Alice (KlimovaNK) <natusyaklimova25@gmail.com>
Date:   Thu Apr 3 23:48:20 2025 +0300
    build: add project file

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git log -- project.cbp
commit 728fcbdc9aed7008732eeaca855429c3ba36785a
Author: Alice (KlimovaNK) <natusyaklimova25@gmail.com>
Date:   Thu Apr 3 23:48:20 2025 +0300
    build: add project file


9. Просмотр коммитов

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git show HEAD~1
commit 10ae2b40550f1766b7096cf765e6a2e7437c945c
Author: Alice (KlimovaNK) <natusyaklimova25@gmail.com>
Date:   Fri Apr 4 00:03:38 2025 +0300

    change added functions betwen digits

diff --git a/main.cpp b/main.cpp
index 03b22ce..5a29d68 100644
--- a/main.cpp
+++ b/main.cpp
@@ -7,5 +7,6 @@ int main()
     cout << "Enter A and B: ";
     int a, b;
     cin >> a >> b;
+    cout << "A + B = " << a + b << '\n'<< "A - B = " << a - b << '\n';
     return 0;
 }

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git show main~1
commit 10ae2b40550f1766b7096cf765e6a2e7437c945c
Author: Alice (KlimovaNK) <natusyaklimova25@gmail.com>
Date:   Fri Apr 4 00:03:38 2025 +0300

    change added functions betwen digits

diff --git a/main.cpp b/main.cpp
index 03b22ce..5a29d68 100644
--- a/main.cpp
+++ b/main.cpp
@@ -7,5 +7,6 @@ int main()
     cout << "Enter A and B: ";
     int a, b;
     cin >> a >> b;
+    cout << "A + B = " << a + b << '\n'<< "A - B = " << a - b << '\n';
     return 0;
 }

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git show abadbb7~1
commit 10ae2b40550f1766b7096cf765e6a2e7437c945c
Author: Alice (KlimovaNK) <natusyaklimova25@gmail.com>
Date:   Fri Apr 4 00:03:38 2025 +0300

    change added functions betwen digits

diff --git a/main.cpp b/main.cpp
index 03b22ce..5a29d68 100644
--- a/main.cpp
+++ b/main.cpp
@@ -7,5 +7,6 @@ int main()
     cout << "Enter A and B: ";
     int a, b;
     cin >> a >> b;
+    cout << "A + B = " << a + b << '\n'<< "A - B = " << a - b << '\n';
     return 0;
 }

10. Просмотр изменений

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git diff
diff --git a/main.cpp b/main.cpp
index 5a29d68..28503fd 100644
--- a/main.cpp
+++ b/main.cpp
@@ -8,5 +8,6 @@ int main()
     int a, b;
     cin >> a >> b;
     cout << "A + B = " << a + b << '\n'<< "A - B = " << a - b << '\n';
+    cout << "A * B = " << a * b << '\n';
     return 0;
 }


11. Откат изменений

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git reset --hard HEAD~1 - Возвращение к предыдущей версии
HEAD is now at 10ae2b4 change added functions betwen digits

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git checkout HEAD -- main.cpp - Возвращение к последней сохраненной версии файла


12. Обмен кодом через удаленное хранилище

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ eval $(ssh-agent -s)
Agent pid 940

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ ssh-add
Enter passphrase for /c/Users/user/.ssh/id_ed25519:
Identity added: /c/Users/user/.ssh/id_ed25519 (user@WIN-IUP1272D2T4)

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ cat ~/.ssh/id_ed25519.pub
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIMGdeFLnnPvE1uCGG/0upbhzLptemLjuY0hDEeBLxzPi user@WIN-IUP1272D2T4


13. Отправка проекта на сервер

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$

git remote add origin git@github.com:Alwayssleep13/cs-lab02.git
git branch -M main
git push -u origin main
The authenticity of host 'github.com (140.82.121.4)' can't be established.
ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
Host key verification failed.
fatal: Could not read from remote repository.
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 8 threads
Compressing objects: 100% (11/11), done.
Writing objects: 100% (12/12), 1.65 KiB | 563.00 KiB/s, done.
Total 12 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), done.
To github.com:Alwayssleep13/cs-lab02.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.



14. Получение проекта с сервера

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/bob
$ git clone https://github.com/Alwayssleep13/cs-lab02 project
Cloning into 'project'...
remote: Enumerating objects: 12, done.
remote: Counting objects: 100% (12/12), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 12 (delta 1), reused 12 (delta 1), pack-reused 0 (from 0)
Receiving objects: 100% (12/12), done.
Resolving deltas: 100% (1/1), done.

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/bob
$ cd project

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/bob/project (main)
$ git push
info: please complete authentication in your browser...
Everything up-to-date

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git fetch

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git log --oneline --decorate --all --graph
* 10ae2b4 (HEAD -> main, origin/main, origin/HEAD) change added functions betwen
 digits
* 8c1d657 change file main
* 728fcbd build: add project file
* dd324b6 code: заготовка программы

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git pull --ff-only
Already up to date.

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git push
Everything up-to-date

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/bob/project (main)
$ git pull
Already up to date.


15. Разрешение конфликтов правок при совместной работе

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/bob/project (main)
$ git pull
Already up to date.

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/bob/project (main)
$ git commit -a -m 'change: added minimuum if sigits'
Author identity unknown

*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'user@WIN-IUP1272D2T4.(none)')

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/bob/project (main)
$ git commit -a -m 'change: added minimuum of digits'
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/bob/project (main)
$ git rebase origin/main
Current branch main is up to date.

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/bob/project (main)
$ git add main.cpp

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/bob/project (main)
$ git rebase --continue
fatal: no rebase in progress


16. Использование веток

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git branch double

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (double)
$ git push
fatal: The current branch double has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin double

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (double)
$ git push --set-upstream origin double
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 493 bytes | 493.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: Create a pull request for 'double' on GitHub by visiting:
remote:      https://github.com/Alwayssleep13/cs-lab02/pull/new/double
remote:
To github.com:Alwayssleep13/cs-lab02.git
 * [new branch]      double -> double
branch 'double' set up to track 'origin/double'.

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git merge double
Already up to date.

user@WIN-IUP1272D2T4 MINGW64 ~/Desktop/lab02/alice/project (main)
$ git push
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To github.com:Alwayssleep13/cs-lab02.git
   10ae2b4..72166e8  main -> main


