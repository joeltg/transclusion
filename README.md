# transclusion.html

iframes are cool, but heavy. With WebComponents we can do similar things, but faster, and have more fun while doing them too.

```
<!--index.html-->
<html>
<head>
  <link rel="import" href="transclusion.html">
</head>
<body>
  <p>a:</p>
  <html-import name="foo" href="a.html"></html-import>
  <p>b:</p>
  <html-import name="bar" href="b.html"></html-import>
</body>
</html>
```

```
<!--a.html-->
<html>
<head>
  <link rel="import" href="transclusion.html">
</head>
<body>
  <html-export name="foo">
    <p>Hi this is a.html.</p>
    <html-import name="bar" href="b.html"></html-import>
  </html-export>
</body>
</html>
```

```
<!--b.html-->
<html>
<head>
  <link rel="import" href="transclusion.html">
</head>
<body>
  <html-export name="bar">
    <p>Hi this is b.html</p>
  </html-export>
</body>
</html>
```

![cool, right?](https://github.com/joeltg/transclusion/raw/master/demo.png)

Export and import multiple elements with a `name=` attribute. Add CSS to taste.
Don't recurse; it does exactly what you expect.
