CentOS 下安装

```
yum install screen
```

Ubuntu/Debian 下安装

```
apt-get install screen
```

screen 是一个可以在多个进程（通常是交互式 shell）之间复用一个物理终端的全屏幕窗口管理器。即 linux 下使用多窗口

| **常用 screen 参数**              | **效果**                                            |
| --------------------------------- | --------------------------------------------------- |
| `screen -S session_name`          | # 新建一个叫 session_name 的 session                |
| `screen -ls`（或者 screen -list） | # 列出当前所有的 session                            |
| `screen -r session_name`          | # 回到 session_name 这个 session                    |
| `screen -d session_name`          | # 远程 detach 某个 session                          |
| `screen -d -r session_name`       | # 结束当前 session 并回到 session_name 这个 session |

进入 screen 窗口后，想暂时退出（等会还想连接这个 screen 窗口）
`crtl+a+d`
退出当前 screen 窗口，结束当前 screen 窗口，不想再连接回来（即杀死会话）
`exit` 或者 `ctrl+d`

