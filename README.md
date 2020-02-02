# _git_hook_client

sh init.sh

## commit-msg

```
 $ diff .git/hooks/commit-msg.sample git_hooks/commit-msg -us                                                                                                           (git)-[master]
--- .git/hooks/commit-msg.sample
+++ .git_hooks/commit-msg

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
