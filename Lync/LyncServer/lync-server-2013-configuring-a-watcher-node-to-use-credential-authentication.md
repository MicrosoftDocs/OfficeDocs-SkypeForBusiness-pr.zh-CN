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
ms.openlocfilehash: d38a06c7ea40bd30f962484c8ce0d882c9633bf0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>将观察程序节点配置为在 Lync Server 2013 中使用凭据身份验证

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

如果您的观察程序节点计算机位于外围网络之外，则您必须遵循一个略有不同的过程来配置该观察程序节点以运行综合事务。具体而言，不应创建一个受信任的应用程序池和受信任的应用程序，而且必须安装一个证书，使得观察程序节点能够向外围网络内的计算机发送警报。这意味着您需要完成两个单独的任务：

  - 更新计算机的 RTC Local Read-only Administrators 组中的成员身份

  - 安装观察程序节点配置文件

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>更新 RTC Local Read-Only Administrators 组中的成员身份

如果您的观察程序节点位于外围网络之外，则您必须将 Network Service 帐户添加到观察程序节点计算机上的 RTC Local Read-only Administrators 组。为此，请在观察程序节点上完成以下过程：

1.  单击“开始”****，右键单击“计算机”****，然后单击“管理”****。

2.  在服务器管理器中，展开“配置”****，展开“本地用户和组”****，然后单击“组”****。

3.  在“组”窗格中，双击“RTC Local Read-only Administrators”****。

4.  在“RTC Local Read-only Administrators 属性”**** 对话框中，单击“添加”****。

5.  在“选择用户、计算机、服务帐户或组”**** 对话框中，单击“位置”****。

6.  在“位置”**** 对话框中，选择观察程序节点计算机的名称，然后单击“确定”****。

7.  在“输入要选择的对象名称”**** 框中，键入“Network Service”****，然后单击“确定”****。

8.  在“RTC Local Read-only Administrators 属性”**** 对话框中，单击“确定”****，然后关闭“服务器管理器”****。

重新启动观察程序节点计算机。

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>安装观察程序节点配置文件

重新启动观察程序节点计算机后，下一步是运行文件 Watchernode.msi。 若要运行此文件，请依次单击 "**开始**"、"**所有程序**"、" **lync Server 2013**" 和 " **lync server 命令行管理**程序"，打开 Lync server 2013 命令行管理程序。 在 Lync Server 命令行管理程序中，键入以下命令，然后按 ENTER （确保并指定 Watchernode.msi 副本的实际路径）：

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> 如上所述，还可以从命令窗口运行 Watchernode.msi。若要打开命令窗口，请单击“开始”<STRONG></STRONG>，右键单击“命令提示符”<STRONG></STRONG>，然后单击“以管理员身份运行”<STRONG></STRONG>。命令窗口打开后，键入如上所示的相同命令。



</div>

任何时候如果无法将观察程序节点设置为一个受信任应用程序池，都将使用协商模式。 在此模式中，管理员需要管理观察程序节点上的测试用户密码。

</div>

</div>

<span> </span>

</div>

</div>

</div>

