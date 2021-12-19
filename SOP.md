

#### 删除子模块

```bash
$ git rm --cached static/games
$ git submodule deinit --all
$ git rm -f static/games
$ rm .gitmodules
```