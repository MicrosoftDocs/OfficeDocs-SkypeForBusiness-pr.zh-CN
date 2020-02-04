---
title: Lync Server 2013：查看组织中设备的软件更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9a969aac4559f02ee7d05f36bece84e40f65aca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>在 Lync Server 2013 中查看设备的软件更新

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

使用 Lync Server 2013，您可以使用 "设备更新" Web 服务查看和管理您的组织的设备的软件更新。 来自 Microsoft 支持网站的 .cab （cabinet）文件中提供了这些更新[http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)。 下载 .cab 文件后，运行**CSDeviceUpdate** cmdlet 以从 .cab 文件中导入设备更新规则。 有关**CSDeviceUpdate** cmdlet 的详细信息，请参阅 Lync Server Management Shell 文档中的[Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) 。

<div>


> [!TIP]  
> 在为你的组织部署新的更新之前，请验证它在测试设备上是否正常工作。



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>查看 UC 设备的软件更新

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  从 Microsoft 支持网站中[http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)，将 .cab 文件下载到 Lync Server 2013 计算机上的某个位置（例如，C：\\Updates\\UCUpdates）。

3.  通过运行以下 cmdlet 之一，从 C：\\Updates\\UCUpdates 文件中导入设备更新规则：
    
      - 如果 .cab 文件与运行要更新的服务的同一台计算机（服务： Redmond-websvc）位于同一台计算机上，请运行以下 cmdlet：
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - 如果 .cab 文件所在的计算机不同于运行要更新的服务的计算机（服务： Redmond-websvc），请运行以下 cmdlet：
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

5.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**设备更新**"。

6.  在 "**设备更新**" 页面上，单击列表中的更新，然后执行下列操作之一：
    
      - **取消待处理的更新。** 若要阻止所选更新部署到你的组织的设备，请单击 "**操作**" 菜单，然后单击 "**取消挂起的更新**"。
    
      - **批准更新。** 若要允许将所选更新部署到你的组织的设备，请单击 "**操作**" 菜单，然后单击 "**批准**"。
    
      - **还原更新。** 若要允许将以前批准的更新部署到你的组织的设备，请单击 "**操作**" 菜单，然后单击 "**还原**"。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中管理设备、电话和客户端应用程序](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

