**ǰ���ǣ��Ѿ���װ��Vscode��Git**
1. �½��ļ�������Vscodeͼ��(������Vscode��)��д����Ŀ��
2. ������Դ�������ֱ����ʾ�ļ�������ˢ�º���ʾ������Թ��ύ���������½�ͬ����־�����ƣ�д����ͬ�������ı�����(��Ϊ���µ�Github��֧���Ʊ�Ϊmain��������Vscode������master��֧Ϊmain)�����Կ���������ʧ��
3. *��һ���ȿ�4.*��һ����Ҫ�ϴ�����Ҫ��������㣬ѡ������(push)���������½ǳ��ֵ����������Զ��(Ҳ����Github��)�������ӣ������м���ֵ������������(Allow)���ͻ���������Github���ٵ�������㣬ѡ�����͵����ӳ��ֵ��ı���������Github���Զ�̣�Ȼ����������Ҫ���ӵ���Github����(û�о͵�Github�½�һ��repo)��
4. ��һ���ϴ����������ܲ����С��������ڵ�Github��main��֧����Vscode��master��֧����Ҫ��Vscode�ն˸��ġ������������ϴ����̴��롣
```Git
git branch -m main ����[git branch -m master main]#�ķ�֧masterΪmain
git branch -v #������û�иĳ�main
git remote add origin git@github.com:���Github��/����.git #���Զ��
git pull origin main ����[git pull origin main -f]#�ѱ��زֿ����ӵ�Զ�̿�
git pull --rebase origin main #GithubԶ����ReadMe�ļ���������û�У�����һ����
git push orgin main #�����ϴ�Github
```
5. �鿴Github������û���ϴ������ݡ�֮��Ϳ��Ե���������е����͵���ֱ�ӵ�����Ϳ��ϴ���
```
git branch -D master #ɾ��master��֧
git branch -a #�鿴���з�֧
git branch -r #�鿴Զ�̷�֧
```
����֣�
git branch -vv #�����п�����main����origin��main
���Ծ���ɾ��Զ�̵�origin main���������㣬ѡ��Զ���е�ɾ��Զ�̴洢�⣬����ı�������Ҫɾ����origin main��
֮����Ҫ�ϴ�����д��
git pull Github�Ŀ��� main
�ڲ鿴Զ�̿⣺git branch -r��ֻ��һ��main�ˡ�