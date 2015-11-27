# slim-goes-slimmer
HTML pages with embedded JS or complicated division hierarchy are written with indentation for readability and good developer experience. This causes websites' source codes to look like this:
```
<html>
  <body>
    <div>
      <div>
        <span>
          <ul>
            <li>un
              <a>
                Some content here
              </a>
            </li>
            <li>
              <a>
                Some other here
              </a>
            </li>
            <li>
              <a>
                Still another content here
              </a>
            </li>
          </ul>
        </span>
      </div>
    </div>
    <script>
      function someAwesomeFunction() {
        // This function does something
        for() {
          if() {
           // Some code here
          } else {
           // Some more code here
          }
        }
      }
    </script>
  </body>
</html>
```
I did a rough benchmarking of this on several popular media websites and found that we waste somewhere from 20 to 30% of the HTML bandwidth to indented HTML and JavaScript. So, I decided to solve this problem, and implement this for Slim framework first, because this the framework I'm currently working with.

So far, slim-goes-slimmer reduces the above piece of HTML to 
```
<html>
<body>
<div>
<div>
<span>
<ul>
<li>
<a>
Some content here
</a>
</li>
<li>
<a>
Some other here
</a>
</li>
<li>
<a>
Still another content here
</a>
</li>
</ul>
</span>
</div>
</div>
<script>
function someAwesomeFunction() {
// This function does something
for() {
if() {
// Some code here
} else {
// Some more code here
}
}
}
</script>
</body>
</html>
```
... thus stripping whitespaces from the beginning of every line

# Why I haven't "optimized" it further?
Mainly because I'm facing weird issues with base64-encoded images in HTML

#Inspiratoin
This project is inspired by a project I have contributed to https://github.com/christianklisch/slim-minify earlier. I intended to contribute to it further, but haven't sone so because slim-goes-slimmer is specifically addresses to my set of problems, and I will tweak this as and how I need it on my PHP projects.

# Contributing
Contributing is dumb simple. Fork, code, push and rase a pull request.
