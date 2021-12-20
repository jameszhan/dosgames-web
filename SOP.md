

#### 删除子模块

```bash
$ git rm --cached static/games
$ git submodule deinit --all
$ git rm -fr static/games
$ rm .gitmodules
```

