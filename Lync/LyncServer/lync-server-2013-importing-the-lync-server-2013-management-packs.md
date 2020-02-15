---
title: Lync Server 2013：导入 Lync Server 2013 管理包
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adaf9fe1c6d5d4cc0769810aece05bcb46681e79
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>导入 Lync Server 2013 管理包

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

您可以通过安装管理包来扩展 System Center Operations Manager 的功能，该软件规定 System Center Operations Manager 可以监视的项目，以及应如何监视这些项目以及应如何触发警报以及如何触发警报以及报表. Lync Server 2013 包括两个 System Center Operations Manager 管理包，它们提供以下功能：

  - 组件和用户管理包（Microsoft.LS.2013.Monitoring.ComponentAndUser.mp）跟踪事件日志中记录的、由性能计数器注册的 Lync Server 问题，或记录在呼叫详细信息记录（CDR）或用户体验质量（QoE）中的数据库. 对于关键问题，可以将 System Center Operations Manager 配置为立即通过电子邮件、即时消息或短信服务（SMS）消息通知管理员。 SMS 是用于将短信从一个移动设备发送到另一个移动设备的技术。
    
    <div>
    

    > [!NOTE]  
    > 有关配置 Operations Manager 通知的详细信息，请参阅 TechNet Library 中的配置通知<A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>。

    
    </div>

  - 主动监控管理包（Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp）主动测试重要的 Lync Server 组件，例如，登录到系统、交换即时消息或呼叫位于公开交换的电话电话网络（PSTN）。 这些测试通过使用 Lync Server 综合事务 cmdlet 进行。 例如，您可使用 **Test-CsIM** cmdlet 在一对测试用户之间模拟即时消息 (IM) 对话。 如果此命令模拟消息对话失败，则将生成警报。

您需要导入管理包。 如果不导入管理包，则不能使用 Operations Manager 来监视 Lync Server 事件或运行 Lync Server 合成事务。

组件和用户管理包仅用于监视 Lync Server 2013。 如果您在共存方案中，同时安装了 Lync Server 2013 和 Lync Server 2010，则应继续为 Lync Server 2010 计算机使用 Lync Server 2010 管理包。

<div>


> [!NOTE]  
> Lync Server 2010 的管理包包括 Lync Server 2010 监视管理包和 Lync Server 2010 组聊天监控管理包。



</div>

可使用下列任一工具导入管理包：

  - **System Center Operations Manager**   通过此方法，您可以使用 Operations Manager 为 Lync Server 添加监控。

  - **Operations manager 命令行**   管理程序您可以使用 operations manager 命令行管理程序直接导入，或解决在使用 System Center Operations Manager 控制台导入管理包时遇到的任何问题。

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>使用 System Center Operations Manager 导入管理包

1.  下载文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 和 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp。

2.  在 System Center Operations Manager 中，单击 "**管理**"。

3.  在“管理”**** 窗格中，右键单击“管理包”****，然后单击“导入管理包”****。

4.  在“选择管理包”**** 对话框中，单击“添加”****，然后单击“从磁盘中添加”****。

5.  在 "**联机目录连接**" 对话框中，单击 "**取消**" 以阻止 Operations Manager 联机查看是否存在与 Lync Server 管理包相关的依赖项。 如果使用的是 System Center Operations Manager 2012，请单击 "**否**"。

6.  在“选择要导入的管理包”**** 对话框中，查找并选择“Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp”**** 和“Microsoft.LS.2013.Monitoring.ComponentAndUser.mp”****，然后单击“打开”****。若要在对话框中选择多个文件，请单击第一个文件，按住 Ctrl 键，然后单击第二个文件。

7.  在“选择管理包”**** 对话框中，单击“安装”****。如果您收到错误消息并且安装失败，则通常意味着管理包文件位于受 Windows 用户帐户控制保护的文件夹中。如果出现此情况，请将文件复制到其他文件夹中，然后重新开始导入和安装过程。

8.  在“选择管理包”**** 对话框中，单击“关闭”****。请注意，导入和安装过程可能需要几分钟时间才能完成。

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>使用 Operations Manager 命令行管理程序导入管理包

通常情况下，使用 Operations Manager 导入管理包更为简单。但是，如果发生错误，并且导入失败，则控制台不总是提供足够的错误报告。 通过比较，Operations Manager 命令行管理程序提供了详细信息。 如果您使用的是 Operations Manager，并且在导入管理包时遇到问题，请使用 Operations Manager 命令行管理程序导入该程序包。 Operations Manager 命令行管理程序提供了详细信息，可帮助您确定导入失败的原因。

如果您使用的是 System Center Operations Manager 2007 R2，请完成以下过程：

1.  依次单击 "**开始**"、"**所有程序**"、" **System Center Operations Manager 2007 R2**" 和 " **Operations Manager Shell**"。

2.  在 Operations Manager 命令行管理程序中，使用文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 的副本的实际路径在命令提示符处键入以下命令，然后按 ENTER：
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  导入第一个管理包之后，使用至文件 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 的副本的路径重复此过程：
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  关闭 Operations Manager 命令行管理程序。

如果使用的是 System Center Operations Manager 2012，请改为完成此过程：

1.  依次单击 "**开始**"、"**所有程序**"、" **Microsoft System Center 2012**"、" **Operations manager**" 和 " **operations manager Shell**"。

2.  在 Operations Manager 命令行管理程序中，使用文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 的副本的实际路径在命令提示符处键入以下命令，然后按 ENTER：
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  导入第一个管理包之后，使用至文件 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 的副本的路径重复此过程：
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

