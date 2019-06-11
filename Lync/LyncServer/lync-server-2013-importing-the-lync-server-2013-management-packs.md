---
title: 'Lync Server 2013: 导入 Lync Server 2013 管理包'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70c753334ea9a046c6081a73ce70e4de00de9188
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>导入 Lync Server 2013 管理包

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-22_

你可以通过安装管理包来扩展 System Center Operations Manager 的功能, 即决定 System Center Operations Manager 可以监视哪些项目以及应如何监视这些项目以及应如何触发警报的软件以及据. Lync Server 2013 包括两个 System Center Operations Manager 管理包, 它们提供以下功能:

  - 组件和用户管理包 (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) 跟踪事件日志中记录的 Lync Server 问题 (由性能计数器注册), 或记录在呼叫详细记录 (CDR) 或体验质量 (QoE) 中。数据库. 对于严重问题, System Center Operations Manager 可以配置为通过电子邮件、即时消息或短消息服务 (SMS) 消息通知立即通知管理员。 SMS 是用于将文本消息从一个移动设备发送到另一个移动设备的技术。
    
    <div>
    

    > [!NOTE]  
    > 有关配置 Operations Manager 通知的详细信息, 请参阅 TechNet 库中的配置通知<A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>。

    
    </div>

  - 活动监视管理包 (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) 主动测试关键 Lync 服务器组件, 如登录到系统、交换即时消息或拨打公共交换上的电话电话网络 (PSTN)。 这些测试通过 Lync Server 合成事务 cmdlet 进行。 例如, 你可以使用**CsIM** cmdlet 来模拟一对测试用户之间的即时消息 (IM) 对话。 如果此模拟消息对话失败, 则会生成一个警报。

您需要导入管理包。 如果不导入管理包, 则无法使用 Operations Manager 监视 Lync 服务器事件或运行 Lync Server 合成事务。

组件和用户管理包仅用于监视 Lync Server 2013。 如果你在共存方案中, 同时安装了 Lync Server 2013 和 Lync Server 2010, 则应继续为 Lync Server 2010 计算机使用 Lync Server 2010 管理包。

<div>


> [!NOTE]  
> Lync Server 2010 的管理包包括 Lync Server 2010 监视管理包和 Lync Server 2010 组聊天监视管理包。



</div>

可使用下列任一工具导入管理包：

  - **System Center Operations Manager**   使用此方法, 你可以使用 Operations Manager 添加 Lync Server 的监视。

  - **Operations manager 外壳**   程序你可以使用 operations manager 外壳程序直接导入, 或通过使用 System Center Operations Manager 控制台导入管理包时遇到的任何问题进行故障排除。

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>使用 System Center Operations Manager 导入管理包

1.  下载文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 和 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp。

2.  在 System Center Operations Manager 中, 单击 "**管理**"。

3.  在 "**管理**" 窗格中, 右键单击 "**管理包**", 然后单击 "**导入管理包**"。

4.  在“选择管理包”**** 对话框中，单击“添加”****，然后单击“从磁盘中添加”****。

5.  在 "**联机目录连接**" 对话框中, 单击 "**取消**" 以防止 Operations Manager 联机以查看 Lync Server 管理包是否存在任何依赖关系。 如果您使用的是 System Center Operations Manager 2012, 请单击 "**否**"。

6.  在 "**选择要导入的管理包**" 对话框中, 找到并选择 "文件**Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** " 和 " **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** ", 然后单击 "**打开**"。 若要选择对话框中的多个文件, 请单击第一个文件, 按住 Ctrl 键, 然后单击第二个文件。

7.  在“选择管理包”**** 对话框中，单击“安装”****。 如果您收到错误消息并且安装失败，则通常意味着管理包文件位于受 Windows 用户帐户控制保护的文件夹中。 如果出现这种情况, 请将文件复制到其他文件夹, 然后重新启动导入和安装过程。

8.  在“选择管理包”**** 对话框中，单击“关闭”****。 请注意, 导入和安装过程可能需要几分钟才能完成。

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>使用 Operations Manager 外壳程序导入管理包

一般情况下, 使用 Operations Manager 更容易导入管理包。但是, 如果出现错误, 并且导入失败, 则控制台不会始终提供足够的错误报告。 通过比较, Operations Manager Shell 提供详细信息。 如果你使用的是 Operations Manager, 并且在导入管理包时遇到问题, 请使用 Operations Manager 外壳程序导入该程序包。 Operations Manager Shell 提供详细信息, 可帮助你确定导入失败的原因。

如果您使用的是 System Center Operations Manager 2007 R2, 请完成以下过程:

1.  依次单击 "**开始**"、"**所有程序**"、" **System Center Operations Manager 2007 R2**", 然后单击 " **Operations Manager 外壳**程序"。

2.  在 Operations Manager Shell 中, 使用文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 副本的实际路径在命令提示符处键入以下命令, 然后按 ENTER:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  导入第一个管理包后, 使用文件 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 副本的路径重复该过程:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  关闭 Operations Manager 外壳程序。

如果您使用的是 System Center Operations Manager 2012, 请改为完成此过程:

1.  依次单击“开始”****、“所有程序”****、“Microsoft System Center 2012”****、“Operations Manager”**** 和“Operations Manager Shell”****。

2.  在 Operations Manager Shell 中, 使用文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 副本的实际路径在命令提示符处键入以下命令, 然后按 ENTER:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  导入第一个管理包后, 请使用文件 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 的副本的路径重复该过程:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

