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
ms.openlocfilehash: ce1940f92860d5ccd2d66c53a0a4da16cebada24
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>在 Lync Server 2013 中查看设备的软件更新

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

使用 Lync Server 2013，可以使用设备更新 Web 服务查看和管理组织设备的软件更新。 来自 Microsoft 支持网站的 .cab （cab）文件中提供了这些更新[https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)。 下载 .cab 文件后，运行**CSDeviceUpdate** cmdlet 将设备更新规则从 .cab 文件中导入。 有关**CSDeviceUpdate** cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档中的[import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) 。

<div>


> [!TIP]  
> 将新的更新部署到组织之前，请验证其在测试设备上是否正常工作。



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>查看 UC 设备的软件更新

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  在处[https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)的 Microsoft 支持网站中，将 .cab 文件下载到 Lync Server 2013 计算机上的某个位置（例如，C：\\Updates\\为 ucupdates-r2.）。

3.  通过运行以下 cmdlet 之一，从 C：\\Updates\\为 ucupdates-r2. 文件中导入设备更新规则：
    
      - 如果 .cab 文件位于运行要更新的服务 (service:Redmond-websvc-2) 的计算机上，请运行以下 cmdlet：
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - 如果 .cab 文件不在运行要更新的服务 (service:Redmond-websvc-3) 的计算机上，请运行以下 cmdlet：
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

5.  在左侧导航栏中，单击 **“客户端”**，然后单击 **“设备更新”**。

6.  在 **“设备更新”** 页上，单击列表中的更新，然后执行下列操作之一：
    
      - **取消待处理的更新。** 要阻止将所选更新部署到组织的设备，请单击 **“操作”** 菜单，然后单击 **“取消待处理的更新”**。
    
      - **批准更新。** 要允许将所选更新部署到组织的设备，请单击 **“操作”** 菜单，然后单击 **“批准”**。
    
      - **还原更新。** 要允许将先前批准的更新部署到组织的设备，请单击 **“操作”** 菜单，然后单击 **“还原”**。

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

