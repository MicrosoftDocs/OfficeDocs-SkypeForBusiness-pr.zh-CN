---
title: Lync Server 2013：配置观察程序节点以使用凭据身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d0fa67c4ef2688035471d2290ead78123f73239
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>将观察程序节点配置为使用 Lync Server 2013 中的凭据身份验证

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-20_

如果你的观察程序节点计算机位于外围网络之外，则你必须执行稍有不同的过程，才能将该观察程序节点配置为运行合成事务。 具体而言，不应创建受信任的应用程序池和受信任的应用程序，并且必须安装一个允许观察程序节点向外围网络内的计算机发送警报的证书。 这意味着你需要完成两个单独的任务：

  - 更新计算机的 RTC 本地只读管理员组中的成员身份

  - 安装观察程序节点配置文件

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>更新 RTC 本地只读管理员组中的成员身份

如果你的观察程序节点位于外围网络外部，则必须将网络服务帐户添加到观察程序节点计算机上的 RTC 本地只读管理员组。 若要执行此操作，请在 "观察程序" 节点上完成以下过程：

1.  单击 "**开始**"，右键单击 "**计算机**"，然后单击 "**管理**"。

2.  在服务器管理器中，展开 "**配置**"，展开 "**本地用户和组**"，然后单击 "**组**"。

3.  在 "组" 窗格中，双击 " **RTC 本地只读管理员**"。

4.  在 " **RTC 本地只读管理员属性**" 对话框中，单击 "**添加**"。

5.  在 "**选择用户、计算机、服务帐户或组**" 对话框中，单击 "**位置**"。

6.  在 "**位置**" 对话框中，选择 "观察程序节点" 计算机的名称，然后单击 **"确定"**。

7.  在 "**输入要选择的对象名称**" 框中，键入 "**网络服务**"，然后单击 **"确定"**。

8.  在 " **RTC 本地只读管理员属性**" 对话框中，单击 **"确定**"，然后关闭 "**服务器管理器**"。

重新启动观察程序节点计算机。

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>安装观察程序节点配置文件

在观察程序节点计算机重启后，下一步是运行文件 Watchernode。 若要运行此文件，请依次单击 "**开始**"、"**所有程序**"、" **lync server 2013**"，然后单击 " **Lync Server Management Shell**"，打开 Lync Server 2013 命令行管理程序。 在 Lync Server 命令行管理器中，键入以下命令，然后按 ENTER （确保并指定 Watchernode 副本的实际路径）：

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> 正如前面所述，Watchernode 也可以从命令窗口运行。 若要打开命令窗口，请单击“开始”<STRONG></STRONG>，右键单击“命令提示符”<STRONG></STRONG>，然后单击“以管理员身份运行”<STRONG></STRONG>。 当 "命令" 窗口打开时，键入与前面所示相同的命令。



</div>

任何时候如果无法将观察程序节点设置为一个受信任应用程序池，都将使用协商模式。在此模式中，管理员需要管理观察程序节点上的测试用户密码。

</div>

</div>

<span> </span>

</div>

</div>

</div>

