
- 模板語法可使用 python string list dic tuple
- 將網頁拆分幾個 Componse ,用一個 base.html 放入各 Componse 規劃主要 layerout<br>
  網頁界繼承 base 使用相同的 block 代表複寫. 可以用 super() 新增


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
[jinja2 官方文件](https://jinja.palletsprojects.com/en/2.11.x/templates/)<br>[Flask 幾個重要的用法](https://realpython.com/primer-on-jinja-templating/#quick-examples)<br>
