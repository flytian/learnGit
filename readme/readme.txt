��ʼ��һ��Git�ֿ⣬ʹ��git init���

����ļ���Git�ֿ⣬��������

��һ����ʹ������git add <file>��ע�⣬�ɷ������ʹ�ã���Ӷ���ļ���
�ڶ�����ʹ������git commit����ɡ�

git status���������ļ����޸Ĺ�[��ʾadd,commit]����git diff���Բ鿴�޸�����

�鿴�ύ��־   $ git log --pretty=oneline [��¼ÿ�ε�  commit id �� ����  ����]

���˵���һ���汾 $ git reset --hard HEAD^,����һ���汾����HEAD^^,����100���汾HEAD~100

���˺󣬷���δ���İ汾id��$ git reset --hard 3628164

�鿴ÿ�� commit �� reset �� id�� git reflog

�汾���˺�ǰ��������ͨ�� $ git reset --hard commitid ���

ÿ���޸ģ������add���ݴ������ǾͲ�����뵽commit��

�������������޸�
����git checkout -- readme.txt��˼���ǣ���readme.txt�ļ��ڹ��������޸�ȫ�����������������������

һ����readme.txt���޸ĺ�û�б��ŵ��ݴ��������ڣ������޸ľͻص��Ͱ汾��һģһ����״̬��

һ����readme.txt�Ѿ���ӵ��ݴ������������޸ģ����ڣ������޸ľͻص���ӵ��ݴ������״̬��

��֮������������ļ��ص����һ��git commit��git addʱ��״̬��

�����ݴ������޸�
������git reset HEAD readme.txt���԰��ݴ������޸ĳ�������unstage�������·Żع�����
git reset����ȿ��Ի��˰汾��Ҳ���԰��ݴ������޸Ļ��˵�����������������HEADʱ����ʾ���µİ汾��
�ݴ���������°汾����Ϊ�ա�

�����汾����޸ģ����ύ����û��pushʱ��
�汾����$ git reset --hard commitid

ɾ���ļ�$ git rm test.txtɾ����
Ҫô�ύ $ git commit -m "remove test.txt"
Ҫô����ɾ��  $ git checkout -- test.txt

ADD key to github
�ٶ��������ɵ��ԣ���һ����ڹ�˾�ύ��һ����ڼ����ύ��ֻҪ��ÿ̨���Ե�Key����ӵ�GitHub
����SSH Key��$ ssh-keygen -t rsa -C "flytonus@sina.com"
���û���Ŀ¼���ҵ�.sshĿ¼��������id_rsa��id_rsa.pub�����ļ�������������SSH Key����Կ�ԣ�id_rsa��˽Կ������й¶��ȥ��id_rsa.pub�ǹ�Կ�����Է��ĵظ����κ���
��½GitHub���򿪡�Account settings������SSH Keys��ҳ�棺
Ȼ�󣬵㡰Add SSH Key������������Title����Key�ı�����ճ��id_rsa.pub�ļ�������