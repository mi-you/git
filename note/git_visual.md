# part 1

- `git checkout -b bugFix` : 新建并切换到 bugFix 分支
- `git checkout main`; `git merge bugFix` : 把 bugFix 合并到 main 上
- `git checkout bugFix`; `git rebase main` : 变基 bugFix
- HEAD 一般指向的是分支名，可以通过 `git checkout <hash>` 让其指向某一特定记录。这是 HEAD 的分离（不指向分支名）
- `git checkout main^`: 向上移动一个节点
- `git checkout main^^^`: 向上移动三个节点
- `git branch -f main HEAD~3`: 让 main 分支强行之前第三级父提交
- git reset: 通过把分支记录回退几个提交记录来实现撤销改动。你可以将这想象成“改写历史”。git reset 向上移动分支，原来指向的提交记录就跟从来没有提交过一样。`git reset HEAD~1`
- git revert: 虽然在你的本地分支中使用 git reset 很方便，但是这种“改写历史”的方法对大家一起使用的远程分支是无效的哦！为了撤销更改并分享给别人，我们需要使用 `git revert HEAD`
- `git cherry-pick hash1 hash2 hash3`: 把 hash1,2,3 提交到当前分支
- 交互式 rebase 指的是使用带参数 --interactive 的 rebase 命令, 简写为 -i。 `git rebase -i HEAD~4`
- `git commit --amend`: 修改提交描述
- `git tag v1.0 <hash>`: 我们将这个标签命名为 v1.0，并且明确地让它指向提交记录<hash>，如果你不指定提交记录，Git 会用 HEAD 所指向的位置
- 由于标签在代码库中起着“锚点”的作用，Git 还为此专门设计了一个命令用来描述离你最近的锚点（也就是标签），它就是 git describe。
  `git describe <ref>` <ref> 可以是任何能被 Git 识别成提交记录的引用，如果你没有指定的话，Git 会以你目前所检出的位置（HEAD）。
  它输出的结果是这样的： <tag>\_<numCommits>\_g<hash> tag 表示的是离 ref 最近的标签， numCommits 是表示这个 ref 与 tag 相差有多少个提交记录， hash 表示的是你所给定的 ref 所表示的提交记录哈希值的前几位。当 ref 提交记录上有某个标签时，则只输出标签名称
- `git branch bugWork main^^2~`: 在特定的提交记录创建新分支，但是并没有切换过去
- show solution
