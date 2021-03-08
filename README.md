
# WinXray 
WinXray[:loud_sound:](http://dict.youdao.com/dictvoice?audio=winxray&type=2) 是最简洁轻快的 V2Ray、XRay、Trojan、Trojan-go、Shadowsocks、SSR(ShadowsocksR)、SSRoT、NaïveProxy，SOCKS，HTTP,HTTPS 全能通用客户端（Windows系统），支持并发检测大量服务器并迅速找到当前最快的服务器，服务器连接异常时可自动寻找其他速度最快的服务器 - 切换速度快如闪电，自订阅源获取的服务器异常时可自动刷新订阅，并且自带一键自动部署服务端工具。

**本软件源码已放弃版权贡献到公共域** ，源码可使用 [aardio](http://www.aardio.com) 编译生成单文件绿色EXE，**[点这里下载](./../../raw/master/release/winXray.7z)** （ [64位版本](./../../raw/master/release/winXray.7z) / [32位版本](./../../raw/master/release/winXray32.7z) ），解压即可直接使用( 体积很小仅  **[6.1 MB](./../../raw/master/release/winXray.7z)** - 已自带 V2Ray Core ）。  

# WinXray 未注册任何域名，谨防钓鱼网站    
WinXray 分为原版、抄袭版。  
抄袭版没有贡献任何功能，仅添加了假冒官网推广链接，然后原版更新任何功能，抄袭版都会复制粘贴改成他自己的名字重新提交，并且乱改版本号，日常踩原作者吹捧自己。原版作者估计是受不了那货已经失踪很久了。

本项目基于原版 WinXray v3.7 基础上继续更新 ，并将保持原版干净、纯净。本项目严禁上述假冒官网的抄袭版抄袭本项目的任何一句代码 。

# 免费服务器   
[网络免费 vmess 服务器订阅链接](https://proxypool.ga/vmess/sub)   
[网络免费 Shadowsocks 服务器订阅链接](https://proxypool.ga/ss/sub)     
[网络免费 clash 服务器订阅链接](https://proxypoolss.tk/clash/proxies?speed=100&type=vmess,trojan)   
可复制上面各种格式订阅链接，在 winXray 中点击「批量导入链接」体验 winXray 有强大的兼容性。  
免费的服务器仅供测试（一定要走 PAC，不要开全局代理不要登录账号更不要长时间使用 ）。

# 关于误报  
现在大多杀毒软件都是白名单查杀，所以新生的EXE都会乱报病毒，因为我更新的速度太快，所以不断的推新EXE上来，所以你可能遇到误报，但是你完全可以使用源代码自己编译出一模一样的EXE，还有人吹牛说其他翻墙软件不误报 - 你去 issues 里以及网上搜一下有多少误报好不好？！遇到误报可以提交给你的杀毒厂商核实，也可以自己编译源码生成EXE后使用，解决和核实问题很容易 - 其他套路都是多余的。


# PAC 代理模式 / 全局代理 + 路由模式 对比

winXray 的 PAC 代理稳定、流畅、易用。  在 PAC 模式下，winXray 会优先启用高效安全的 SOCKS5 协议，并且可以自动兼容在 PAC 模式下仅支持 HTTP代理的应用。winXray 也可以在 PAC 模式下完美支持 Telegram IP 地址库 。

SOCKS5 支持对比：
- [ ] 全局路由模式: 不支持 SOCKS5
- [x] PAC模式: 支持 高效安全的SOCKS5   
  
UWP 应用支持对比：
- [ ] 全局路由模式: UWP 应用全部无法联网。
- [x] PAC模式: UWP 应用可以正常联网，使用 winXray 自带工具也可以为UWP应用开启本地代理。 

DNS 解析对比：
- [ ] 全局路由模式: 使用本机发起 DNS 解析，即使设为国外 DNS 服务器，仍然会返回适用于国内线路地址。
- [x] PAC模式: 使用服务器上的 DNS 解析，安全可靠。

根据客户端自动切换代理协议：
- [ ] 全局路由模式: 不支持
- [x] PAC模式: winXray 里的 PAC 代理可以让目标应用（例如浏览器）优先选择高效安全的 SOCKS5 代理协议，对于不支持 SOCKS 代理的应用（例如谷歌地球），winXray 在 PAC 模式下会自动为这些应用提供 HTTP 代理。

IP 段代理规则：
- [x] 全局路由模式: 比较好的支持 IP 段代理规则
- [x] PAC模式: winXray 里 PAC 可以支持IP 段代理规则（ 完美支持 Telegram ）。

独立性
- [ ] 全局路由模式: 不独立，代理规则集成在翻墙软件内核中
- [x] PAC模式: 完全独立，PAC 代理服务完全独立于翻墙软件，只有 PAC 指定的域名或IP才会与翻墙软件发生交互。

兼容性
- [ ] 全局路由模式: 不是由系统实现的规则，一旦设置全局代理，不管适不适合走代理的软件都被强制使用代理，所以兼容性不太好，会导致上述的 UWP 无法联网等问题。
- [x] PAC模式: 由系统提供的PAC有良好的兼容性，因为历史悠久，一般的软件都会对PAC有良好的兼容，PAC 主要为适合走代理的浏览器等软件而设计，所以其他软件可以较好的识别并判断是不是要使用 PAC 指定的代理还是直连。

简易度
- [ ] 全局路由模式: 配置复杂，有一定门槛。
- [x] PAC模式: 配置非常简单。


一般不建议普通用户去编辑路由规则 - 错误的配置可能会导致敏感的流量误走代理服务器。
专业的事请交给专业的人去做，使用 winXray 可以一键启用、更新 [v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) 提供的最新路由规则。

注意在 winXray 里无论使用 NaïveProxy 还是 SSR，SSRoT 都支持 V2Ray 路由规则。

# 设置系统代理失败怎么办
如果设置代理以后不能正常生效：请首先右键点击 winXray 任务栏的托盘图标，在弹出的右键菜单中点击【查看 Internet 代理设置】，并检查代理设置是否正常。如果 winXray 不能修改代理设置，但是可以手动修改成功，这一般是被安全软件错误地拦截了( 而且安全软件没有正常弹出确认对话框，或者误点了阻止设置 ）。这时候请到安全软件的相关设置中将 winXray 添加到信任列表即可。

如果不是上面的原因，请按下【Win + R】组合键打开系统运行对话框，输入 regedit 点击确定打开注册表路径 
<span style="color:green">HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings\Connections</span>
然后将“Connections”项删除，注销一下系统即可正常使用代理了。

如果上面的方法仍然不行，请在注册表中打开打开路径
<span style="color:green">Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\WinHttpAutoProxySvc</span>
将 start 的值改为 2， 也就是将 WinHttpAutoProxySvc 服务改为自动启动，然后重启计算机即可。

# Core 默认路径：

可在「 winXray/ 配置 / Core配置 」 下载更新 V2Ray Core / Xray Core / SSR Core ，  
下载更新 V2Ray Core（或 Xray Core）完成后会自动切换 V2Ray 内核。

默认会在以下目录查找 V2Ray Core（或 Xray Core）：

    ./v2ray-core/
    %localappdata%\winXray\core

默认会在以下目录查找 SSR Core：

    ./v2ray-core/ssr-core
    %localappdata%\winXray\ssr-core

默认会在以下目录查找 NaïveProxy Core：

    ./v2ray-core/naive-core
    %localappdata%\winXray\naive-core

找不到会自动下载，没有代理访问 Github 会很慢很慢，有时可能根本打不开，建议经常运行一下 winXray 工具里自带的 【Github 网速优化工具】

注意不同的代理协议连接时会调用不同的 Core，   
例如 NaïveProxy 连接时会启动 naive.exe，这时候系统防火墙会有提示，  
如果这时候没看清就点了拒绝，那么就无法正常使用相应的 Core 了，  
所以请看清楚再点，点错了到系统防火墙里再打开一下就可以了。  

# 安装 NaïveProxy 服务端 

参考：https://github.com/klzgrad/naiveproxy  以 CentOS 为例：

```sh
yum intall golang
yum install git
go get -u github.com/caddyserver/xcaddy/cmd/xcaddy
~/go/bin/xcaddy build --with github.com/caddyserver/forwardproxy@caddy2=github.com/klzgrad/forwardproxy@naive
sudo setcap cap_net_bind_service=+ep ./caddy
wget -O naive.tar.xz  https://github.com/klzgrad/naiveproxy/releases/download/v88.0.4324.96-1/naiveproxy-v88.0.4324.96-1-linux-x64.tar.xz 
tar -xf ./naive.tar.xz

mv naiveproxy-v88.0.4324.96-1-linux-x64 naive
echo -e "{\n  \"listen\": \"socks://127.0.0.1:1080\",\n  \"proxy\": \"https://user:pass@example.com\"\n}" > ./naive/config.json

cat << EOF > ./Caddyfile
:443, example.com
tls me@example.com
route {
  forward_proxy {
    basic_auth user pass
    hide_ip
    hide_via
    probe_resistance
  }
  file_server { root /var/www/html }
}
EOF

iptables -A INPUT -p tcp --dport 80 -j ACCEPT;iptables -A INPUT -p tcp --dport 443 -j ACCEPT;firewall-cmd --permanent --add-port=80/tcp;firewall-cmd --permanent --add-port=443/tcp;firewall-cmd --reload;

./naive/naive --config ./naive/config.json &
./caddy run # 后台运行改成 ./caddy start
```

安装以前需要提前准备一个域名，并将上面脚本中的 example.com 替换为你的域名，user:pass 改为代理登录用户名与密码。