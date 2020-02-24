---
layout: post
title: Study notes
date: '2020-01-09T00:04:00.000+07:00'
author: LongNX
tags:
- Software Engineering
---

## Git pulll un-related histories

TLDR:
làm theo cái guide "chuẩn" mà ăn cái error msg `The current branch master has no upstream branch.` vào mặt thì pull bằng lệnh này

```console
git pull --allow-unrelated-histories
```

> Step 1 : Download git, use `git config` to tell git about my username & email. Worked fine.
>
> All the following command were executed in my new local repo's main directory
>
> Step 2 : `git init`. Worked fine.
>
> Step 3 : Do a `git add` on all my files. Worked fine.
>
> Step 4 : Do the first commit : `git commit -m "First commit from new computer"`. Worked fine.
>
>
> Step 5 : Do `git remote add origin https://github.com/roparzhhemon/myremoterepo.git`. Worked fine, according to
> `git remote -v`.
>
>
> Step 6 : `git push`. Got the following error message :
>
> ```console
> fatal: The current branch master has no upstream branch.
> To push the current branch and set the remote as upstream, use
> git push --set-upstream origin master
> ```
>
> Step 7 : Do as I'm told, and type : `git push --set-upstream origin master`. Got the following error message :
>
> ```console
> error: failed to push some refs to [remote repo]
> hint: Updates were rejected because the remote contains work that you do
> hint: not have locally. This is usually caused by another repository pushing
> hint: to the same ref. You may want to first integrate the remote changes
> hint: (e.g., 'git pull ...') before pushing again.
> hint: See the 'Note about fast-forwards' in 'git push --help' for details.
> ```
>
> Step 8 : Do as I'm told, and type : `git pull`. Got the following message :
>
> ```console
> warning: no common commits
> remote: Counting objects: 11450, done.
> remote: Compressing objects: 100% (17/17), done.
> remote: Total 11450 (delta 13), reused 17 (delta 8), pack-reused 11425
> Receiving objects: 100% (11450/11450), 1.96 MiB | 2.65 MiB/s, done.
> Resolving deltas: 100% (7710/7710), done.
> From [remote repo]
> * [new branch] master -> origin/master
> There is no tracking information for the current branch.
> Please specify which branch you want to merge with.
> See git-pull(1) for details.
> git pull <remote> <branch>
> If you wish to set tracking information for this branch you can do so with:
> git branch --set-upstream-to=origin/<branch> master
> ```
>
> Step 9 : Do as I'm told, and type : `git branch --set-upstream-to=origin/master master`. Seemed to work, output the following :
>
> ```console
> Branch 'master' set up to track remote branch 'master' from 'origin'.
> ```
>
> Step 10 : Try `git pull` again. Got the error message :
>
> ```console
> fatal: refusing to merge unrelated histories
> ```
>
> Step 11 : Try `git push` again. Got the error message :
>
> ```console
> To [remote repo]
> ! [rejected] master -> master (non-fast-forward)
> error: failed to push some refs to [remote repo]
> hint: Updates were rejected because the tip of your current branch is behind
> hint: its remote counterpart. Integrate the remote changes (e.g.
> hint: 'git pull ...') before pushing again.
> hint: See the 'Note about fast-forwards' in 'git push --help' for details.
> ```
>
