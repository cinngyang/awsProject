[ubuntu 環境安裝設定](ubuntu.md)<br>[MySql環境安裝設定](mysql.md)<br>[flask 建置與設定](flask.md)<br>[flask login 介紹](flask_login.md)<br>[aws congito](AWS_Congito)<br>[Python Sample code](https://github.com/cinngyang/ETLTemplate)<br>[Flask Web 結構](WebComponent.md)<br>




<h2 id='aws'>AWS 設定</h2>

- 安裝 aws cli2
- 匯入IAM 金鑰

```shell
aws --versionaws
-cli/2.1.26 Python/3.7.9 Windows/10 exe/AMD64 prompt/off
aws configure --profile produser    
aws configure
aws configure import --csv file://credentials.csv -- 匯入 aws 設定檔名稱與 IAM 使用者名稱相符
aws configure list</code>
```

[awscli2 文件](https://docs.aws.amazon.com/zh_tw/cli/latest/userguide/cli-configure-quickstart.html)<p>

###Cognito 設定

User Pools & Cognito Sync<br>User Pools 設定 集區設定

[使用者管理](https://akuma1.pixnet.net/blog/post/321458140-%ef%bc%88%e5%8d%81%ef%bc%89cognito%ef%bc%88%e4%bd%bf%e7%94%a8%e8%80%85%e7%ae%a1%e7%90%86%ef%bc%89%ef%bc%8d%ef%bc%8daws%e7%b6%93%e9%a9%97%e6%95%99%e5%ad%b8)<br>[範例](https://github.com/capless/warrant)<br>[範例 2](https://www.reddit.com/r/flask/comments/9srjjn/aws_cognito_jwt/)<br>[Cognito 設定 9:242](https://www.youtube.com/watch?v=jTu--LpjA18&ab_channel=edureka%21) <br>[Flask login](https://www.youtube.com/watch?v=qMtk4LJ5OfE&ab_channel=BojanBaltic)<br>[Flask login Page Git code](https://github.com/Balta-zar/cognito-js-flask-tutorial)<br>

