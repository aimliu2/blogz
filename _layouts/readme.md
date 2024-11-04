# Jekyll layout
- markdown layout styling
- use as a <head> loader

**default.html**

```html
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title>{{ page.title }}</title>
  </head>
  <header>
    <!-- zepto -->
    <script src="{{ site.baseurl }}/libraries/js/core/zepto.min.js" crossorigin="anonymous" referrerpolicy="no-referrer"></script> 
    <!-- Bootstrap -->
    <link rel="stylesheet" href="{{ site.baseurl }}/libraries/css/core/bootstrap.min.css">
    <script src="{{ site.baseurl }}/libraries/js/core/bootstrap.bundle.min.js"></script>
    </header>
  <body>
    <div class="container">
    {{ content }}
    </div>
  </body>
</html>
```

## Jekyll load using
- `use {{ site.baseurl }}/ and {{ site.url }}/` on **layout** or **.md** page