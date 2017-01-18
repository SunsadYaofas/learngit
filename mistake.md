1.linux实在每个用户的主目录中查看 .ssh文件夹之下是否含有id_rsa和id_rsa.puh文件，因此每一个linux这种多用户系统必然面对不同的用户有不同的ssh。<br>
   关于<br>
   [配置ssh](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001374385852170d9c7adf13c30429b9660d0eb689dd43a000)
   有详细的介绍，可以参考<br>
2.可通过ssh -T git@github.com 来查看ssh访问权限，以本机为例<br>

root@sun-Lenovo:/home/sun/new# ssh -T git@github.com<br>
Hi SunsadYaofas! You've successfully authenticated, but GitHub does not provide shell access.<br>
3.git clone git@github.com:SunsadYaofas/learngit
4.这里分为两种情况，一种是当暂存区中有文件时，另一种是暂存区中没有文件。<br>
（1）当暂存区中没有文件时，git diff比较的是，工作区中的文件与上次提交到版本库中的文件。<br>
（2）当暂存区中有文件时，git diff则比较的是，当前工作区中的文件与暂存区中的文件。<br>
而 git diff HEAD -- file，比较的是工作区中的文件与版本库中文件的差异。HEAD指向的是版本库中的当前版本，而file指的是当前工作区中的文件。<br>
补充：git diff命令比较的是工作目录中当前文件与暂存区快照之间的差异，也就是修改之后还没有暂存起来的变化内容。<br>
注意：git diff本身只显示尚未暂存的改动，而不是自上次提交以来所做的所有改动。所以，有时候你一下子暂存了所有更新过的文件后，运行git diff后却什么也没有，<br>就是这个原因。<br>
如果要查看已暂存的将要添加到下次提交里的内容，可以使用git diff --cached或者git diff --staged。


