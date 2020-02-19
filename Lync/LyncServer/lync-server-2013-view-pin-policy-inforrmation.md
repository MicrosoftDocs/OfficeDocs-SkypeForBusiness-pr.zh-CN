---
title: Lync Server 2013：查看 PIN 策略信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 855fa6afe5cd0d302fbd999675d18e2bf5535074
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a>在 Lync Server 2013 中查看 PIN 策略信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

您可以使用 " **PIN 策略**" 选项卡查看使用 IP 电话连接到 Lync 2013 的用户的个人标识号（PIN）身份验证。 要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”****。 有关详细信息，请参阅[在 Lync Server 2013 中修改现有的 Web 服务配置设置](lync-server-2013-modify-existing-web-service-configuration-settings.md)。

按照以下步骤修改用户级别或站点级别的 PIN 策略。

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a>在 Lync Server 控制面板中查看有关 PIN 策略的信息

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“安全性”****，然后单击“PIN 策略”****。

4.  在 " **PIN 策略**" 页上，单击某个策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看 PIN 策略

您还可以使用 Windows PowerShell 和 Get-cspinpolicy cmdlet 查看 PIN 策略。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-view-pin-policies"></a>查看 PIN 策略

  - 若要查看有关所有 PIN 策略的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsPinPolicy
    
    这将返回与以下类似的信息：
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

有关详细信息，请参阅[get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中修改现有的 Web 服务配置设置](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[在 Lync Server 2013 中创建新的 PIN 策略](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

