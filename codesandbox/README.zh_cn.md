# ������Codesandbox�ķ���1

1. ע��Codesandbox�˺ţ������Github��С�ŵ�¼��
2. ��������һ��Docker������
3. ���նˣ�����"Ctrl + `"��ݼ���
4. ʹ���������ر�repo: `wget -O main.zip "<URL>"`, ���� `<URL>` ����ɫ"<> Code"��ť����� "Download ZIP" �����ӵ�ַ��ע�⣬Codesandbox�ϵ� "git clone" �����á�
5. ���������������ù�����workspace (����ճ������)��

```
unzip main.zip -d .codesandbox
REPO_ROOT=$(ls -d .codesandbox/*/)
mv $REPO_ROOT/* .codesandbox
rm -r $REPO_ROOT main.zip
(cd .codesandbox/codesandbox && chmod +x csb.sh && ./csb.sh)
```

6. ��������������Env Variables����������Ͻǵķ���ͼ�꣬ѡ�� "Project settings"�������ҵ�������������ҳ�档�����ڴ������µ�UUID����¼ƾ�ݣ����½�һ����ΪUUID�Ļ����������ɡ�
7. ������Ͻǵķ���ͼ�꣬Ȼ��ѡ�� "Restart Sandbox" ��
8. �깤��


# ������Codesandbox�ķ���2

1. ��Github��Fork����Ŀ���Լ����˺Ż���С�ţ��Ƽ�����
2. ʹ�ø�Github�˺�ע�Ტ��¼Codesandbox��
3. ��Dashboard����¼֮����Ǹ��ط����ϣ���� "Import Repository" ��Ȼ��ѡ��ղ�Fork����Ŀ��
4. ������Ͻǵķ���ͼ�꣬Ȼ��ѡ�� "Project settings" ����Ŀ���ã�. ������ "Repository" ҳ���У�ȡ��ѡ�� "Protect current branch" ��������֧���ݣ��� 
5. ���������������ù�����workspace (����ճ������)��
```
[ -d .codesandbox ] && rm -rf .codesandbox
mkdir -p .codesandbox && mv -n * .codesandbox/
(cd .codesandbox/codesandbox && chmod +x csb.sh && ./csb.sh)
```
6. ��������������Env Variables����������Ͻǵķ���ͼ�꣬ѡ�� "Project settings"�������ҵ�������������ҳ�档�����ڴ������µ�UUID����¼ƾ�ݣ����½�һ����ΪUUID�Ļ����������ɡ�
7. ������Ͻǵķ���ͼ�꣬Ȼ��ѡ�� "Restart Branch" ��
8. �깤��


# ע��
1. ������һ��ʱ����Զ����ߣ����ݲ���ʧ����Cloudflare ����� URL ����ʱ�ı䣨��ѵ�Cloudflareͨ������֤����ʱ�䣩����õĽ��������ʹ�ö��� ��Subscription������ַ��`https://<URL>/<UUID>.txt`�� ���� <UUID> �� x-ray �� UUID�� <URL> �� Codesandbox ����� URL��������Ϊ "entrypoint:8080" ��ҳ�����ҵ���
2. "entrypoint.sh" �а��� UUID ��Ĭ��ֵ�����Ǵ��ڰ�ȫԭ��ǿ�ҽ���ʹ���Լ����ɵ�UUID�����÷���������Ĳ���6��
3. �ٷ� Warp-Cli �� Codesandbox �����ã��ᱨ "Insufficient File Descriptors"��
