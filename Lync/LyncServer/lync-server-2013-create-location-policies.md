---
title: Lync Server 2013：创建位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eca6b5c2b4bb88ed1b611eedd831c5c30d14bbb2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a>在 Lync Server 2013 中创建位置策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-11_

Lync Server 使用位置策略在客户端注册过程中为 E9-1-1 启用 Lync 客户端。 位置策略包含定义 E9-1-1 实现方式的设置。

可以编辑全局位置策略，并创建新的带标记的位置策略。客户端所在的子网没有关联位置策略，或没有直接为客户端分配位置策略时，客户端会获取全局策略。向子网或用户分配带标记的策略。

要创建位置策略，必须使用 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator 管理角色成员的帐户，或者具有等效管理员权限的帐户。

有关位置策略的完整说明，请参阅[定义 Lync Server 2013 的位置策略](lync-server-2013-defining-the-location-policy.md)。 此过程中的 Cmdlet 使用下列值定义的位置策略：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>元素</th>
<th>值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnhancedEmergencyServicesEnabled</p></td>
<td><p><strong>True</strong></p></td>
</tr>
<tr class="even">
<td><p>LocationRequired</p></td>
<td><p><strong>免责声明</strong></p></td>
</tr>
<tr class="odd">
<td><p>EnhancedEmergencyServiceDisclaimer</p></td>
<td><p>您的公司策略要求您设置一个位置。如果不设置位置，紧急情况下，紧急服务将无法找到您。请设置一个位置。</p></td>
</tr>
<tr class="even">
<td><p>UseLocationForE911Only</p></td>
<td><p><strong>False</strong></p></td>
</tr>
<tr class="odd">
<td><p>PstnUsage</p></td>
<td><p><strong>EmergencyUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>EmergencyDialString</p></td>
<td><p><strong>911</strong></p></td>
</tr>
<tr class="odd">
<td><p>EmergencyDialMask</p></td>
<td><p><strong>112</strong></p></td>
</tr>
<tr class="even">
<td><p>NotificationUri</p></td>
<td><p><strong>sip:security@litwareinc.com</strong></p></td>
</tr>
<tr class="odd">
<td><p>ConferenceUri</p></td>
<td><p><strong>sip:+14255550123@litwareinc.com</strong></p></td>
</tr>
<tr class="even">
<td><p>ConferenceMode</p></td>
<td><p><strong>twoway</strong></p></td>
</tr>
<tr class="odd">
<td><p>LocationRefreshInterval</p></td>
<td><p><strong>双面</strong></p></td>
</tr>
</tbody>
</table>


有关使用位置策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - 新 New-cslocationpolicy

  - New-cslocationpolicy

  - New-cslocationpolicy

  - New-cslocationpolicy

  - Grant-New-cslocationpolicy

<div>

## <a name="to-create-location-policies"></a>创建位置策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。
    
    <div>
    

    > [!NOTE]  
    > 如果 PstnUsages 的全局列表中还没有 <STRONG>PstnUsage</STRONG> 设置，则 CsLocationPolicy 会失败。

    
    </div>

2.  也可以选择运行以下 cmdlet 编辑全局位置策略：
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  运行以下命令创建带标记的位置策略。
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  运行以下 cmdlet 将步骤 3 中创建的带标记的位置策略应用于用户策略。
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

