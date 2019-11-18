---
title: "Hugo Tips (How to upload new post)"
date: 2019-11-18T19:19:20+09:00
---

## How to upload new post

1. Create a markdown file using below command. You can find new file in `contents/posts/<postname>.md`
```console
[18/11/19 7:26:22] ❯ hugo new posts/test-post.md
/Users/bmy4415/Desktop/workspace/bmy4415_blog/content/posts/test-post.md created

[18/11/19 7:29:03] ❯ tree content
content
└── posts
    ├── hugo-tips.md
    ├── my-first-post.md
    └── test-post.md

1 directory, 3 files
```


1. Update `contents/posts/<postname>.md` file. You can check intermediate result on `localhost:1313` with below command.
```console
[18/11/19 7:26:34] ❯ hugo server -D

                   | EN
+------------------+----+
  Pages            | 12
  Paginator pages  |  0
  Non-page files   |  0
  Static files     | 13
  Processed images |  0
  Aliases          |  4
  Sitemaps         |  1
  Cleaned          |  0

Total in 13 ms
Watching for changes in /Users/bmy4415/Desktop/workspace/bmy4415_blog/{archetypes,content,data,layouts,static,themes}
Watching for config changes in /Users/bmy4415/Desktop/workspace/bmy4415_blog/config.toml
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop

Change detected, rebuilding site.
2019-11-18 19:26:42.961 +0900
Source changed "/Users/bmy4415/Desktop/workspace/bmy4415_blog/content/posts/hugo-tips.md": WRITE
Total in 17 ms
```


1. Remove `draft: true` line in `contents/posts/<postname>.md`. If you don't do this, `deploy.sh` will not deploy your post.
```console
[18/11/19 7:52:48] ❯ head content/posts/hugo-tips.md
---
title: "Hugo Tips (How to upload new post)"
date: 2019-11-18T19:19:20+09:00
draft: true
---

## How to upload new post
```

1. Deploy with `deploy.sh`.
```console
[18/11/19 7:56:08] ❯ ./deploy.sh
Deploying updates to GitHub...

                   | EN
+------------------+----+
  Pages            | 11
  Paginator pages  |  0
  Non-page files   |  0
  Static files     | 13
  Processed images |  0
  Aliases          |  4
  Sitemaps         |  1
  Cleaned          |  0

Total in 17 ms
commit msg: rebuilding site Mon Nov 18 19:56:08 KST 2019
[master 05641e3] rebuilding site Mon Nov 18 19:56:08 KST 2019
 8 files changed, 248 insertions(+), 5 deletions(-)
 create mode 100644 posts/hugo-tips/index.html
오브젝트 나열하는 중: 25, 완료.
오브젝트 개수 세는 중: 100% (25/25), 완료.
Delta compression using up to 4 threads
오브젝트 압축하는 중: 100% (13/13), 완료.
오브젝트 쓰는 중: 100% (14/14), 3.39 KiB | 496.00 KiB/s, 완료.
Total 14 (delta 9), reused 0 (delta 0)
remote: Resolving deltas: 100% (9/9), completed with 4 local objects.
To https://github.com/bmy4415/bmy4415.github.io.git
   34ab8c3..05641e3  master -> master
```

#### Feel free to make questions or advices to me