# ��Ŀ���ƣ�
ʹ�� bert ģ���������Ľ��з��࣬���ı�����

# ��Ŀ������
pytorch��python   
��ؿⰲװ
`pip install -r requirement.txt`

# ��ĿĿ¼��
Bert        
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
    |-- requests.txt         ��Ҫ�İ�װ��                
    |-- test.py              �����ļ�              
    |-- utils.py             ���ݴ����ļ�

# Bert ģ�ͽṹ���ı�����ģ�ͽṹ
![bert ģ�ͽṹ](image/bert%20ģ�ͽṹ.jpg)   
![bert �ı�����ģ��](image/bert%20�ı�����ģ��.jpg)    
`Overall pre-training and fine-tuning procedures for BERT. Apart from output layers, the same architectures are used in both pre-training and fine-tuning. The same pre-trained model parameters are used to initialize
models for different down-stream tasks. During fine-tuning, all parameters are fine-tuned. [CLS] is a special
symbol added in front of every input example, and [SEP] is a special separator token (e.g. separating questions/answers).`   

`BERT������Ԥѵ����΢�����򡣳��������֮�⣬��Ԥѵ����΢����ʹ����ͬ�ļܹ�����ͬ��Ԥѵ��ģ�Ͳ������ڳ�ʼ��
��ͬ���������ģ�͡���΢���ڼ䣬��΢�����в�����[CLS]��һ�������
���������ÿ������ʾ����ǰ�棬[SEP]��һ������ķָ�����ǣ����磬�ָ�����/�𰸣���`

# Bert ģ�͵�Ԥѵ����΢���ṹ
![bert Pre-training and Fine-Tuning](image/bert%20Pre-training%20and%20Fine-Tuning.jpg)  
����ͼ��ʾ��Ԥѵ���Ĺ��̣��ұߵ�ͼ�Ƕ��ھ��������΢�����̡�

# Bert ģ�͵�����
BERT ��������԰���һ�����Ӷ� (���� A �;��� B)��Ҳ�����ǵ������ӡ�ͬʱ BERT ������һЩ���������õı�־λ��   
[CLS] ��־���ڵ�һ�����ӵ���λ������ BERT �õ��ĵı������� C �������ں����ķ�������   
[SEP] ��־���ڷֿ�����������ӣ������������ A �� B��Ҫ�ھ��� A��B �������� [SEP] ��־��   
[MASK] ��־�����ڸǾ����е�һЩ���ʣ��������� [MASK] �ڸ�֮�������� BERT ����� [MASK] ����Ԥ�ⵥ����ʲô��   

# Bert ģ�͵� Embedding ģ��
BERT �õ�Ҫ����ľ��Ӻ�Ҫ�����ӵĵ���ת�� Embedding��Embedding �� E ��ʾ��  
�� transformer ��ͬ��BERT ������ Embedding ������������ӵõ���Token Embedding��Segment Embedding��position Embedding��   
![bert Embedding ģ��](image/bert%20Embeddingģ��.jpg)   
Token Embedding�����ʵ� Embedding������ [CLS] dog �ȣ�ͨ��ѵ��ѧϰ�õ���   
Segment Embedding����������ÿһ���������ھ��� A ���Ǿ��� B�����ֻ����һ�����Ӿ�ֻʹ�� EA��ͨ��ѵ��ѧϰ�õ���   
position Embedding�����뵥�ʳ��ֵ�λ�ã��� transformer ʹ�ù̶��Ĺ�ʽ���㲻ͬ��BERT �� position Embedding Ҳ��ͨ��ѧϰ�õ��ģ��� BERT �У���������Ϊ 512��

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

����2D�۷� ����������ʮ���¸���\t8   
60������������״������о(��ͼ)\t5    

class.txt����ǩ����ı���
## �޸����ݣ�
�������ļ����޸ĳ��ȡ��������Ԥѵ��ģ�͵�ַ    
parser.add_argument("--bert_pred", type=str, default="./bert-base-chinese")   
parser.add_argument("--class_num", type=int, default=10)   
parser.add_argument("--max_len", type=int, default=38)

