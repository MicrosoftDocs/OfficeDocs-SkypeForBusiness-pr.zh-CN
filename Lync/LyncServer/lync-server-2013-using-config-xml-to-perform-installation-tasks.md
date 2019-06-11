---
title: 'Lync Server 2013: 使用 Config.xml 执行安装任务'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3fb6f4c77375781b6c5d767087ad61f3ec6401b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>在 Lync Server 2013 中使用 Config.xml 执行安装任务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-02_

尽管 Office 自定义工具 (OCT) 是用于自定义安装的主要工具，但管理员可以使用 Config.xml 文件指定在 OCT 中不可用的其他安装说明。下列自定义只能通过 Config.xml 文件来进行：

  - 指定网络安装点的路径。

  - 选择要安装的产品。

  - 配置日志记录和安装程序自定义文件及软件更新的位置。

  - 指定安装选项，如用户名。

  - 无需安装 Office，将本地安装源 (LIS) 复制到用户的计算机上。

  - 在安装中添加语言或从安装中删除语言。

我们建议你使用 Config.xml 文件配置 Lync 2013 静默安装。

默认情况下, 存储在核心产品文件夹 (例如, 产品) \\中的 config.xml 文件。WW) 指导安装程序安装该产品。 例如, 以下文件夹中的 Config.xml 文件将安装 Lync 2013:

  - \\\\服务器\\共享\\Lync15\\Lync \\config.xml

下表列出了用于 Lync 2013 安装的最常用的 Config.xml 元素。

### <a name="configxml-elements"></a>Config.xml 元素

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
<td><p>配置</p></td>
<td><p>顶级元素（必需）。 包含 Product 属性, 例如: Product = Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>指定在安装期间如何处理特定产品功能。 使用以下属性来阻止企业连接服务的安装, 其中包括干扰 Outlook 2010 的共享组件:</p>
<ul>
<li><p>Id =&quot;LOBiMain&quot;</p></li>
<li><p>State =&quot;缺少&quot;</p></li>
<li><p>子级 =&quot;强制&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Display</p></td>
<td><p>安装程序向用户显示的 UI 级别。典型属性包括：</p>
<ul>
<li><p>CompletionNotice =&quot;是&quot; | &quot;No&quot;(默认值)</p></li>
<li><p>AcceptEula =&quot;是&quot; | &quot;No&quot;(默认值)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>日志记录</p></td>
<td><p>安装程序执行的日志记录类型的选项。典型属性包括：</p>
<ul>
<li><p>键入 =&quot;Off&quot; | &quot;标准&quot;(默认值) |&quot;详细&quot;</p></li>
<li><p>Template=”filename.txt”（日志文件的名称）</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>设置</p></td>
<td><p>指定 Windows Installer 属性的值。典型属性包括：</p>
<ul>
<li><p>设置 Id =&quot;Name&quot; (Windows Installer 属性的名称)</p></li>
<li><p>Value =&quot;value&quot; (分配给属性的值)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>从该位置运行安装的网络安装点的完全限定路径。包括 Location 属性：</p>
<ul>
<li><p>Location=”path”</p></li>
</ul></td>
</tr>
</tbody>
</table>


以下示例显示了 Lync 2013 的典型静默安装的 Config.xml 文件。

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

有关使用 Config.xml 文件执行 Office 安装和维护任务的详细信息, 请访问<http://go.microsoft.com/fwlink/p/?linkid=267514>。

<div>

## <a name="to-customize-the-configxml-file"></a>自定义 Config.xml 文件

1.  使用文本编辑器工具（例如记事本）打开 Config.xml 文件。

2.  找到包含您要更改元素的行。

3.  使用您需要的静默选项修改元素项。 请确保删除注释分隔符 "\<\!--" 和 "-\>"。 例如，使用以下语法：
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  保存 Config.xml 文件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

