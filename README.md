# MergeGithubFiles
Admin@Admin-PC MINGW32 ~
$ mkdir merge

Admin@Admin-PC MINGW32 ~
$ cd merge

Admin@Admin-PC MINGW32 ~/merge
$ git init .
Initialized empty Git repository in C:/Users/Admin/merge/.git/

Admin@Admin-PC MINGW32 ~/merge (master)
$ ls

Admin@Admin-PC MINGW32 ~/merge (master)
$ ls -a
./  ../  .git/

Admin@Admin-PC MINGW32 ~/merge (master)
$ git branch

Admin@Admin-PC MINGW32 ~/merge (master)
$ git branch -a

Admin@Admin-PC MINGW32 ~/merge (master)
$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)

Admin@Admin-PC MINGW32 ~/merge (master)
$ touch file1

Admin@Admin-PC MINGW32 ~/merge (master)
$ ls
file1

Admin@Admin-PC MINGW32 ~/merge (master)
$ git add .

Admin@Admin-PC MINGW32 ~/merge (master)
$ git commit -m"1st commit in master file1"
[master (root-commit) 43a80bb] 1st commit in master file1
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file1

Admin@Admin-PC MINGW32 ~/merge (master)
$ git log
commit 43a80bbc281185a5490fed972e4c09f629d9bbf3 (HEAD -> master)
Author: KomalKumra <kumrakomal95@gmail.com>
Date:   Thu May 17 14:21:10 2018 -0500

    1st commit in master file1

Admin@Admin-PC MINGW32 ~/merge (master)
$ ls
file1

Admin@Admin-PC MINGW32 ~/merge (master)
$ git branch B1

Admin@Admin-PC MINGW32 ~/merge (master)
$ git branch
  B1
* master

Admin@Admin-PC MINGW32 ~/merge (master)
$ vi file1

Admin@Admin-PC MINGW32 ~/merge (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   file1

no changes added to commit (use "git add" and/or "git commit -a")

Admin@Admin-PC MINGW32 ~/merge (master)
$ git add .
warning: LF will be replaced by CRLF in file1.
The file will have its original line endings in your working directory.

Admin@Admin-PC MINGW32 ~/merge (master)
$ git checkout B1
Switched to branch 'B1'
M       file1

Admin@Admin-PC MINGW32 ~/merge (B1)
$ git branch
* B1
  master

Admin@Admin-PC MINGW32 ~/merge (B1)
$ vi file1

Admin@Admin-PC MINGW32 ~/merge (B1)
$ git status
On branch B1
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   file1

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   file1


Admin@Admin-PC MINGW32 ~/merge (B1)
$ git add .
warning: LF will be replaced by CRLF in file1.
The file will have its original line endings in your working directory.

Admin@Admin-PC MINGW32 ~/merge (B1)
$ git commit -m "Commit from Branch B1"
[B1 9876268] Commit from Branch B1
 1 file changed, 1 insertion(+)

Admin@Admin-PC MINGW32 ~/merge (B1)
$ git log
commit 9876268c789c632a61071e47918993d42f7ee0a7 (HEAD -> B1)
Author: KomalKumra <kumrakomal95@gmail.com>
Date:   Thu May 17 14:25:58 2018 -0500

    Commit from Branch B1

commit 43a80bbc281185a5490fed972e4c09f629d9bbf3 (master)
Author: KomalKumra <kumrakomal95@gmail.com>
Date:   Thu May 17 14:21:10 2018 -0500

    1st commit in master file1

Admin@Admin-PC MINGW32 ~/merge (B1)
$ git branch k1

Admin@Admin-PC MINGW32 ~/merge (B1)
$ git branch
* B1
  k1
  master

Admin@Admin-PC MINGW32 ~/merge (B1)
$ git checkout k1
Switched to branch 'k1'

Admin@Admin-PC MINGW32 ~/merge (k1)
$ ls
file1

Admin@Admin-PC MINGW32 ~/merge (k1)
$ echo "file2" > file2d

Admin@Admin-PC MINGW32 ~/merge (k1)
$ ls
file1  file2d

Admin@Admin-PC MINGW32 ~/merge (k1)
$ git add .
warning: LF will be replaced by CRLF in file2d.
The file will have its original line endings in your working directory.

Admin@Admin-PC MINGW32 ~/merge (k1)
$ git commit -m "Created new file in k1"
[k1 582a8ff] Created new file in k1
 1 file changed, 1 insertion(+)
 create mode 100644 file2d

Admin@Admin-PC MINGW32 ~/merge (k1)
$ git checkout B1
Switched to branch 'B1'

Admin@Admin-PC MINGW32 ~/merge (B1)
$ ls
file1

Admin@Admin-PC MINGW32 ~/merge (B1)
$ git branch
* B1
  k1
  master

Admin@Admin-PC MINGW32 ~/merge (B1)
$ git merge k1
Updating 9876268..582a8ff
Fast-forward
 file2d | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 file2d

Admin@Admin-PC MINGW32 ~/merge (B1)
$ ls
file1  file2d

Admin@Admin-PC MINGW32 ~/merge (B1)
$ git checkout master
Switched to branch 'master'

Admin@Admin-PC MINGW32 ~/merge (master)
$ git log
commit 43a80bbc281185a5490fed972e4c09f629d9bbf3 (HEAD -> master)
Author: KomalKumra <kumrakomal95@gmail.com>
Date:   Thu May 17 14:21:10 2018 -0500

    1st commit in master file1

Admin@Admin-PC MINGW32 ~/merge (master)
$ ls
file1

Admin@Admin-PC MINGW32 ~/merge (master)
$ vi file1

Admin@Admin-PC MINGW32 ~/merge (master)
$ git add .
warning: LF will be replaced by CRLF in file1.
The file will have its original line endings in your working directory.

Admin@Admin-PC MINGW32 ~/merge (master)
$ git merge B1
error: Your local changes to the following files would be overwritten by merge:
        file1
Please commit your changes or stash them before you merge.
Aborting
Updating 43a80bb..582a8ff

Admin@Admin-PC MINGW32 ~/merge (master)
$ git commit -m "final commit on master"
[master ca9a890] final commit on master
 1 file changed, 1 insertion(+)

Admin@Admin-PC MINGW32 ~/merge (master)
$ git merge B1
Auto-merging file1
CONFLICT (content): Merge conflict in file1
Automatic merge failed; fix conflicts and then commit the result.

Admin@Admin-PC MINGW32 ~/merge (master|MERGING)
$ vi file1

Admin@Admin-PC MINGW32 ~/merge (master|MERGING)
$ git add .

Admin@Admin-PC MINGW32 ~/merge (master|MERGING)
$ git commit -m"Resolving commit"
[master 6428b3e] Resolving commit

Admin@Admin-PC MINGW32 ~/merge (master)
$ git log
commit 6428b3e1a85659d478c208739a41a207b3052800 (HEAD -> master)
Merge: ca9a890 582a8ff
Author: KomalKumra <kumrakomal95@gmail.com>
Date:   Thu May 17 14:32:08 2018 -0500

    Resolving commit

commit ca9a89014e8135ae25932b042aedc839394d6e31
Author: KomalKumra <kumrakomal95@gmail.com>
Date:   Thu May 17 14:30:50 2018 -0500

    final commit on master

commit 582a8ff988ca679bfdf41a5ccd70569a9cab7d95 (k1, B1)
Author: KomalKumra <kumrakomal95@gmail.com>
Date:   Thu May 17 14:28:05 2018 -0500

    Created new file in k1

commit 9876268c789c632a61071e47918993d42f7ee0a7
Author: KomalKumra <kumrakomal95@gmail.com>
Date:   Thu May 17 14:25:58 2018 -0500


Admin@Admin-PC MINGW32 ~/merge (master)
$ git remote add origin https://github.com/KomalKumraCoder/MergeGithubFiles

Admin@Admin-PC MINGW32 ~/merge (master)
$ git remote -v
origin  https://github.com/KomalKumraCoder/MergeGithubFiles (fetch)
origin  https://github.com/KomalKumraCoder/MergeGithubFiles (push)

Admin@Admin-PC MINGW32 ~/merge (master)
$ git push -f origin master
Username for 'https://github.com': KomalKumraCoder
Counting objects: 15, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (8/8), done.
Writing objects: 100% (15/15), 1.20 KiB | 72.00 KiB/s, done.
Total 15 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/KomalKumraCoder/MergeGithubFiles
 + 72baf80...6428b3e master -> master (forced update)

