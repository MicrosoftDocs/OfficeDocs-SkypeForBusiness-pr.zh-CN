---
title: 根据主街道地址指南测试市政地址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d6aa1443dc2e062aa099237d9b25f2b33e32b2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>根据 Lync Server 2013 中的主要街道地址指南测试市政地址

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>验证计划</p></td>
<td><p>每天</p></td>
</tr>
<tr class="even">
<td><p>测试工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要权限</p></td>
<td><p>当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsRegistration cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsLisCivicAddress cmdlet 用于验证添加到您的位置信息服务（.LIS）数据库中的位置。 该 cmdlet 的工作原理是将位置与属于 E9 网络路由提供商的主街道地址指南（MSAG）中找到的位置进行比较。 如果你没有网络路由提供程序或无法访问提供程序，则你的测试将失败。

如果将可选的开关参数 UpdateValidationStatus 添加到命令，则每个传递测试的地址都将为其设置相应的 MSAGValid 数据库属性。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsLisCivicAddress cmdlet 可用于测试各个地址或测试多个地址。 例如，此命令测试位于 Redmond、WA 中的单个地址：

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

通过比较，此命令将测试 IIS 数据库中当前的所有地址：

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

有关详细信息，请参阅[CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

CsLisCivicAddress 将报告提供的地址的成功或失败。 如果找不到地址或无法联系服务提供商，则地址测试将失败。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsLisCivicAddress 可能失败的一些常见原因：

  - .LIS 服务提供商可能不可用。 你可以通过运行 CsLisConfiguration cmdlet 来检索 IIS 的服务提供商的 URL：
    
        Get-CsLisConfiguration 
    
    然后，你可以 ping 该 URL 以验证服务提供程序是否可用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

