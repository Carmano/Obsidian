

You must create your template files in the correct location; in the `templates` subdirectory next to the python module (== the module where you create your Flask app).

The error indicates that there is no `home.html` file in the `templates/` directory. Make sure you created that directory in the same directory as your python module, and that you did in fact put a `home.html` file in that subdirectory. If your app is a package, the templates folder should be created _inside_ the package.

```python
myproject/
    app.py
    templates/
        home.html
```

```python
myproject/
    mypackage/
        __init__.py
        templates/
            home.html
```

Alternatively, if you named your templates folder something other than `templates` and don't want to rename it to the default, you can tell Flask to use that other directory.

```python
app = Flask(__name__, template_folder='template')
```

You can ask Flask to explain how it tried to find a given template, by setting the [`EXPLAIN_TEMPLATE_LOADING` option](https://flask.palletsprojects.com/config/#EXPLAIN_TEMPLATE_LOADING) to `True`. For every template loaded, you'll get a report logged to the [Flask `app.logger`](https://flask.palletsprojects.com/quickstart/#logging), at level `INFO`.

This is what it looks like when a search is successful; in this example the `foo/bar.html` template extends the `base.html` template, so there are two searches:

```
[2019-06-15 16:03:39,197] INFO in debughelpers: Locating template "foo/bar.html":
    1: trying loader of application "flaskpackagename"
       class: jinja2.loaders.FileSystemLoader
       encoding: 'utf-8'
       followlinks: False
       searchpath:
         - /.../project/flaskpackagename/templates
       -> found ('/.../project/flaskpackagename/templates/foo/bar.html')
[2019-06-15 16:03:39,203] INFO in debughelpers: Locating template "base.html":
    1: trying loader of application "flaskpackagename"
       class: jinja2.loaders.FileSystemLoader
       encoding: 'utf-8'
       followlinks: False
       searchpath:
         - /.../project/flaskpackagename/templates
       -> found ('/.../project/flaskpackagename/templates/base.html')
```

Blueprints can [register their own template directories](https://flask.palletsprojects.com/blueprints/#templates) too, but this is not a requirement if you are using blueprints to make it easier to split a larger project across logical units. The main Flask app template directory is always searched first even when using additional paths per blueprint.