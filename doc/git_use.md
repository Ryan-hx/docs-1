# gitʹ��

�½�һ��git��Ŀ�����͵�git������
׼������:
     1�� �½�һ���ļ�����Ϊ��Ŀ�ĸ�Ŀ¼����demo
     2����Զ�̷��������½�һ���ֿ⼴new  respositories���������������½��õĲֿ� ��https��https://github.com/johnxue2013/ocdemo.gitgit
     3�����벽��һ���½����ļ���demo���һ�ѡ��git bash here��windows�������������������mac����linux�ϣ���Ҫ���ն� Ҳ���������н��룩
     4��ִ����������
git initgit add README.md
git commit -m "first commit"
git remote add origin https://github.com/johnxue2013/ocdemo.gitgit
push -u origin master


�����еı��زֿ����͵�Զ�̷�����
     
     git remote add origin https://github.com/johnxue2013/ocdemo.git
     git push -u origin master


�������ݵ�Զ�ֿ̲�
     git push [remote-name] [branch-name]
    ���ͣ������زֿ��е��������͵�Զ�ֿ̲�,��ѱ��ص�master��֧���͵�origin�������ϵ�master��֧��(�ٴ�˵���£���¡�������Զ�ʹ��Ĭ�ϵ�master��ΪĬ�Ϸ�֧��origin��ΪԶ�ֿ̲��ڱ��صı���), ʹ��
     git push origin master

Զ�ֿ̲��ɾ����������
���°� Git �п�����
  git remote rename
�����޸�ĳ��Զ�ֿ̲��ڱ��صļ�ƣ�������� pb �ĳ� paul��������ô����:
     git remote rename pb paul
ע�⣬��Զ�ֿ̲����������Ҳ��ʹ��Ӧ�ķ�֧���Ʒ����仯��ԭ���� pb/master ��֧���ڳ��� paul/master��

������ͻʱ�ķ�֧�ϲ�
     ��ʱ��ϲ��������������˳��������ڲ�ͬ�ķ�֧�ж��޸���ͬһ���ļ���ͬһ���֣�Git ���޷��ɾ��ذ����ߺϵ�һ��
Git ���˺ϲ�����û���ύ������ͣ������������ͻ��Ҫ������Щ�ļ��ںϲ�ʱ������ͻ�������� git status ����,
�ϲ��ļ�����ɾ��<<<<<<<��======= �� >>>>>>> ��Щ�С��ڽ���������ļ�������г�ͻ������ git add �������Ǳ��Ϊ�ѽ��״̬,
��ʱֱ������git commit -m "XXX"�Ϳ�����ɴ˴κϲ�,�������ٴ�����git merge {branch-name}

Զ�̷�֧�����ݺϲ�����ǰ��֧(git pull)
     ���Ҫ�Ѹ�Զ�̷�֧serverfix�����ݺϲ�����ǰ��֧����������
     git merge origin/serverfix
�����Ҫһ���Լ��� serverfix ��������������Զ�̷�֧�Ļ����Ϸֻ���һ���µķ�֧��:����git checkout -b serverfix origin/serverfix


git pull ����������ǣ�ȡ��Զ������ĳ����֧�ĸ��£����뱾��ִ�еķ�֧�ϲ�������������ʽ�����е㸴�ӡ�
     $ git pull <Զ��������> <Զ�̷�֧��>:<���ط�֧��>
����ȡ��origin������next��֧���뱾�ص�master��֧�ϲ�����Ҫд��
    $ git pull origin next:master
���Զ�̷�֧���뵱ǰ��֧�ϲ�����ð�źͺ���ķ�֧������ʡ��
    $ git pull origin next
���������ʾȡ��origin�ϵ�next��֧�����뵱ǰ��֧�ϲ���ʵ���ϣ����ͬ������git fetch������ git merge��
    $ git fetch origin
    $ git merge origin/next


��ĳЩ���ϣ�git���Զ��ڱ��ط�֧��Զ�̷�֧֮�䣬����һ��׷�ٹ�ϵ(tracking)�����磬��git clone��ʱ�����б��ط�֧Ĭ����Զ��������ͬ����֧������׷�ٹ�ϵ��Ҳ����˵�����ص�master��֧�Զ�׷��"origin/master��֧


git�����ֶ�����׷��׷�ٹ�ϵ��
     $ git branch --set-upstream master origin/next
     tips����������������Ƽ�ʹ��git branch --set-upstream-to=<Զ��������>/<Զ�̷�֧��> <���ط�֧��>
���������ָ������master��֧׷��Զ��origin/next��֧�������ǰ��֧��Զ�̷�֧����׷�ٹ�ϵ��git pull�Ϳ���ʡ��Զ�̷�֧����
     $ git pull origin 
����������ʾ�����صĵ�ǰ��֧�Զ����Ӧ��origin����"׷�ٷ�֧"���кϲ��������ǰ��ֻ֧��һ��׷�ٷ�֧������������������ʡ�ԡ�
     $ git pull
���������ʾ����ǰ��֧�Զ���Ψһ׷�ٷ�֧���кϲ���

���������ύ��Զ��(git push)
git push�������ڽ����ط�֧�ĸ��£����͵�Զ�����������ĸ�ʽ��git pull������¡�
     $ git push <Զ��������> <���ط�֧����>:<Զ�̷�֧��>
     ע�⣺��֧���͵�˳����<���ط�֧����>:<Զ�̷�֧��>����git pull��<Զ�̷�֧��>:<���ط�֧��>�������෴��
���ʡ��Զ�̷�֧�������ʾ�����ط�֧������֮���ڡ�׷�ٹ�ϵ����Զ�̷�֧(ͨ������ͬ��), �����Զ�̷�֧�����ڣ���ᱻ�½���
     $ git push origin master
����������ʾ�������ص�master��֧���͵�origin������master��֧�����origin����������master��֧����origin���½�master��֧��

���ʡ�Ա��ط�֧�������ʾɾ��ָ����Զ�̷�֧����Ϊ���ͬ������һ���յı��ط�֧��Զ�̷�֧��
     $ git push origin :master
��ͬ��
     $ git push origin --delete master
�����ǰ���ڷ�֧��Զ�̷�֧֮�����׷�ٹ�ϵ����pushʱ�����ط�֧��Զ�̷�֧������ʡ��·��
     $ git push origin
���������ʾ������ǰ��֧���͵�origin��Ӧ�ķ�֧��

�����ǰ��ֻ֧��һ��׷�ٷ�֧����ô������������ʡ�ԡ�
     $ git push
�����ǰ��֧������������׷�ٹ�ϵ�����ʹ��-uѡ��ָ��һ��Ĭ������
     $ git push -u origin master
�����������ص�master��֧���͵�origin������׷�ٵķ�֧��ͬʱָ��originΪĬ����������������Ϳ��Բ����κβ���ʹ��git push�ˡ�


����(Stash)
���������������鷢�����������ڽ�����Ŀ��ĳһ���ֵĹ���������Ķ�������һ���Ƚ����ҵ�״̬��������ת��������֧�Ͻ���һЩ�����������ǣ��㲻���ύ������һ��Ĺ����������Ժ����޷��ص���������㡣����������İ취����git stash���
�������ء������Ի�ȡ�㹤��Ŀ¼���м�״̬����Ҳ�������޸Ĺ��ı�׷�ٵ��ļ����ݴ�ı���������������浽һ��δ������Ķ�ջ�У���ʱ��������Ӧ�á�


���磬������git status����,�������½��
���������л���֧,git�ᱨ���޷���ɷ�֧�л�����������л�����Ҫʹ��git stash���


��ʱ������git status �������ʾ��ķ�֧�Ǹɾ���
��ʱ��Ϳ����л���������֧���й����ˣ������Ҫ�ָ�stashʱ�ĳ�����ʹ��git stash apply, ����ʹ��git stash list�����г����е�
stash��¼��
��Ҳ����ʹ��git stash apply stash@{2}��ȥָ���ָ���һ��stash��Ĭ�������git stash applyʹ�����һ�ε�stash��

applyѡ��ֻ�ǳ���Ӧ�ô洢�Ĺ���---stash��������Ȼ��ջ�ϡ�Ҫ�Ƴ��������������git stash drop <stash-name>��
��Ҳ��������git stash pop <stash-name>������Ӧ�ô洢��ͬʱ���̽���Ӷ�ջ�����ߡ�

PS: ����ҪstashʱЯ��ע�ͣ���ʹ��git stash save <ע��>����: git stash save "�ݴ�bug123"

git branch�����ʹ��

 git branch �����������г������Ѿ����ڵķ�֧�������ڵ�ǰ��֧��ǰ��ӡ�*���ű�ǣ����磺
   #git branch
   * master
   newbranch

   git branch -r �г�Զ�̷�֧�����磺
   #git branch -r
   m/master -> origin_apps/m1_2.3.4
   origin_apps/hardware/test
   origin_apps/m1
   origin_apps/m1_2.3.4
   origin_apps/master

   git branch -a �г����ط�֧��Զ�̷�֧�����磺
   #git branch -a
   * master
   newbranch
   remotes/m/master -> origin_apps/m1_2.3.4
   remotes/origin_apps/hardware/test
   remotes/origin_apps/m1
   remotes/origin_apps/m1_2.3.4
   remotes/origin_apps/master

   git branch ����һ���µı��ط�֧����Ҫע�⣬�˴�ֻ�Ǵ�����֧�������з�֧�л������磺
   #git branch newbranch2
   #git branch
   * master
   newbranch
   newbranch2
   ��ǰ�ķ�֧��Ȼ��master���������л���

   git branch -m | -M oldbranch newbranch ��������֧�����newbranch���ַ�֧�Ѿ����ڣ�����Ҫʹ��-Mǿ��������������ʹ��-m������������

   git branch -d | -D branchname ɾ��branchname��֧

   git branch -d -r branchname ɾ��Զ��branchname��֧


���ӣ�
git help branch�е�һ�����ӣ�
   $ git clone git://git.kernel.org/pub/scm/.../linux-2.6 my2.6
   $ cd my2.6
   $ git branch my2.6.14 v2.6.14   
   $ git checkout my2.6.14      
   �����з���git branch <branchname> [<start-point>]�ĸ�ʽ������v2.6.14Ϊstart-point�������µı��ط�֧branchname��


   ���������˵İ汾ǿ�ƻָ�(����)��ĳһ���ύ
     1������ʹ��git log����ҵ�����ָ�����һ�ε��ύ��commit id
     
     2��ʹ�� git reset --hard <commit_id>����

     3��ʹ��git push <clone�����ķ���������> HEAD --force���� git push origin HEAD --force


��������Ŀ����git������ʹ�������н�������Ŀ����github
git initgit add README.mdgit commit -m "first commit"
git remote add origin https://github.com/johnxue2013/medicinerecommendation.git
git push -u origin master

���Ѿ�����git�������Ŀ����github
git remote add origin https://github.com/johnxue2013/medicinerecommendation.git
git push -u origin master

һ����Ŀͬʱ����Զ�̷���������ͬ��
      ������Ŀ��ʱ��һ�㹫˾���Լ�git�������������ϰ�ʱ�����������������ͬ����һ��������������Ǿ������ڿɷ��ʣ���������������
�����ʹ���һ�����⣬����°�֮����Ҫ������д���룬�������ڵڶ����ϰ�ʱ��ͬ�����Լ��°�֮��д�Ĵ������ô�죿��ʱ�����ڹ�˾�ĵ����Ͻ���˾����Ŀͬʱ������Զ�̷���������ͬ����һ���һ�δ�git����ȡ��Ŀʱ(׼ȷ��˵��clone)��gitĬ�ϻὫ��ȡ��������Ŀ������������Ϊorigin�����������git clone <��Ŀurl> ֮������git remote show������git remote -v ���в鿴��
����ͼ����ʱ�ҵ�medicinerecommendation��Ŀ����������Զ�̷���������ͬ����һ����10.1.64.87������ǹ�˾��git����������һ����github��������

     Ĭ������£�clone��������Ŀֻ��һ��git����������ͬ��(��������÷���������push��fetch)������git remote add <Զ�̷���������> <Զ�ֿ̲�����URL>������һ��Զ�̷����������޴���(�����������������������������һ������origin�ķ�������������ʱ��ӵڶ���Զ�̷�����ʱ���������ٽ���origin)��������git remote show,�����ֶ��Զ�̷�֧.
     ��һ����Ŀ�ж��Զ�̷�����������£�push��fetch���Ǻ�һ����Ŀ��һ��Զ�̷�����һ���ġ�����Ҫ�ύ���뵽mr��������git push mr <���ط�֧��>:<��������֧��>,��Ҳ����ָ��һ��Ĭ�ϵ�Զ�̷�֧��ͨ��git push -u mr dev:dev �����ύ���ط�֧dev��Զ�̷�����ͬ����֧dev����ָ��mrΪĬ�Ϸ������� ��ʱmr����������Ϊ����Ŀ��Ĭ�Ϸ���������push��ָ��������ʱ��mr����Ϊȱʡֵ��

gitǿ�Ƹ��Ƿ�����
     ���������ϵĴ����ĺ��һ��д���ʱ�������صĴ���ȷʵ��������ȷ�ģ���ʱ����ʹ�ñ��ش���ǿ�Ƹ��Ƿ��������룬
     ʹ�� git push <����������> <���ط�֧��>:<��������֧��> --force
     
git��κ����Ѿ��ύ���ļ�
     ��������ĳЩ�ļ����ļ����Ҹ��ļ����ļ��д�δ���ύ��������ֱ������Ŀ��Ŀ¼����git�����д�����ʹ��touch .gitignore�����½�һ���ļ����ڸ��ļ��������Ҫ���Ե��ļ����ļ��У�
�������Ŀ��Ŀ¼�µ�.idea�ļ��У���.gitignore�ļ�������Ӧ��������������ӡ�

     /.idea

       ��ʱ��С���ύ�˲����ύ���ļ�����ĳЩ�����ļ������ύ֮������.gitignore���ú��Խ��������ã���Ϊ���ļ�ֻ��������Untrack Files��
Ҳ���Ǵ���û�б�git��¼�����ļ�(������Ժ󣬴�δadd�Լ�commit�����ļ�)��Ҳ����˵һ��add����commit֮�󣬸��ļ������ļ��оʹ���track file��
��ʱ���޸�.gitignore��Ȼ�Ͳ��������ˡ���ʱ��ȷ��������ʹ��
     git rm --cached <�ļ���>
Ȼ���޸�.gitignore���ú��ԣ����
     git add .gitignore
��
     git commit -"ע��"
��
     git push <����������> <���ط�֧��>:<��������֧��>
���˷������������������Ե��ļ������ļ��С�

˵��: git rm --cached <�ļ���>  ɾ������׷��״̬�������������ļ���������治��Ҫ�ˣ������ʹ��ֱ��ʹ��rm ����ɾ�����ļ����ļ���


tag���ǩ
      ͬ����� VCS һ����Git Ҳ���Զ�ĳһʱ����ϵİ汾���ϱ�ǩ�������ڷ���ĳ������汾������ v1.0 �ȵȣ���ʱ�򣬾�����ô������������һ����ѧϰ����г����п��õı�ǩ������½���ǩ���Լ����ֲ�ͬ���ͱ�ǩ֮��Ĳ��
     �г����еı�ǩ�г����б�ǩ������ǳ��򵥣�ֱ������ git tag ���ɣ�
$ git tag
v0.1
v1.3
��ʾ�ı�ǩ����ĸ˳�����У����Ա�ǩ���Ⱥ󲢲���ʾ��Ҫ�̶ȵ����ء�
���ǿ������ض�������ģʽ�г����������ı�ǩ���� Git ������Ŀ�ֿ��У����ų��� 240 ����ǩ�������ֻ�� 1.4.2 ϵ�еİ汾����Ȥ������������������
$ git tag -l 'v1.4.2.*'
v1.4.2.1
v1.4.2.2
v1.4.2.3
v1.4.2.4
�½���ǩGit ʹ�õı�ǩ���������ͣ��������ģ�lightweight���ͺ���ע�ģ�annotated������������ǩ�����Ǹ�����仯�ķ�֧��ʵ���������Ǹ�ָ���ض��ύ��������á�������ע��ǩ��ʵ�����Ǵ洢�ڲֿ��е�һ�������������������У�����Ϣ�������ű�ǩ�����֣������ʼ���ַ�����ڣ��Լ���ǩ˵������ǩ����Ҳ����ʹ�� GNU Privacy Guard (GPG) ��ǩ�����֤��һ�����Ƕ�����ʹ�ú���ע�͵ı�ǩ���Ա㱣�������Ϣ����Ȼ�����ֻ����ʱ�Լ�ע��ǩ�����߲���Ҫ��ע������Ϣ������������ǩҲû���⡣
����ע�ı�ǩ����һ������ע���͵ı�ǩ�ǳ��򵥣��� -a ����ע��ȡ annotated ������ĸ��ָ����ǩ���ּ��ɣ�
$ git tag -a v1.4 -m 'my version 1.4'
$ git tag
v0.1
v1.3
v1.4
�� -m ѡ����ָ���˶�Ӧ�ı�ǩ˵����Git �Ὣ��˵��һͬ�����ڱ�ǩ�����С����û�и�����ѡ�Git �������ı��༭������������ǩ˵����
����ʹ�� git show ����鿴��Ӧ��ǩ�İ汾��Ϣ������ͬ��ʾ���ǩʱ���ύ����
$ git show v1.4
tag v1.4
Tagger: Scott Chacon <schacon@gee-mail.com>
Date:   Mon Feb 9 14:45:11 2009 -0800

my version 1.4
commit 15027957951b64cf874c3557a0f3547bd83b3ff6
Merge: 4a447f7... a6b4c97...
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sun Feb 8 19:02:46 2009 -0800

    Merge branch 'experiment'
���ǿ��Կ������ύ������Ϣ���棬�г��˴˱�ǩ���ύ�ߺ��ύʱ�䣬�Լ���Ӧ�ı�ǩ˵����
ǩ���ǩ��������Լ���˽Կ���������� GPG ��ǩ���ǩ��ֻ��Ҫ��֮ǰ�� -a ��Ϊ -s ����ע�� ȡ signed ������ĸ�����ɣ�
$ git tag -s v1.5 -m 'my signed 1.5 tag'
You need a passphrase to unlock the secret key for
user: "Scott Chacon <schacon@gee-mail.com>"
1024-bit DSA key, ID F721C45A, created 2009-02-09
���������� git show �ῴ����Ӧ�� GPG ǩ��Ҳ�������ڣ�
$ git show v1.5
tag v1.5
Tagger: Scott Chacon <schacon@gee-mail.com>
Date:   Mon Feb 9 15:22:20 2009 -0800

my signed 1.5 tag
-----BEGIN PGP SIGNATURE-----
Version: GnuPG v1.4.8 (Darwin)

iEYEABECAAYFAkmQurIACgkQON3DxfchxFr5cACeIMN+ZxLKggJQf0QYiQBwgySN
Ki0An2JeAVUCAiJ7Ox6ZEtK+NvZAj82/
=WryJ
-----END PGP SIGNATURE-----
commit 15027957951b64cf874c3557a0f3547bd83b3ff6
Merge: 4a447f7... a6b4c97...
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sun Feb 8 19:02:46 2009 -0800

    Merge branch 'experiment'
�Ժ�������ѧϰ�����֤�Ѿ�ǩ��ı�ǩ��
��������ǩ��������ǩʵ���Ͼ���һ�������Ŷ�Ӧ�ύ�����У�����Ϣ���ļ���Ҫ���������ı�ǩ��һ�� -a��-s �� -m ѡ����ã�ֱ�Ӹ�����ǩ���ּ��ɣ�
$ git tag v1.4-lw
$ git tag
v0.1
v1.3
v1.4
v1.4-lw
v1.5
�������� git show �鿴�˱�ǩ��Ϣ����ֻ����Ӧ���ύ����ժҪ��
$ git show v1.4-lw
commit 15027957951b64cf874c3557a0f3547bd83b3ff6
Merge: 4a447f7... a6b4c97...
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sun Feb 8 19:02:46 2009 -0800

    Merge branch 'experiment'
��֤��ǩ����ʹ�� git tag -v [tag-name] ����ע��ȡ verify ������ĸ���ķ�ʽ��֤�Ѿ�ǩ��ı�ǩ������������ GPG ����֤ǩ������������Ҫ��ǩ���ߵĹ�Կ������� keyring �У�������֤��
$ git tag -v v1.4.2.1
object 883653babd8ee7ea23e6a5c392bb739348b1eb61
type commit
tag v1.4.2.1
tagger Junio C Hamano <junkio@cox.net> 1158138501 -0700

GIT 1.4.2.1

Minor fixes since 1.4.2, including git-mv and git-http with alternates.
gpg: Signature made Wed Sep 13 02:08:25 2006 PDT using DSA key ID F3119B9A
gpg: Good signature from "Junio C Hamano <junkio@cox.net>"
gpg:                 aka "[jpeg image of size 1513]"
Primary key fingerprint: 3565 2A26 2040 E066 C9A7  4A7D C0C6 D9A4 F311 9B9A
����û��ǩ���ߵĹ�Կ���ᱨ���������������Ĵ���
gpg: Signature made Wed Sep 13 02:08:25 2006 PDT using DSA key ID F3119B9A
gpg: Can't check signature: public key not found
error: could not verify the tag 'v1.4.2.1'
���ڼ�ע��ǩ�����������ں��ڶ����ȵ�ĳ���ύ��ע��ǩ������������չʾ���ύ��ʷ�У�
$ git log --pretty=oneline
15027957951b64cf874c3557a0f3547bd83b3ff6 Merge branch 'experiment'
a6b4c97498bd301d84096da251c98a07c7723e65 beginning write support
0d52aaab4479697da7686c15f77a3d64d9165190 one more thing
6d52a271eda8725415634dd79daabbc4d9b6008e Merge branch 'experiment'
0b7434d86859cc7b8c3d5e1dddfed66ff742fcbc added a commit function
4682c3261057305bdd616e23b64b0857d832627b added a todo file
166ae0c4d3f420721acbb115cc33848dfcc2121a started write support
9fceb02d0ae598e95dc970b74767f19372d61af8 updated rakefile
964f16d36dfccde844893cac5b347e7b3d44abbc commit the todo
8a5cbc430f1a9c3d00faaeffd07798508422908a updated readme
�����������ύ ��updated rakefile�� ��Ϊ����Ŀ���ϰ汾�� v1.2��û��ϵ������Ҳ������ֻҪ�ڴ��ǩ��ʱ����϶�Ӧ�ύ�����У��ͣ���ǰ��λ�ַ������ɣ�
$ git tag -a v1.2 9fceb02
���Կ��������Ѿ������˱�ǩ��
$ git tag
v0.1
v1.2
v1.3
v1.4
v1.4-lw
v1.5

$ git show v1.2
tag v1.2
Tagger: Scott Chacon <schacon@gee-mail.com>
Date:   Mon Feb 9 15:32:16 2009 -0800

version 1.2
commit 9fceb02d0ae598e95dc970b74767f19372d61af8
Author: Magnus Chacon <mchacon@gee-mail.com>
Date:   Sun Apr 27 20:43:35 2008 -0700

    updated rakefile
...
�����ǩĬ������£�git push ������ѱ�ǩ���͵�Զ�˷������ϣ�ֻ��ͨ����ʽ������ܷ����ǩ��Զ�˲ֿ⡣�������ʽ��ͬ���ͷ�֧������git push origin [tagname] ���ɣ�
$ git push origin v1.5
Counting objects: 50, done.
Compressing objects: 100% (38/38), done.
Writing objects: 100% (44/44), 4.56 KiB, done.
Total 44 (delta 18), reused 8 (delta 1)
To git@github.com:schacon/simplegit.git
* [new tag]         v1.5 -> v1.5
���Ҫһ���������б��������ı�ǩ��ȥ������ʹ�� --tags ѡ�
$ git push origin --tags
Counting objects: 50, done.
Compressing objects: 100% (38/38), done.
Writing objects: 100% (44/44), 4.56 KiB, done.
Total 44 (delta 18), reused 8 (delta 1)
To git@github.com:schacon/simplegit.git
 * [new tag]         v0.1 -> v0.1
 * [new tag]         v1.2 -> v1.2
 * [new tag]         v1.4 -> v1.4
 * [new tag]         v1.4-lw -> v1.4-lw
 * [new tag]         v1.5 -> v1.5

���ڣ������˿�¡����ֿ����ȡ����ͬ����Ҳ�ῴ����Щ��ǩ��



gitʹ��https��ʽ���ӣ���������ģʽ�¼�ס�������÷�ʽ��

1����������������
   git config credential.helper store
   �س�
2�����ú�ֻҪ������һ�Σ��Ժ�Ͳ���Ҫ�û����������� ֻҪ���к��´�push��ʱ��������һ�����룬git�ͻ��ס






��¼��
0��git status      ��ȡ�㵱ǰ���ڵķ�֧��δtrack���ļ���Ϊtrack���ļ���Ҫʹ��git add [�ļ���]����track
1��git add ...     �����޸ĵĶ����ӵ�git�� //����ʹ�������ύ���� �ύsrc������δtrack���ļ�ʹ������ git add src/
2��git commit -m "����ע��"      ������޸��ύ������
3��git fetch origin [��֧����]      �ѷ������ϵ��ļ���������
4��git merge origin/[��֧����]      �����������ļ����㱾�صķ�֧�ϲ���/����û�пո� ����г�ͻ�����ͻ���ظ�����1,2
5��git checkout [���ط�֧��dev��security]
6��git merge [�㱾�صķ�֧�� *_xh]
7��git push -u origin [��֧����]
8��git checkout [�Լ��ķ�֧]








