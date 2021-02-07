+ [python viscode 小常識](https://www.maxlist.xyz/2019/07/13/vscode-tip/)

+ AWS  安裝 ununtu Command<br>

  安裝 Python & Python 虛擬環境 nginx for Web Service , MySql Cilent<br>

  利用 requirement 管理版本與元件

<pre><code>sudo apt-get upgrade
sudo apt-get install python3-pip
sudo apt-get install python3-venv
sudo apt-get install nginx
sudo apt-get install git
sudo apt-get install mysql-client
pip3 -V
#pip freeze > requirements.txt
#pip install -r requirements.txt

+ Python 建立虛擬環境 virtualenv(可以隔離)<br>

  [參考 資料 pyvenv VS virtualenv ](https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/471323/)

<pre><code>python3 -m venv myenv
cd myenv
source bin/activate
python3 --version
which python3
pip3 list
pip3 install flask

+ Git 指令<br>[認識Git](https://www.maxlist.xyz/2018/11/02/git_tutorial/)<br>[list of git ignore templates](https://github.com/github/gitignore)

+ 

  <pre><code>$git init
  $git add <file>
  $git add . #all Folder and files
  $git commit -m '<command>'
  $git brench -M 
  $git config --list
  $git status
  $git clone <repo URL> -b

  Push local File

  ```
  git remote add origin <URL>
  git branch -M main
  git push -u origin main
  ```

  

