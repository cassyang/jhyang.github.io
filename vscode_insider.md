1. �����ڹ�������[vscode insider��](https://code.visualstudio.com/insiders/)
2. ����չ�а�װRemote-SSH
3. ����[�ٷ�����](https://code.visualstudio.com/docs/remote/troubleshooting#_installing-a-supported-ssh-client)���ñ���SSH�������ڹ�˾�ĵ�����û�����óɹ����гɹ���ͬѧ���Ը����ҡ����ղ�����������Լ�����һ��SSHȻ������[���ص�ַ](https://me.jinchuang.org/sofw/OpenSSHWindows53p1-2.rar)��Ȼ���ڻ������������``��װ·��/bin``
4. ��vscode insider�棬��ס``ctrl+shift+P``Ȼ������SSH�����Remote-SSH:Open Configuration File�����������ļ������������룺
	```
	# Read more about SSH config files: https://linux.die.net/man/5/ssh_config
	Host -i C:\\Users\\gzyangjianhui\\.ssh\\id_rsa gzyangjianhui@192.168.42.196 -p32200 -o IdentitiesOnly=yes -o StrictHostKeyChecking=no
	```
	��Ӧ�ļǵø�һ�£�id_rsa���Լ��ĵ�ַ
5. ��ס``ctrl+shift+P``Ȼ������SSH�����Remote-SSH:Connect To Host��ѡ���Լ��ղŵ����ã��������ӡ�
6. ����������ӹ����п��ܴ������������������������yes��������ǵ����-o StrictHostKeyChecking=no���ɡ�
7. �����TEMRMINAL����ʾ``Connected to SSH Host - Please do not close this terminal`` ��ô�󹦸�ɣ�ѡ���һ���ļ��п�ʼ���ֵ�vscode remote�����ɣ�