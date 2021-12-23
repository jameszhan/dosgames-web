

#### 删除子模块

```bash
$ git rm --cached static/games
$ git submodule deinit --all
$ git rm -fr static/games
$ rm .gitmodules
```

## 参考资料

[dosbox]:   https://www.dosbox.com  "Emulator for x86 with DOS"
[dosbox-x]: https://dosbox-x.com    "An open-source DOS emulator for running DOS applications and games"
[js-dos]:   https://js-dos.com      "The simpliest API to run DOS games in browser"