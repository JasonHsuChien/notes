设置Github ssh

C:\Users\jasonxuqian>ssh-keygen -t rsa -C "847741840@qq.com"
Generating public/private rsa key pair.
Enter file in which to save the key (C:\Users\jasonxuqian/.ssh/id_rsa): id_rsa_github
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in id_rsa_github.
Your public key has been saved in id_rsa_github.pub.
The key fingerprint is:
SHA256:9toKwqSMpv3iWWtHqt/zB1hbwiGhfM465NW4KWQlxpU 847741840@qq.com
The key's randomart image is:
+---[RSA 3072]----+
|      oo         |
|   o oE .        |
|    * oo .       |
|   . * o+ .      |
|    = =oS+       |
| o O oo+o.       |
|..o Oo+  ..      |
|o..oo*o. o.      |
|..=*+..o+o.      |
+----[SHA256]-----+

生成id_rsa_github和id_rsa_github.pub文件，在C:\Users\jasonxuqian目录下



push代码没有权限

JasonXuqian@CNM19FKY33 MINGW64 /c/Jason/Git Jason/notes (master)
$ git push -u origin master
ssh: connect to host github.com port 22: Connection timed out
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.



在id_rsa_github相同目录下新建一个config文件

文件内容如下

Host github.com
User git
Hostname ssh.github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa_github
Port 443



C:\Users\jasonxuqian>ssh -T git@github.com
The authenticity of host '[ssh.github.com]:443 ([20.205.243.160]:443)' can't be established.
ECDSA key fingerprint is SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM.
Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: yes
Warning: Permanently added '[ssh.github.com]:443,[20.205.243.160]:443' (ECDSA) to the list of known hosts.
Hi JasonHsuChien! You've successfully authenticated, but GitHub does not provide shell access.



push成功

JasonXuqian@CNM19FKY33 MINGW64 /c/Jason/Git Jason/notes (master)
$ git push -u origin master
Enumerating objects: 20, done.
Counting objects: 100% (20/20), done.
Delta compression using up to 8 threads
Compressing objects: 100% (17/17), done.
Writing objects: 100% (20/20), 34.46 KiB | 1.57 MiB/s, done.
Total 20 (delta 0), reused 0 (delta 0)
To github.com:JasonHsuChien/notes.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.





https://zhuanlan.zhihu.com/p/149288774?from_voters_page=true