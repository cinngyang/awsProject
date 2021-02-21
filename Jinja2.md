
- 模板語法可使用 python string list dic tuple
- 將網頁拆分幾個 Componse ,用一個 base.html 放入各 Componse 規劃主要 layerout<br>
  網頁界繼承base 後


- context 
自訂義 global variable @app.context_process



``` python
{% set navigation %}

{% endset%}

# register template global function
@app.template_global()
def glver():
    ...
    return ..

# 404 error handler
@app.errorhandler(404)
def page_not_found(e):
    return render_template('errors/404.html'), 404


```

----
[jinja2 官方文件](https://jinja.palletsprojects.com/en/2.11.x/templates/)<br>
