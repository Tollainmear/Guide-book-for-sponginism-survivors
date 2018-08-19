## 引言
&emsp;&emsp;结合我们之前提到的相关特性，我们可以将 Sponge 的搭建步骤分解为以下几步：
### 重中之重
没有规矩，不成方圆，请所有开服者遵守 MojangAB 为 Minecraft 服务器运营者指定的 EULA（最终用户许可协议）：
[EULA](https://account.mojang.com/documents/minecraft_eula)

另外，本教程仅针对于正确安装了 Java 的 Windows 用户。

#

### 1.下载 MinecraftServer 服务端
&emsp;&emsp;首先，从 MC 官网下载服务端内核：

【推荐】[1.12.2](http://s3.amazonaws.com/Minecraft.Download/versions/1.12.2/minecraft_server.1.12.2.jar)（推荐原因：插件 mod 稳定完备，以下例子将以本核心为准）

【不推荐】[1.13](https://launcher.mojang.com/mc/game/1.13/server/d0caafb8438ebd206f99930cfaecfa6c9a13dca0/server.jar)（不推荐原因：最新版的 mod 和插件不够完备）

#

### 2.下载 forge（以 1.12.2 的 2705 版本为例）
Forge 官网：[https://files.minecraftforge.net/](https://files.minecraftforge.net/)

&emsp;&emsp;我们推荐您使用 forge 官方推荐的版本（Recommended，即有 ★ 标记的），如果 Forge 默认首页的 Forge 版本和您的服务端核心版本不对应，请点击左侧 `Minecraft version` 标签栏内对应的MC版本。
![选择 forge ](https://github.com/Tollainmear/Guide-book-for-sponginism-survivors/blob/master/%E5%9B%BE%E4%BE%8B/%E6%90%AD%E5%BB%BASponge%E6%9C%8D%E5%8A%A1%E7%AB%AF/%E4%B8%8B%E8%BD%BDforge.png?raw=true)
&emsp;&emsp;**确定版本对应后**，点击 `Windows Installer` 图标将会进入跳转页面。等待 6 秒后，点击右上角的 Skip 按钮即可开始下载。（无法跳转的用户请关闭阻止广告的插件）

![forge跳转](https://raw.githubusercontent.com/Tollainmear/Guide-book-for-sponginism-survivors/master/%E5%9B%BE%E4%BE%8B/%E6%90%AD%E5%BB%BASponge%E6%9C%8D%E5%8A%A1%E7%AB%AF/forge%E4%B8%8B%E8%BD%BD-%E8%B7%B3%E8%BD%AC%E7%95%8C%E9%9D%A2.png)

###### 注：因为国内部分地区无法进行网页跳转，因此，我们为这部分无法在官方下载的用户准备了[网盘备份](https://pan.baidu.com/s/1bMcI0wJ16lbAI-Xfbvb4Wg)，★请注意★为了保证Forge开发者的合理收益，除非您无法访问官方下载通道，否则请不要使用备用网盘，因为我们不保证备用网盘是最新的推荐版本。

#

### 3.安装 forge
&emsp;&emsp;到这一步的时候，我们假设已经得到了两个必要文件：
1. Minecraft_Server 核心
2. 对应版本的 Forge 安装包

&emsp;&emsp;为了方便演示，我们创建一个名为 `KaroglanServer` 文件夹(这里明明随意)，然后将服务端核心放置进去，按以下步骤操作：
1. 双击打开 forge 安装程序
2. 如图所示，选择第二个 `Install server` ，并将路径选择到指定的路径。
3. 点击`确定` —— 开始安装

![forge安装](https://raw.githubusercontent.com/Tollainmear/Guide-book-for-sponginism-survivors/master/%E5%9B%BE%E4%BE%8B/%E6%90%AD%E5%BB%BASponge%E6%9C%8D%E5%8A%A1%E7%AB%AF/forge%E5%AE%89%E8%A3%85.png)

&emsp;&emsp;安装过程如图：

![安装过程](https://raw.githubusercontent.com/Tollainmear/Guide-book-for-sponginism-survivors/master/%E5%9B%BE%E4%BE%8B/%E6%90%AD%E5%BB%BASponge%E6%9C%8D%E5%8A%A1%E7%AB%AF/forge%E5%AE%89%E8%A3%85-%E7%95%8C%E9%9D%A2.png)

&emsp;&emsp;安装完毕后，将会提示：

![安装成功](https://raw.githubusercontent.com/Tollainmear/Guide-book-for-sponginism-survivors/master/%E5%9B%BE%E4%BE%8B/%E6%90%AD%E5%BB%BASponge%E6%9C%8D%E5%8A%A1%E7%AB%AF/forge%E5%AE%89%E8%A3%85-%E6%88%90%E5%8A%9F.png)

###### 注：因为部分网络无法访问 Forge 依赖类库的下载网址，所以请根据情况自行切换线路

#

### 4.启动服务器
&emsp;&emsp;因为未启动过的 forge 端没有生成必要文件结构，因此，我们需要先启动一次服务端，我们需要创建一个 txt 文件，将其内容改为：

```
java -Xms1024M -Xmx2048M -jar forge-1.12.2-14.23.4.2705-universal.jar nogui
pause
```

```
解释：
- Xms ： 表示最小内存分配，即初始内存（请根据实际情况调整）
- Xmx ： 表示最大内存分配，即最大内存（请根据实际情况调整）
- 1.12.2-14.23.4.2705-universal.jar ： 启动的核心文件，实际上是 Forge 生成的 jar 文件，可以在修改 jar 文件名后在这里改为修改后的名字
- nogui ： 无图形界面界面
- pause ： 启动参数，当批处理命令执行完毕后暂停（用于调试）
```

&emsp;&emsp;修改完成后，保存关闭，并将此Txt文本后缀名改为.bat

###### 注：如果无法修改拓展名，请根据[此教程](https://jingyan.baidu.com/article/b7001fe14f5cbe0e7282ddf5.html)，将拓展名显示出来

&emsp;&emsp;此时，您的目录结构应该是这样：

![文件目录](https://raw.githubusercontent.com/Tollainmear/Guide-book-for-sponginism-survivors/master/%E5%9B%BE%E4%BE%8B/%E6%90%AD%E5%BB%BASponge%E6%9C%8D%E5%8A%A1%E7%AB%AF/%E5%90%AF%E5%8A%A8%E5%89%8D.png)

&emsp;&emsp;最后，双击启动你刚刚写完的 bat 文件，正常启动后，bat 脚本将会自动暂停，如果图所示：

![启动成功1](https://raw.githubusercontent.com/Tollainmear/Guide-book-for-sponginism-survivors/master/%E5%9B%BE%E4%BE%8B/%E6%90%AD%E5%BB%BASponge%E6%9C%8D%E5%8A%A1%E7%AB%AF/%E5%90%AF%E5%8A%A8%E5%90%8E.png)

&emsp;&emsp;这里涉及到一个提示
```
You need to agree to the EULA in order to run the server. Go to eula.txt for more info.
```

```
翻译：
如果要运行服务器，你需要同意 EULA 协议，您可以查看 eula.txt 来了解更多信息。
```

&emsp;&emsp;如果显示正确，说明本步骤完成。

###### 注：如果无法跳转到这一步，请：
- 检测Forge依赖类库的完整性
- 检测Java正确安装和配置

#

### 5.第二次启动服务器
&emsp;&emsp;MojangAB 要求所有服务器所有者必须遵守 EULA 协议方可运行服务器，详细的 EULA 请参考[这里](https://account.mojang.com/documents/minecraft_eula)。

&emsp;&emsp;操作方法：打开根目录文件夹下的 `EULA.txt` 文件，并将 `eula=false` 改为 `eula=true`。

&emsp;&emsp;保存并执行启动脚本.bat 后，最终将得到完整的文件结构：

![完整目录结构](https://raw.githubusercontent.com/Tollainmear/Guide-book-for-sponginism-survivors/master/%E5%9B%BE%E4%BE%8B/%E6%90%AD%E5%BB%BASponge%E6%9C%8D%E5%8A%A1%E7%AB%AF/%E7%AC%AC%E4%BA%8C%E6%AC%A1%E5%90%AF%E5%8A%A8%E5%AE%8C%E6%88%90.png)

#

### 6.下载并安装 Spongeforge
&emsp;&emsp;Sponge 官方网站为大家提供了非常多的版本的 Spongeforge，这里建议大家在[官网下载地址](https://www.spongepowered.org/downloads/spongeforge/stable/1.12.2)下载 `RECOMMENDED BUILD`（通常为置顶）。

&emsp;&emsp;这里需要注意：SpongeForge 必须严格对应 Forge 版本号（只能等于或者高于要求的 Forge 版本），我们可以从 SpongeForge 的命名方式得到要求的 Forge 版本号，例如名为 `1.12.2-2705-7.1.0-BETA-3361`的Spongeforge对应需要的Forge最低版本为`2705`。

###### 注：国内网络可以正常访问和下载 SpongeForge。

&emsp;&emsp;下载完成后我们需要把得到的 SpongeForge 放在`服务器根目录\mods`文件夹下，自此，SpongeForge 安装完毕

#

### 7.启动服务端
&emsp;&emsp;在你确保你每一步都操作无误后，即可运行`启动服务器.bat`进行服务器启动，启动完毕后，输入：
```
/sponge version
```
&emsp;&emsp;当输出如图所示的时候，代表您已经安装成功了。

![最终命令行显示](https://raw.githubusercontent.com/Tollainmear/Guide-book-for-sponginism-survivors/master/%E5%9B%BE%E4%BE%8B/%E6%90%AD%E5%BB%BASponge%E6%9C%8D%E5%8A%A1%E7%AB%AF/%E6%9C%80%E7%BB%88%E5%91%BD%E4%BB%A4%E8%A1%8C%E6%98%BE%E7%A4%BA.png)

#

### 8.注意事项
&emsp;&emsp;自此，我们已经完成了 Sponge 服务端的搭建步骤，同时，我们十分推荐您继续阅读我们整理的[管理规范（倡议）](未完成)部分，这将在很大程度上降低您的维护成本。

&emsp;&emsp;如果您在阅读本文的过程中遇到了任何问题，请在[Github](https://github.com/Tollainmear/Guide-book-for-sponginism-survivors/issues)上参与反馈，或者在相关帖子下方留言，感谢您的阅读。

#

### 供稿人：Tollainmear