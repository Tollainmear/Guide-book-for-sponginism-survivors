### 引言
&emsp;&emsp;结合我们之前提到的相关特性，我们可以将Sponge的搭建步骤分解为以下几步：
##### 重中之重
没有规矩，不成方圆，请所有开服者遵守MojangAB为Minecraft服务器运营者指定的EULA（最终用户许可协议）：
[EULA](https://account.mojang.com/documents/minecraft_eula)

另外，本教程仅针对于正确安装了Java的Windows用户。
###### 1.下载MinecraftServer服务端
&emsp;&emsp;首先，从MC官网下载服务端内核：

【推荐】[1.12.2](http://s3.amazonaws.com/Minecraft.Download/versions/1.12.2/minecraft_server.1.12.2.jar)（推荐原因：插件mod稳定完备，以下例子将以本核心为准）

【不推荐】[1.13](https://launcher.mojang.com/mc/game/1.13/server/d0caafb8438ebd206f99930cfaecfa6c9a13dca0/server.jar)（不推荐原因：最新版的mod和插件不够完备）
###### 2.下载forge（以1.12.2的2705为例）
Forge官网：[https://files.minecraftforge.net/](https://files.minecraftforge.net/)

&emsp;&emsp;我们推荐您使用forge官方推荐的版本（Recommended，即有★标记的），如果Forge默认首页的Forge版本和您的服务端核心版本不对应，请点击左侧`Minecraft version`标签栏内对应的MC版本。

&emsp;&emsp;**确定版本对应后**，点击`Windows Installer`图标将会进入跳转页面。等待6秒后，点击右上角的Skip按钮即可开始下载。（无法跳转的用户请关闭阻止广告的插件）

注：因为国内部分地区无法进行网页跳转，因此，我们为这部分无法在官方下载的用户准备了[网盘备份](https://pan.baidu.com/s/1bMcI0wJ16lbAI-Xfbvb4Wg)，★请注意★为了保证Forge开发者的合理收益，除非您无法访问官方下载通道，否则请不要使用备用网盘，因为我们不保证备用网盘是最新的推荐版本。

###### 3.安装forge
&emsp;&emsp;到这一步的时候，我们假设已经得到了两个必要文件：
1. Minecraft_Server核心
2. 对应版本的Forge安装包

&emsp;&emsp;为了方便演示，我们创建一个名为`KaroglanServer`文件夹(这里明明随意)，然后将服务端核心放置进去，按以下步骤操作：
1. 双击打开forge安装程序
2. 如图所示，选择第二个`Install server`，并将路径选择到指定的路径。
3. 点击`确定` —— 开始安装

注：因为部分网络无法访问Forge依赖类库的下载网址，所以请根据情况自行切换线路
###### 4.启动服务器
&emsp;&emsp;因为未启动过的forge端没有生成必要文件结构，因此，我们需要先启动一次服务端，我们需要创建一个txt文件，将其内容改为：

```
java -Xms1024M -Xmx2048M -jar forge-1.12.2-14.23.4.2705-universal.jar nogui
pause
```
解释：
- Xms ： 表示最小内存分配，即初始内存（请根据实际情况调整）
- Xmx ： 表示最大内存分配，即最大内存（请根据实际情况调整）
- 1.12.2-14.23.4.2705-universal.jar ： 启动的核心文件，实际上是Forge生成的jar文件，可以在修改jar文件名后在这里改为修改后的名字
- nogui ： 无GUI界面
- pause ： 启动参数，当批处理命令执行完毕后暂停（用于调试）

修改完成后，保存关闭，并将此Txt文本后缀名改为.bat

注：如果无法修改拓展名，请根据[此教程](https://jingyan.baidu.com/article/b7001fe14f5cbe0e7282ddf5.html)，将拓展名显示出来

&emsp;&emsp;最后，双击启动你刚刚写完的bat文件，正常启动后，bat脚本将会自动暂停，如果图所示：

这里涉及到一个提示
```
You need to agree to the EULA in order to run the server. Go to eula.txt for more info.
```
翻译：
```
如果要运行服务器，你需要同意EULA协议，您可以查看eula.txt来了解更多信息。
```
如果显示正确，说明本步骤完成。
注：如果无法跳转到这一步，请：
- 检测Forge依赖类库的完整性
- 检测Java正确安装和配置
###### 3.第二次启动服务器

&emsp;&emsp;MojangAB要求所有服务器所有者必须遵守EULA协议方可运行服务器，详细的EULA请参考[这里](https://account.mojang.com/documents/minecraft_eula)。

&emsp;&emsp;操作方法：打开根目录文件夹下的`EULA.txt`文件，并将`eula=false`改为`eula=true`。

&emsp;&emsp;执行启动脚本.bat。

&emsp;&emsp;最终将得到完整的文件结构：

###### 5.下载并安装Spongeforge
&emsp;&emsp;Sponge官方网站为大家提供了非常多的版本的Spongeforge，这里建议大家在[官网下载地址](https://www.spongepowered.org/downloads/spongeforge/stable/1.12.2)下载`RECOMMENDED BUILD`（通常为置顶）。

&emsp;&emsp;这里需要注意：SpongeForge必须严格对应Forge版本号（只能等于或者高于要求的Forge版本），我们可以从SpongeForge的命名方式得到要求的Forge版本号，例如名为`1.12.2-2705-7.1.0-BETA-3361`的Spongeforge对应需要的Forge最低版本为`2705`。

注：国内网络可以正常访问和下载SpongeForge。

&emsp;&emsp;下载完成后我们需要把得到的SpongeForge放在`服务器根目录\mods`文件夹下，自此，SpongeForge安装完毕
###### 6.启动服务端
&emsp;&emsp;在你确保你每一步都操作无误后，即可运行`启动服务器.bat`进行服务器启动，启动完毕后，输入：
```
/sponge version
```
当输出如图所示的时候，代表您已经安装成功了。

###### 7.注意事项
&emsp;&emsp;自此，我们已经完成了Sponge服务端的搭建步骤，同时，我们十分推荐您继续阅读我们整理的[管理规范（倡议）](未完成)部分，这将在很大程度上降低您的维护成本。

&emsp;&emsp;如果您在阅读本文的过程中遇到了任何问题，请在[Github](https://github.com/Tollainmear/Guide-book-for-sponginism-survivors/issues)上参与反馈，或者在相关帖子下方留言，感谢您的阅读。

#### 供稿人：Tollainmear