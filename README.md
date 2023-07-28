User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git add team.html

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash save "team"
Saved working directory and index state On dev: team

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash list
stash@{0}: On dev: team
stash@{1}: On dev: about
stash@{2}: On dev: home

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash pop stash@{1}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Dropped stash@{1} (b30851e838b4d9b5e3449adaa1edb0056e49ccbf)

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash list
stash@{0}: On dev: team
stash@{1}: On dev: home

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash apply --index stash@{1}
error: Your local changes to the following files would be overwritten by merge:
  about.html
Index was not unstashed.
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        about.html

nothing added to commit but untracked files present (use "git add" to track)

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git add .

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash apply --index stash@{1}
error: Your local changes to the following files would be overwritten by merge:
  about.html
Index was not unstashed.
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        about.html

nothing added to commit but untracked files present (use "git add" to track)

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash apply --index stash@{2}
fatal: log for 'stash' only has 2 entries

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git add about.html 

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash apply --index stash@{2}
fatal: log for 'stash' only has 2 entries

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash apply --index stash@{1}
error: Your local changes to the following files would be overwritten by merge:
  about.html
Index was not unstashed.
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        about.html

nothing added to commit but untracked files present (use "git add" to track)

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git commit -m "current changes"
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        about.html

nothing added to commit but untracked files present (use "git add" to track)

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git add .

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash apply --index stash@{1}
error: Your local changes to the following files would be overwritten by merge:
  about.html
Index was not unstashed.
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        about.html

nothing added to commit but untracked files present (use "git add" to track)

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git commit -m "current changes"
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        about.html

nothing added to commit but untracked files present (use "git add" to track)

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git push origin main
Everything up-to-date

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$
 *  History restored 


User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git add .

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git commit -m "commits"
[dev b5f08ec] commits
 1 file changed, 9 insertions(+)
 create mode 100644 about.html

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git push origin dev
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 416 bytes | 416.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'dev' on GitHub by visiting:
remote:      https://github.com/Angekarara/git/pull/new/dev
remote:
To https://github.com/Angekarara/git.git
 * [new branch]      dev -> dev

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash ls
fatal: subcommand wasn't specified; 'push' can't be assumed due to unexpected token 'ls'

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ ls
about.html  file.html

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash list
stash@{0}: On dev: team
stash@{1}: On dev: home

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash save "Temporary changes for the team page index"
No local changes to save

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git stash pop stash@{0}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html

Dropped stash@{0} (85df62a508cc3922aab5bf67d0734c65a2d24abe)

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git status
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html


User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git reset team.html

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git checkout -- team.html
error: pathspec 'team.html' did not match any file(s) known to git

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (dev)
$ git checkout -b ft/bundle-2
Switched to a new branch 'ft/bundle-2'

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/bundle-2)
$ git add .

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/bundle-2)
$ echo services.html
services.html

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/bundle-2)
$ touch services.html

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/bundle-2)
$ git add .

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/bundle-2)
$ git commit -m "commits"
[ft/bundle-2 c79b84d] commits
 2 files changed, 9 insertions(+)
 create mode 100644 services.html
 create mode 100644 team.html

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/bundle-2)
$ git push origin main 
Everything up-to-date

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/bundle-2)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (main)
$ git checkout ft/bundle-2 
Switched to branch 'ft/bundle-2'

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/bundle-2)
$ git push origin ft/bundle-2 
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 490 bytes | 490.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'ft/bundle-2' on GitHub by visiting:
remote:      https://github.com/Angekarara/git/pull/new/ft/bundle-2
remote:
To https://github.com/Angekarara/git.git
 * [new branch]      ft/bundle-2 -> ft/bundle-2

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/bundle-2)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (main)
$ git pull origin main
remote: Enumerating objects: 2, done.
remote: Counting objects: 100% (2/2), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 2 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (2/2), 1.21 KiB | 206.00 KiB/s, done.
From https://github.com/Angekarara/git
 * branch            main       -> FETCH_HEAD
   1bb4431..f83a890  main       -> origin/main
Updating 1bb4431..f83a890
Fast-forward
 about.html    | 9 +++++++++
 services.html | 9 +++++++++
 team.html     | 0
 3 files changed, 18 insertions(+)
 create mode 100644 about.html
 create mode 100644 services.html
 create mode 100644 team.html

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (main)
$ git checkout -b ^C

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (main)
$ git checkout -b ft/service-redesign
Switched to a new branch 'ft/service-redesign'

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign)
$ git add services.html 

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign)
$ git commit -m "service"
[ft/service-redesign 9ceac53] service
 1 file changed, 1 insertion(+), 1 deletion(-)

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign)
$ git push origin ft/service-redesign 
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 282 bytes | 282.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote:
remote: Create a pull request for 'ft/service-redesign' on GitHub by visiting:
remote:      https://github.com/Angekarara/git/pull/new/ft/service-redesign
remote:
To https://github.com/Angekarara/git.git
 * [new branch]      ft/service-redesign -> ft/service-redesign

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign)
$ git che
checkout      cherry        cherry-pick   

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign)
$ git checkout main 
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (main)
$ git add services.html

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (main)
$ git commit -m "service"
[main 4967bd9] service
 1 file changed, 1 insertion(+), 1 deletion(-)

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (main)
$ git push origin main 
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 282 bytes | 282.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Angekarara/git.git
   f83a890..4967bd9  main -> main

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (main)
$ git checkout ft/service-redesign 
Switched to branch 'ft/service-redesign'

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign)
$ git pull origin main
From https://github.com/Angekarara/git
 * branch            main       -> FETCH_HEAD
Auto-merging services.html
CONFLICT (content): Merge conflict in services.html
Automatic merge failed; fix conflicts and then commit the result.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign|MERGING)
$ git checkout ft/service-redesign
error: you need to resolve your current index first
services.html: needs merge

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign|MERGING)
$ git diff main
diff --git a/services.html b/services.html
index e1d0db6..b118eaa 100644
--- a/services.html
+++ b/services.html
@@ -3,7 +3,11 @@
   <head>
     <meta charset="UTF-8" />
     <meta name="viewport" content="width=device-width, initial-scale=1.0" />
+<<<<<<< HEAD
+    <title>servicesss</title>
+=======
     <title>services1</title>
+>>>>>>> 4967bd9078c373250cbbf1eac90a9ac94646216e
   </head>

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign|MERGING)
$ git merge main
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign|MERGING)
$ git merge main
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign|MERGING)
$ git pull origin ft/service-redesign 
error: Pulling is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign|MERGING)
$ git merge ft/service-redesign 
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign|MERGING)
$ git merge main
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign|MERGING)
$ git merge main
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign|MERGING)
$ git merge main
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign|MERGING)
$ git merge main
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign|MERGING)
$ git add .

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign|MERGING)
$ git commit -m "service"
[ft/service-redesign 368a2b7] service

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign)
$ git push origin main
To https://github.com/Angekarara/git.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/Angekarara/git.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign)
$ git push origin ft/service-redesign
To https://github.com/Angekarara/git.git
 ! [rejected]        ft/service-redesign -> ft/service-redesign (fetch first)
error: failed to push some refs to 'https://github.com/Angekarara/git.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

User@DESKTOP-18JCNLB MINGW64 ~/Desktop/git (ft/service-redesign)
$# git
