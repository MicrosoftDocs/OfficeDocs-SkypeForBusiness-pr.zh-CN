---
title: Lync Server 2013：测试副本服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cae11cce4d4214f0392304823710fe1f02a36f7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>在 Lync Server 2013 中测试副本服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-11-03_


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
<td><p>所需的权限</p></td>
<td><p>在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>CsReplica</strong> cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

**CsReplica** Cmdlet 验证 Lync Server 2013 副本服务是否正在本地计算机上运行。 **CsReplica** cmdlet 执行以下任务：

  - 检查复制器代理和集中日志记录代理服务的状态

  - 验证是否已在 Windows 防火墙中打开所需的端口

  - 确保所需的 Active Directory 和本地计算机安全组存在。

请注意，此 cmdlet 必须在本地运行。 也就是说，它必须在运行副本服务的同一台计算机上运行。 没有用于对远程服务器运行**CsReplica** cmdlet 的选项。

</div>

<div>

## <a name="running-the-test"></a>运行测试

示例1中显示的命令测试本地计算机上的 Lync Server 2013 副本服务。 在此示例中，Verbose 参数用于确保有关测试的信息（包括测试的最终故障或成功）以及由测试生成的报告的位置显示在屏幕上。

    Test-CsReplica -Verbose

示例 2 是示例 1 中显示的命令的变体。 在这种情况下，将包含 Report 参数，以指定由测试生成的报告的文件夹路径和名称。 如果不指定报告路径，将向报告提供如下所示的自动生成的名称：

C：\\用户\\Litwareinc\\AppData\\本地\\临时\\1\\测试-Cs-副本-3db40ee0-4b5d-4f58-8d3d-b1e61253129e

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

在此处插入章节正文。

详细：创建新日志文件 "C：\\用户\\测试\\AppData\\本地\\临时\\测试-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c"。

详细：创建新日志文件 "C：\\用户\\测试\\AppData\\本地\\临时\\测试-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c"。

详细： "Test-CsReplica" 处理已成功完成。

详细：可在 "\\C：用户\\测试\\AppData\\本地\\临时\\测试-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c" 中找到详细结果。

详细：创建新的日志文件

"C：\\用户\\测试\\AppData\\本地\\临时\\2\\测试-CsReplica-29fddb35-f56e-4e3c-8f4c-e"

d3bd0e4a083 "。

详细：创建新的日志文件

"C：\\用户\\测试\\AppData\\本地\\临时\\2\\测试-CsReplica-29fddb35-f56e-4e3c-8f4c-e"

d3bd0e4a083 "。

警告： CsReplica 失败。

警告：详细结果可在以下位置找到：

"C：\\用户\\测试\\AppData\\本地\\临时\\2\\测试-CsReplica-29fddb35-f56e-4e3c-8f4c-e"

d3bd0e4a083 "。

测试-CsReplica：命令执行失败：请求的注册表访问不是

支持.

位于第1行：1个字符：1

\+CsReplica-Verbose

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo： InvalidOperation：（:)\[CsReplica\]、Security

异常

\+FullyQualifiedErrorId： ProcessingFailed，Microsoft .aspx. .Deploy

。TestReplicaCmdlet

PS C：\\用户\\测试\>

PS C：\\用户\\测试\> test-csucwaconference-TargetFqdn "LyncTest

icrosoft.com "

警告：无法读取给定的完全限定的注册器端口号

域名（FQDN）。 使用默认注册器端口号。 异常

InvalidOperationException：在拓扑中找不到匹配的群集。

个

TryRetri 的 SipSyntheticTransaction。 SyntheticTransactions

eveRegistrarPortFromTopology （Int32& registrarPortNumber）

测试-Test-csucwaconference：没有分配的测试用户

\[LyncTest.SelfHost.Corp.Microsoft.com\]。 验证测试用户配置。

位于第1行：1个字符：1

\+Test-csucwaconference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo： ResourceUnavailable：（:)\[Test-test-csucwaconference\]

，InvalidOperationException

\+FullyQualifiedErrorId： NotFoundTestUsers、

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是**测试 CsReplica**可能失败的一些常见原因：

  - 副本复制器代理和集中日志记录代理服务可能存在更大的问题

  - 可能未在 Windows 防火墙中打开所需的端口

  - 必需的 Active Directory 和本地计算机安全组可能不存在

</div>

</div>

<span> </span>

</div>

</div>

</div>

