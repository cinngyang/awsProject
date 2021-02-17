Flask 登入管理使用 [flask_login](https://flask-login.readthedocs.io/en/latest/)<br>

+ init login manager

+ 設立 User Model & UserMxin

+ route 加入 @login_required 

+ handle login failed  @app.errorhandler(401)

[Flask-Login_登入狀態管理](https://hackmd.io/@shaoeChen/ryvr_ly8f?type=view)<br>

``` python
from flask import Flask, url_for, request, redirect ,render_template
from flask_login import LoginManager, UserMixin, login_user, current_user, login_required, logout_user

app = Flask(__name__)
app.config['SECRET_KEY'] = 'cairocoders-ednalan'

# init login manager
login_manager = LoginManager()
login_manager.init_app(app)

class User(UserMixin, db.Model):
    #假裝是我們的使用者 
	users = {'usr@bar.tld': {'password': 'secret'}} 

class User(UserMixin):  
  """ 繼承 userMixin 可以做更多判斷
  如is_administrator也可以從這邊來加入 
  """  
  pass 

```



Route 設置

``` python
@login_manager.user_loader 
def user_loader(email): 
  """
  讓flask_login可以隨時取到目前的使用者 id  
  :param email:官網此例將email當id使用，賦值給予user.id  
  """  
  if email not in users:
        return 

  user = User() 
  user.id = email 

  return user 

@app.route('/login', methods=['GET', 'POST']) 
def login(): 
  """ 
  官網 git很給力的寫了一個login的頁面，在GET的時候回傳渲染   
  """  
  if request.method == 'GET':
        return  '''  

  <form action='login' method='POST'>
  <input type='text' name='email' id='email' placeholder='email'/>
  <input type='password' name='password' id='password' placeholder='password'/>
  <input type='submit' name='submit'/>
  </form> '''

  email = request.form['email'] 

  if request.form['password'] == users[email]['password']: 

    #實作User類別 
    user = User() 
    #設置id就是email 
    user.id = email 
    #透過login_user來記錄user_id，如下了解程式碼的login_user說明。 

    login_user(user) 
    # 登入成功，轉址 
    return redirect(url_for('protected'))   

  return 'Bad login' 


@app.route('/protected') 
@login_required 
def protected(): 

  """ 
  在login_user(user)之後，我們就可以透過current_user.id來取得用戶的相關資訊了 
  """  

  #current_user確實的取得了登錄狀態

  if current_user.is_active:
    return 'Logged in as: ' + current_user.id + 'Login is_active:True'

@app.route('/Demo')
@login_required
def demo():
  return render_template('Demo.html')  

@app.route('/logout') 
def logout(): 
  """ 
  logout\_user會將所有的相關session資訊給pop掉 
  """ 
  logout_user() 
  return 'Logged out' 

# handle login failed
@app.errorhandler(401)
def page_not_found(e):
  return redirect(url_for('login'))


# Run Flask
if __name__ == '__main__': 
  app.debug = True 
  app.run()

```

