<h1 align="center">
  <br>
  <a href="https://webtorrent.io">
    <img src="https://webtorrent.io/img/WebTorrent.png" alt="WebTorrent" width="200">
  </a>
  <br>
  WebTorrent Desktop Personal
  <br>
  <br>
</h1>

<h4 align="center"><a href="https://github.com/webtorrent/webtorrent-desktop">see origin here</a></h4>

## 尝试修改默认trackerslist(AnnounceList)
具体实现见根目录下webtorrent.js

## 具体说明
asar格式压缩&解压

'''
cd webtorrent\resources
asar extract app.asar app
asar pack app app.asar
'''

修改文件 \app\build\renderer\webtorrent.js

搜索 my_add 查看具体修改位置

HTTPS GET trackerslist https://trackerslist.com/all.txt or https://cdn.jsdelivr.net/gh/XIU2/TrackersListCollection@master/all.txt

更改了以下两处变量，不知道哪个生效了

'''
global.WEBTORRENT_ANNOUNCE
// and
client.add(torrentID, {
      announce: mytrackerslist,  // my_add
})
'''
