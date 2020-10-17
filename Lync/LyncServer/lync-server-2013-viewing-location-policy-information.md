---
title: Lync Server 2013：查看位置策略信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b5c4b512acc3541b933f583ad69e3f730dc14f9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523509"
---
# <a name="viewing-location-policy-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看位置策略信息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

在 Lync Server 2013 中，可以使用位置策略应用与增强的 9-1-1 (E9-1-1) 功能以及用户或联系人的位置设置相关的设置。 位置策略可确定用户是否启用了 E9-1-1，以及在启用了该服务时紧急呼叫的行为。 例如，您可以使用位置策略定义哪些数字构成紧急呼叫（例如，美国的 911）、是否应自动通知企业安全人员以及应如何路由该呼叫。

您可以在 Lync Server 2013 控制面板中的 " **网络配置** " 组中配置位置策略。 从 Lync Server 控制面板中，您可以查看、创建、修改或删除位置策略。 可使用以下过程查看位置策略的信息。 有关创建或修改位置策略的详细信息，请参阅 [在 Lync Server 2013 中创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)。

<div>

## <a name="to-view-information-about-a-location-policy"></a>查看位置策略的信息

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“位置策略”****。

4.  在“位置策略”**** 页上，选择要修改的位置策略。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。
    
    <div>
    

    > [!NOTE]  
    > 一次只能查看一个位置策略的信息。

    
    </div>

默认情况下，存在一个名为“全局”的策略，无法将其删除或进行重命名。但是，您可以修改“全局”策略。该策略将应用于所有用户和联系人，除非您创建站点策略或每用户策略。每用户策略必须应用于特定用户。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[在 Lync Server 2013 中创建位置策略](lync-server-2013-create-location-policies.md)  
[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)  


[新 New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

