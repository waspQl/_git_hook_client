# _git_hook_client

## commit-msg

```
 $ diff .git/hooks/commit-msg.sample .git/hooks/commit-msg -us                                                                                                           (git)-[master]
--- .git/hooks/commit-msg.sample        2020-02-02 18:45:16.000000000 +0900
+++ .git/hooks/commit-msg       2020-02-02 18:54:26.000000000 +0900
@@ -12,8 +12,8 @@
 # Doing this in a hook is a bad idea in general, but the prepare-commit-msg
 # hook is more suited to it.
 #
-# SOB=$(git var GIT_AUTHOR_IDENT | sed -n 's/^\(.*>\).*$/Signed-off-by: \1/p')
-# grep -qs "^$SOB" "$1" || echo "$SOB" >> "$1"
+SOB=$(git var GIT_AUTHOR_IDENT | sed -n 's/^\(.*>\).*$/Signed-off-by: \1/p')
+grep -qs "^$SOB" "$1" || echo "$SOB" >> "$1"
```

```
 $ git commit -m "commit-msg test"                                                                                                                                       (git)-[master]
[master 20e8338] commit-msg test
 1 file changed, 1 insertion(+)
 create mode 100644 commit-msg-test.txt
```

↓

```
 $ git commit -m "commit-msg test"                                                                                                                                       (git)-[master]
[master 20e8338] commit-msg test Signed-off-by: sakutaro <u390862@gmail.com>
 1 file changed, 1 insertion(+)
 create mode 100644 commit-msg-test.txt
```
