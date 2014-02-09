git-task-1 mkdir r1
git-task-1 cd r1
r1 touch fileA.txt
r1 touch fileB.txt
r1 git init r1-hh
r1 git add fileA.txt fileB.txt
r1 git init .
r1 git add --all
r1 git commit -m "initial commit"
r1 git checkout -b "branch1"
r1 cd ../
git-task-1 git clone r1 r2
r1 cd r2 && git checkout branch1
r2 touch fileC.txt
r2 git add fileC.txt
r2 git commit -m "new file in repo2"
r2 git remote add paren  ../r1/
r2 git push paren branch1
r2 cd ../r1/ && git config receive.denyCurrentBranch ignore
r1 cd -
r2 git push paren branch1
r1 cd ../r1/ && vim fileC.txt
r1 git checkout -- fileC.txt
r1 vim fileC.txt 
r1 git add fileC.txt && git commit -m "fileC modified in r1 repo"
r1 cd ../r2/ && vim fileC.txt
r2 git add fileC.txt 
r2 git commit -m "fileC.txt modified in r2 repo"
r2 git fetch paren branch1
r2 git merge paren/branch1
r2 git add fileC.txt
r2 git add fileC.txt && git commit -m "fileC merge conflict resolved"
r2 cd ../r1/ 
r1 git pull newremote branch1
r1 git checkout -- fileC.txt 
r1 git add fileC.txt
r1 git checkout -- fileC.txt 
r1 git pull newremote branch1
r1 git add fileC.txt 
r1 git commit -m "commit of acdidentally modified fileC"
r1 git pull newremote branch1
r1 git add fileC.txt 
r1 git commit -m "merge conflict resolved"
r1 cd ../r2/
r2 git remote add github git@github.com:danila-hh/repoB.git
r2 git push github branch1
r2 cd ../r1/
r1 git remote add github git@github.com:danila-hh/repoA.git
r1 git push github branch1
