###���������ݴ���

Git�������汾����ϵͳ��SVN��һ����֮ͬ���������ݴ����ĸ��

���������ʽ��͡�

###��������Working Directory��

�������ڵ������ܿ�����Ŀ¼�������ҵ�learngit�ļ��о���һ����������

working-dir

###�汾�⣨Repository��

��������һ������Ŀ¼.git��������㹤����������Git�İ汾�⡣

Git�İ汾������˺ܶණ������������Ҫ�ľ��ǳ�Ϊstage�����߽�index�����ݴ���������GitΪ�����Զ������ĵ�һ����֧master���Լ�ָ��master��һ��ָ���HEAD��

git-repo

��֧��HEAD�ĸ��������Ժ��ٽ���

ǰ�潲�����ǰ��ļ���Git�汾�������ӵ�ʱ���Ƿ�����ִ�еģ�

��һ������git add���ļ����ӽ�ȥ��ʵ���Ͼ��ǰ��ļ��޸����ӵ��ݴ�����

�ڶ�������git commit�ύ���ģ�ʵ���Ͼ��ǰ��ݴ��������������ύ����ǰ��֧��

��Ϊ���Ǵ���Git�汾��ʱ��Git�Զ�Ϊ���Ǵ�����Ψһһ��master��֧�����ԣ����ڣ�git commit������master��֧���ύ���ġ�

����Լ�����Ϊ����Ҫ�ύ���ļ��޸�ͨͨ�ŵ��ݴ�����Ȼ��һ�����ύ�ݴ����������޸ġ�

�׻�˵��ʵ������֪�����ڣ���������ϰһ�飬�ȶ�readme.txt�����޸ģ��������һ�����ݣ�

Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Ȼ���ڹ���������һ��LICENSE�ı��ļ����������д����

����git status�鿴һ��״̬��

$ git status
~ On branch master
~ Changes not staged for commit:
~   (use "git add <file>..." to update what will be committed)
~   (use "git checkout -- <file>..." to discard changes in working directory)
~
~       modified:   readme.txt
~
~ Untracked files:
~   (use "git add <file>..." to include in what will be committed)
~
~       LICENSE
no changes added to commit (use "git add" and/or "git commit -a")
Git�ǳ�����ظ������ǣ�readme.txt���޸��ˣ���LICENSE������û�б����ӹ�����������״̬��Untracked��

���ڣ�ʹ����������git add����readme.txt��LICENSE�����Ӻ���git status�ٲ鿴һ�£�

$ git status
~ On branch master
~ Changes to be committed:
~   (use "git reset HEAD <file>..." to unstage)
~
~       new file:   LICENSE
~       modified:   readme.txt
~
���ڣ��ݴ�����״̬�ͱ�������ˣ�

git-stage

���ԣ�git add����ʵ���Ͼ��ǰ�Ҫ�ύ�������޸ķŵ��ݴ�����Stage����Ȼ��ִ��git commit�Ϳ���һ���԰��ݴ����������޸��ύ����֧��

$ git commit -m "understand how stage works"
[master 27c9860] understand how stage works
 2 files changed, 675 insertions(+)
 create mode 100644 LICENSE
һ���ύ���������û�жԹ��������κ��޸ģ���ô���������ǡ��ɾ����ģ�

$ git status
~ On branch master
nothing to commit (working directory clean)
���ڰ汾�������������ݴ�����û���κ������ˣ�

git-stage-after-commit

С��

�ݴ�����Git�ǳ���Ҫ�ĸ��Ū�������ݴ�������Ū������Git�ĺܶ�������׸���ʲô��