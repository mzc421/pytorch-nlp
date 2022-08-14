# ��Ŀ���ƣ�
ʹ�� Bert + TextCNN �ں�ģ���������Ľ��з��࣬���ı�����
Bert�������Զ�һЩ�������޵ľ��ӽ��и��õķ��࣬TextCNN�����Թؼ��ʸ������С�

# ��Ŀ������
pytorch��python   
��ؿⰲװ
`pip install -r requirement.txt`

# ��ĿĿ¼��
```
bert-TextCNN  
    |-- bert-base-chinese    bert ����Ԥѵ��ģ��     
    |-- data                 ���ݼ�   
    |-- image                ���ģ�����ͼƬ
    |-- logs                 ѵ����־               
    |-- model                �����ģ��               
    |-- config.py            �����ļ�                   
    |-- log.py               ��־�ļ�                 
    |-- main.py              ������                      
    |-- model.py             ģ���ļ�                     
    |-- predict.py           Ԥ���ļ�                         
    |-- requirement.txt      ��Ҫ�İ�װ��
    |-- utils.py             ���ݴ����ļ�
```

# bert-TextCNN ģ�ͽṹͼ
## ģ��1
![bert-TextCNN ģ��ͼ1](image/bertTextCnnģ��ͼ1.png)        
Bert-Base��ȥ��һ������㣬��12��encoder�㣬ÿ��encode��ĵ�һ��token��CLS�����������Ե�������������
���ǿ��Գ�������Ϊ��encode��Խǳ����������Խ�ܴ���ͼ���������Ϣ��Խ�������߼���������Ϣ��
���ǵ�Ŀ���Ǽ���õ��йشʵ�����������õ�����������ģ�;��������ǽ���1�㵽��12���CLS��������ΪTextCNN�����룬�����ı����ࡣ

## ģ��2
![bert-TextCNN ģ��ͼ2](image/bertTextCnnģ��ͼ2.png)
�� bert ģ�͵����һ��������������Ϊ TextCNN ģ�͵����룬����ģ���ڼ�������ѧϰ���õ����յĽ���������ı�����


# ��Ŀ���ݼ�
���ݼ�ʹ��THUCNews�е�train.txt��test.txt��dev.txt��Ϊʮ�������⡣
����ѵ����һ���� 180000 ������֤��һ���� 10000 �������Լ�һ���� 10000 ����
�����Ϊ finance��realty��stocks��education��science��society��politics��sports��game��entertainment ��ʮ�����


# ģ��ѵ��
`python main.py`

# ģ��Ԥ��
`python predict.py`

# ѵ���Լ������ݼ�
train.txt��dev.txt��test.txt �����ݸ�ʽ���ı�\t��ǩ�����ֱ�ʾ��
```
����2D�۷� ����������ʮ���¸���\t8   
60������������״������о(��ͼ)\t5    
```
class.txt����ǩ����ı���

## �޸����ݣ�
�������ļ����޸ĳ��ȡ��������Ԥѵ��ģ�͵�ַ    
```
parser.add_argument("--select_model_last", type=bool, default=True, help="ѡ��ģ��")
parser.add_argument("--bert_pred", type=str, default="./bert-base-chinese", help="bert Ԥѵ��ģ��")
parser.add_argument("--class_num", type=int, default=10)   
parser.add_argument("--max_len", type=int, default=38)
```
