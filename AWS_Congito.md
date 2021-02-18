[Home](README.md)

##AWS Congito & Flask

aws 官方提供 python 套件 boot3 / warrant 另外有 Flask-Cognito 跟其他相關套件。<br>

一直採坑中 .....

OAuth 2.0 待研究

[aws congito 設定](#1)

[pythn Sample](#2)



<h2 id="1">congito 設定</h2>

<img src="img\Cognito.png" alt="Conito" style="zoom:70%;"/><br>

User Pools 使用者集區

<h2 id="2">Python Sample</h2> 

[這是找到最簡單的 warrent Sample](https://github.com/capless/warrant)<br>

``` python
import boto3
from warrant import Cognito
from warrant.aws_srp import AWSSRP
from dotenv import load_dotenv
import os


print(f"boto3 version {boto3.__version__}")
print(f"boto3 get_available_services{boto3.Session().get_available_services()}")

#載入 應用程式端 poolid & clientid

load_dotenv()
poolid=os.getenv('user-pool-id')
clientid=os.getenv('client-id')

#新增使用者
client = boto3.client('cognito-idp')
u = Cognito(poolid,poolid,client_secret)
u.add_base_attributes(email='user@locate',name='user')
u.register('user@locate')

```

[設定適用於 JavaScript 的 AWS SDK](http://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/setting-up.html)<br>[設定適用於 .NET 和 Xamarin 的 AWS Mobile SDK](http://docs.aws.amazon.com/mobile/sdkforxamarin/developerguide/index.html)<br>

------

[aws-ampifity SKD](https://github.com/aws-amplify/amplify-js/tree/master/packages/amazon-cognito-identity-js)<br>[aws cognito doc](https://docs.aws.amazon.com/zh_tw/cognito/latest/developerguide/what-is-amazon-cognito.html)<br>[Faksk Congito](https://pypi.org/project/Flask-Cognito/))<br>
[Cognito with js and flask tutorial ](https://www.youtube.com/watch?v=qMtk4LJ5OfE&t=9s&ab_channel=BojanBaltic)<br>[lambda function using cognito python](https://medium.com/@houzier.saurav/aws-cognito-with-python-6a2867dd02c6)

