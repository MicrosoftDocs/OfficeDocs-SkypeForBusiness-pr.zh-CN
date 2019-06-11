---
title: 'Lync Server 2013: 查看位置策略信息'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72e932449cc0e5b69fad46056dfda898d463c531
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看位置策略信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

在 Lync Server 2013 中, 你可以使用位置策略应用与增强的 9-1-1 (E9) 功能以及用户或联系人的位置设置相关的设置。 位置策略确定用户是否启用了 E9-1, 如果是紧急呼叫, 该行为是什么。 例如, 您可以使用位置策略定义哪个号码构成紧急呼叫 (例如, 美国 911)、是否应自动通知企业安全以及如何路由呼叫。

你可以从 Lync Server 2013 控制面板中的 "**网络配置**" 组配置位置策略。 从 Lync Server 控制面板, 您可以查看、创建、修改或删除位置策略。 使用以下过程查看有关位置策略的信息。 有关创建或修改位置策略的详细信息, 请参阅[在 Lync Server 2013 中创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)。

<div>

## <a name="to-view-information-about-a-location-policy"></a>查看有关位置策略的信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**位置策略**"。

4.  在 "**位置策略**" 页面上, 选择要修改的位置策略。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。
    
    <div>
    

    > [!NOTE]  
    > 一次只能查看一个位置策略的相关信息。

    
    </div>

默认情况下存在一个名为 Global 的策略, 不能删除或重命名。 但是, 你可以修改全局策略。 此政策将应用于所有用户和联系人, 除非你创建网站策略或每用户策略。 每用户策略必须应用于特定用户。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[在 Lync Server 2013 中创建位置策略](lync-server-2013-create-location-policies.md)  
[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)  


[新-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

