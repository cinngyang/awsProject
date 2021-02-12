AWS EC2 建立 ubuntu 環境安裝 Python 虛擬環境與 Mysql db<br>Python 虛擬環境方式 virtualenv 可以隔離環境與版本<br>Rasberry Pi 3 安裝 mysql db<p>



+ AWS  安裝 ununtu <br>

  安裝 Python  虛擬環境 利用 requirement 管理版本與元件<br> nginx for Web Service<br> MySql Cilent & Server<br>


<pre><code>sudo apt-get upgrade - 更新安裝環境來源
sudo apt-get install net-tools - 網路元元件
sudo apt-get install python3-pip 
sudo apt-get install python3-venv 
sudo apt-get install nginx
sudo apt-get install git 
sudo apt-get install mysql-client
sudo apt-get install mysql-server
pip3 -V
#pip freeze > requirements.txt
#pip install -r requirements.txt
</code>
</pre>


Rasberrypi my Sql & pandas import errr 處理

```html
sudo apt-get install mariadb-server #rasberry pi
sudo apt-get install libmysqlclient-dev
sudo apt-get install libatlas-base-dev
```

ununtu 建置虛擬環境<br>

<pre><code>python3 -m venv myenv
cd myenv
source bin/activate
python3 --version
which python3
pip3 list
pip3 install flask
</code></pre>

+ ubuntu 常用指令
<pre><code>jobs
 fg %1 - 工作帶回前景 (foreground)
 nohup your-command 
 crontab -l 

+ Git 指令<br>[認識Git](https://www.maxlist.xyz/2018/11/02/git_tutorial/)<br>[list of git ignore templates](https://github.com/github/gitignore)

  <pre><code>$git init
  $git add <file>
  $git add . #all Folder and files
  $git commit -m '<command>'
  $git branch -M 
  $git config --list
  $git status
  $git clone <repo URL> -b

  Push local File

  ```
  git remote add origin <URL>
  git branch -M main
  git push -u origin main
  ```
  

  
  ------
  
  
  
  [python viscode 擴充](https://www.maxlist.xyz/2019/07/13/vscode-tip/)
  
  [參考 資料 pyvenv VS virtualenv ](https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/471323/)<br>

+ [Ubuntu 18.04 MySQL 資料庫架設](https://richiechao95.medium.com/ubuntu-18-04-mysql-%E8%B3%87%E6%96%99%E5%BA%AB%E6%9E%B6%E8%A8%AD%E6%95%99%E5%AD%B8-c7139819576f)<br>
+ [Rasberry Pi mariadb-server](https://atceiling.blogspot.com/2020/03/raspberry-pi-61mysqlmariadb.html)<br>
+ [ubuntu 20.4 python venv](https://stackoverflow.com/questions/62125925/how-to-install-python-package-installer-pip-on-ubuntu-20-04-linux)<br>