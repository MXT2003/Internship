---
title : "Kiá»ƒm tra Gateway Endpoint"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 5.3.2 </b> "
---

#### Táº¡o S3 bucket

1. Äi Ä‘áº¿n S3 management console
2. Trong Bucket console, chá»n **Create bucket**

![Create bucket](/images/5-Workshop/5.3-S3-vpc/create-bucket.png)

3. Trong Create bucket console
+ Äáº·t tĂªn bucket: chá»n 1 tĂªn mĂ  khĂ´ng bá»‹ trĂ¹ng trong pháº¡m vi toĂ n cáº§u (gá»£i Ă½: lab\<sá»‘-lab\>\<tĂªn-báº¡n\>)

![Bucket name](/images/5-Workshop/5.3-S3-vpc/bucket-name.png)


+ Giá»¯ nguyĂªn giĂ¡ trá»‹ cá»§a cĂ¡c fields khĂ¡c (default)
+ KĂ©o chuá»™t xuá»‘ng vĂ  chá»n **Create bucket**

![Create](/images/5-Workshop/5.3-S3-vpc/create-button.png)    

+ Táº¡o thĂ nh cĂ´ng S3 bucket

![Success](/images/5-Workshop/5.3-S3-vpc/bucket-success.png)

#### Káº¿t ná»‘i vá»›i EC2 báº±ng session manager

+ Trong workshop nĂ y, báº¡n sáº½ dĂ¹ng AWS Session Manager Ä‘á»ƒ káº¿t ná»‘i Ä‘áº¿n cĂ¡c EC2 instances. Session Manager lĂ  1 tĂ­nh nÄƒng trong dá»‹ch vá»¥ Systems Manager Ä‘Æ°á»£c quáº£n lĂ½ hoĂ n toĂ n bá»Ÿi AWS. System manager cho phĂ©p báº¡n quáº£n lĂ½ Amazon EC2 instances vĂ  cĂ¡c mĂ¡y áº£o on-premises (VMs)thĂ´ng qua 1 browser-based shell. Session Manager cung cáº¥p kháº£ nÄƒng quáº£n lĂ½ phiĂªn báº£n an toĂ n vĂ  cĂ³ thá»ƒ kiá»ƒm tra mĂ  khĂ´ng cáº§n má»Ÿ cá»•ng vĂ o, duy trĂ¬ mĂ¡y chá»§ bastion host hoáº·c quáº£n lĂ½ khĂ³a SSH.

+ First Cloud AI Journey [Lab](https://000058.awsstudygroup.com/1-introduce/) Ä‘á»ƒ hiá»ƒu sĂ¢u hÆ¡n vá» Session manager.

1. Trong AWS Management Console, gĂµ Systems Manager trong Ă´ tĂ¬m kiáº¿m vĂ  nháº¥n Enter:

![system manager](/images/5-Workshop/5.3-S3-vpc/sm.png)

2. Tá»« **Systems Manager** menu, tĂ¬m **Node Management** á»Ÿ thanh bĂªn trĂ¡i vĂ  chá»n **Session Manager**:

![system manager](/images/5-Workshop/5.3-S3-vpc/sm1.png)

3. Click Start Session, vĂ  chá»n EC2 instance tĂªn **Test-Gateway-Endpoint**. 
{{% notice info %}}
PhiĂªn báº£n EC2 nĂ y Ä‘Ă£ cháº¡y trong "VPC cloud" vĂ  sáº½ Ä‘Æ°á»£c dĂ¹ng Ä‘á»ƒ kiá»ƒm tra kháº£ nÄƒng káº¿t ná»‘i vá»›i Amazon S3 thĂ´ng qua Ä‘iá»ƒm cuá»‘i Cá»•ng mĂ  báº¡n vá»«a táº¡o (s3-gwe). {{% /notice %}}

![Start session](/images/5-Workshop/5.3-S3-vpc/start-session.png)

Session Manager sáº½ má»Ÿ browser tab má»›i vá»›i shell prompt: sh-4.2 $

![Success](/images/5-Workshop/5.3-S3-vpc/start-session-success.png)

Báº¡n Ä‘Ă£ báº¯t Ä‘áº§u phiĂªn káº¿t ná»‘i Ä‘áº¿n EC2 trong VPC Cloud thĂ nh cĂ´ng. Trong bÆ°á»›c tiáº¿p theo, chĂºng ta sáº½ táº¡o má»™t  S3 bucket vĂ  má»™t tá»‡p trong Ä‘Ă³.
#### Create a file and upload to s3 bucket

1. Äá»•i vá» ssm-user's thÆ° má»¥c báº±ng lá»‡nh "cd ~" 

![Change user's dir](/images/5-Workshop/5.3-S3-vpc/cli1.png)

2. Táº¡o 1 file Ä‘á»ƒ kiá»ƒm tra báº±ng lá»‡nh "fallocate -l 1G testfile.xyz", 1 file tĂªn "testfile.xyz" cĂ³ kĂ­ch thÆ°á»›c 1GB sáº½ Ä‘Æ°á»£c táº¡o.

![Create file](/images/5-Workshop/5.3-S3-vpc/cli-file.png)

3. Táº£i file mĂ¬nh vá»«a táº¡o lĂªn S3 vá»›i lá»‡nh "aws s3 cp testfile.xyz s3://your-bucket-name". Thay your-bucket-name báº±ng tĂªn S3 báº¡n Ä‘Ă£ táº¡o.

![Uploaded](/images/5-Workshop/5.3-S3-vpc/uploaded.png)

Báº¡n Ä‘Ă£ táº£i thĂ nh cĂ´ng tá»‡p lĂªn bá»™ chá»©a S3 cá»§a mĂ¬nh. BĂ¢y giá» báº¡n cĂ³ thá»ƒ káº¿t thĂºc session.

#### Kiá»ƒm tra object trong S3 bucket

1. Äi Ä‘áº¿n S3 console.  
2. Click tĂªn s3 bucket cá»§a báº¡n
3. Trong Bucket console, báº¡n sáº½ tháº¥y tá»‡p báº¡n Ä‘Ă£ táº£i lĂªn S3 bucket cá»§a mĂ¬nh

![Check S3](/images/5-Workshop/5.3-S3-vpc/check-s3-bucket.png)

#### TĂ³m táº¯t

ChĂºc má»«ng báº¡n Ä‘Ă£ hoĂ n thĂ nh truy cáº­p S3 tá»« VPC. Trong pháº§n nĂ y, báº¡n Ä‘Ă£ táº¡o gateway endpoint cho Amazon S3 vĂ  sá»­ dá»¥ng AWS CLI Ä‘á»ƒ táº£i file lĂªn. QuĂ¡ trĂ¬nh táº£i lĂªn hoáº¡t Ä‘á»™ng vĂ¬ gateway endpoint cho phĂ©p giao tiáº¿p vá»›i S3 mĂ  khĂ´ng cáº§n Internet gateway gáº¯n vĂ o "VPC Cloud". Äiá»u nĂ y thá»ƒ hiá»‡n chá»©c nÄƒng cá»§a gateway endpoint nhÆ° má»™t Ä‘Æ°á»ng dáº«n an toĂ n Ä‘áº¿n S3 mĂ  khĂ´ng cáº§n Ä‘i qua pub    lic Internet.
