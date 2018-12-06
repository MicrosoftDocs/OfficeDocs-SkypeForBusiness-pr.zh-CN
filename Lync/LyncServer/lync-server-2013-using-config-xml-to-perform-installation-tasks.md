---
title: 使用 Config.xml 执行安装任务
TOCTitle: 使用 Config.xml 执行安装任务
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204651(v=OCS.15)
ms:contentKeyID: 49311910
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用 Config.xml 执行安装任务

 

_**上一次修改主题：** 2016-12-08_

尽管 Office 自定义工具 (OCT) 是用于自定义安装的主要工具，但管理员可以使用 Config.xml 文件指定在 OCT 中不可用的其他安装说明。下列自定义只能通过 Config.xml 文件来进行：

  - 指定网络安装点的路径。

  - 选择要安装的产品。

  - 配置日志记录和安装程序自定义文件及软件更新的位置。

  - 指定安装选项，如用户名。

  - 无需安装 Office，将本地安装源 (LIS) 复制到用户的计算机上。

  - 在安装中添加语言或从安装中删除语言。

建议您使用 Config.xml 文件配置 Lync 2013 无提示安装。

默认情况下，存储在核心产品文件夹（例如 \\*product*.WW）中的 Config.xml 文件会指示安装程序安装该产品。例如，以下文件夹中的 Config.xml 文件将安装 Lync 2013：

  - \\\\server\\share\\Lync15\\Lync.WW \\Config.xml

下表列出了最常用于 Lync 2013 安装的 Config.xml 元素。

### Config.xml 元素

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>元素</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuration</p></td>
<td><p>顶级元素（必需）。包含 Product 属性，例如：Product=Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>指定在安装期间如何处理特定产品功能。使用以下属性可防止安装 Business Connectivity Services，其中包括干扰 Outlook 2010 运行的共享组件：</p>
<ul>
<li><p>Id=&quot;LOBiMain&quot;</p></li>
<li><p>State=&quot;Absent&quot;</p></li>
<li><p>Children=&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Display</p>
<p></p></td>
<td><p>安装程序向用户显示的 UI 级别。典型属性包括：</p>
<ul>
<li><p>CompletionNotice=&quot;Yes&quot; | &quot;No&quot;（默认值）</p></li>
<li><p>AcceptEula=&quot;Yes&quot; | &quot;No&quot;（默认值）</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Logging</p></td>
<td><p>安装程序执行的日志记录类型的选项。典型属性包括：</p>
<ul>
<li><p>Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</p></li>
<li><p>Template=”<em>filename</em>.txt”（日志文件的名称）</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Setting</p></td>
<td><p>指定 Windows Installer 属性的值。典型属性包括：</p>
<ul>
<li><p>Setting Id=&quot;<em>name</em>&quot;（Windows Installer 属性的名称）</p></li>
<li><p>Value=&quot;<em>value</em>&quot;（分配给该属性的值）</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>从该位置运行安装的网络安装点的完全限定路径。包括 Location 属性：</p>
<ul>
<li><p>Location=”<em>path</em>”</p></li>
</ul></td>
</tr>
</tbody>
</table>


以下示例演示用于 Lync 2013 的典型无提示安装的 Config.xml 文件。

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

有关使用 Config.xml 文件执行 Office 安装和维护任务的详细信息，请参见 [http://go.microsoft.com/fwlink/?linkid=267514\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=267514%26clcid=0x804)。

## 自定义 Config.xml 文件

1.  使用文本编辑器工具（例如记事本）打开 Config.xml 文件。

2.  找到包含您要更改元素的行。

3.  使用您需要的静默选项修改元素项。确保删除注释分隔符，“\<\!--”和“--\>”。例如，使用以下语法：
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  保存 Config.xml 文件。

