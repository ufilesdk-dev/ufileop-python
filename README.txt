====��װ������
1��python 2.6 �����ϰ汾
2����װpython requests �� 

��װ�ο���https://github.com/ufilesdk-dev/ufile-pythonsdk


====˵����
1��֧��put С�ļ���10M���ڣ��ϴ���
2��֧��mput ���ļ���10M���ϣ��ϴ���
3��֧�������ļ������أ�


====ʹ�÷�����
1������config.cfg�� ��bucket ��Ӧ�Ĺ�˽Կ������token ���ý�ȥ��
config.cfg:
{
        "public_key":"<$���Bucket��Կ>",
        "private_key":"<$���Bucket˽Կ>"
}


2�����÷�����
python ufile_op.py [upload_put|upload_mput|download] [domain] [key] [file]

NOTE:
    if file is "-", it means:
    - stdin for upload
    - stdout for download

���ӣ�python ufile_op.py upload mybucket.cn-bj.ufileos.com s.php s.php


==== �߼��÷���֧�ֱ�׼������Ϊ����Դ������������mysql dump �Ĳ���ر���
���ӣ�

���ݱ����ļ���ufile:
python ufile_op.py upload_put testecho.cn-bj.ufileos.com s3.php  - < s2.php 
python ufile_op.py upload_mput testecho.cn-bj.ufileos.com s3.php - < s2.php


����mysql dump�ļ���ufile:
mysqldump -h 127.0.0.1 my_dbs my_table | python ufile_op.py upload_mput testecho.cn-bj.ufileos.com mysql_bak/20190507.sql - 

����mysql �����ļ������أ�
python ufile_op.py download testecho.cn-bj.ufileos.com mysql_bak/20190507.sql local_fname.sql



