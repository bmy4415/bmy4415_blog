### When write blog outside mac local
add below block to `theme/kiss/layouts/_default/single.html`
```
+<script src="https://utteranc.es/client.js"
+        repo="bmy4415/bmy4415_blog_comments"
+        issue-term="pathname"
+        theme="github-light"
+        crossorigin="anonymous"
+        async>
+</script>
```