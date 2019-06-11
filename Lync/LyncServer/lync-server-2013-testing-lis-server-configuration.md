---
title: 'Lync Server 2013: 测试 .LIS 服务器配置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e5baed37e4c72da8b8348dab9702b5d22fbbc5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中测试 .LIS 服务器配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-06-05_


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
<td><p>当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsLisConfiguration cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsLisConfiguration cmdlet 验证你是否能够联系 .LIS web 服务。 如果可以联系到 web 服务, 则会将测试视为成功, 无论是否可以找到任何特定位置。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsLisConfguration cmdlet 可以使用预配置的测试帐户运行 (请参阅设置运行 Lync Server 测试的测试帐户) 或已启用 Lync Server 的任何用户的帐户。 若要使用测试帐户运行此检查, 只需指定正在测试的 Lync Server 池的 FQDN。 例如：

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查, 必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。 然后, 在调用 Test-CsLisConfiguration 时, 必须包含该凭据对象和分配给该帐户的 SIP 地址:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息, 请参阅[CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果 IIS 配置正确, 你将收到类似于此的输出, 结果属性标记为**成功:**

TargetUri :https://atl-cs-001.litwareinc.com:443/locationinformation/

liservice

TargetFqdn: atl-cs-001.litwareinc.com

结果: 成功

延迟:00:00: 06.1616913

时发生

自检

如果指定用户无法登录或注销, 则结果将显示为 "失败", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:

TargetUri :

TargetFqdn: atl-cs-001.litwareinc.com

结果: 失败

延迟: 00:00:00

错误: 11004, 所请求的名称有效, 但没有请求的数据

已找到类型

自检

Test-CsLisConfiguration: 在拓扑中找不到匹配的群集。

例如, 以前的输出包含注释 "在拓扑中找不到匹配的群集"。 这通常表示边缘服务器存在问题: IIS 使用边缘服务器连接到服务提供商并验证地址。

如果测试 CsLisConfiguration 失败, 您可能需要重新运行测试, 这一次包括 Verbose 参数:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

当包含 Verbose 参数时, CsLisConfiguration 将返回在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。 例如：

呼叫位置信息服务。

服务路径 =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

子网 =

BssId = 5

ChassisId =

PortId =

PortIdSubType = 未定义的类型

Mac

异常 "位置信息 Web 服务请求失败, 响应代码为 Item400。" 在 STLisConfigurationWorkflow 执行工作流期间发生。

如果你仔细检查以前的输出, 你将看到 cmdlet 在尝试调用位置信息服务后失败。 该调用中使用的参数之一如下所示:

BssId = 5

这不是基本服务集标识符 (BssID) 的有效值。 相反, BssID 应如下所示:

12-34-56-78-90-ab

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsLisConfiguration 可能失败的一些常见原因:

  - 提供的参数值不正确。 如前面的示例所示, 必须正确配置可选参数, 否则测试将失败。 重新运行不带可选参数的命令, 并查看是否成功。

</div>

</div>

<span> </span>

</div>

</div>

</div>

