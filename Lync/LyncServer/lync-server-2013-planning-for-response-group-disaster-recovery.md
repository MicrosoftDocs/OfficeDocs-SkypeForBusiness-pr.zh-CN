---
title: Lync Server 2013：规划响应组灾难恢复
description: Lync Server 2013：规划响应组灾难恢复。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5294ddf7dbd42d95c5eb17acd6be6a5abc7a5917
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549258"
---
# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中规划响应组灾难恢复

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

本节介绍准备对响应组进行灾难恢复的一些方法，并提供灾难恢复过程的概述。

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>为响应组灾难恢复做准备

在准备和执行灾难恢复过程时，请谨记以下做法。

<div>


> [!NOTE]  
> 在共存环境中，本文档中所述的灾难恢复过程仅支持 Lync Server 2013 响应组。



</div>

  - 在进行容量规划时，应制定灾难恢复计划。 对于灾难恢复容量，配对池中的每个池应能够处理两个池中所有响应组的工作负荷。 有关响应组容量规划的详细信息，请参阅 [Lync Server 2013 中的容量规划（针对响应组](lync-server-2013-capacity-planning-for-response-group.md)）。

  - 使用本文档中所述的 export 过程，对部署了响应组应用程序的所有前端池中的所有响应组配置执行常规备份副本。 有关详细信息，请参阅 [Lync Server 2013 中的响应组灾难恢复过程](lync-server-2013-response-group-disaster-recovery-procedures.md)。 请将备份副本保存到安全的位置。

  - 为响应组应用程序保留您使用的所有原始音频文件的单独备份副本，包括任何录制和包含音乐的文件。 请将备份文件保存到安全的位置。

  - 对于 Lync Server 2013 灾难恢复，所有响应组设置必须在您的部署中具有唯一的名称。 此要求适用于工作流、队列、代理组、假日集和工作时间。 在主池和备份池仍处于活动状态时，并且在您需要启动任何故障转移过程之前，您应该确认是否符合此要求。 如果在将响应组数据导入备份池时遇到名称冲突，导入将失败。 若要完成导入和故障转移过程，您需要解决名称冲突，具体方法是在备份池中重命名响应组对象，或将 **Import-CsRgsConfiguration** cmdlet 与 –ResolveNameConflicts 参数结合使用，以通过向响应组对象附加唯一的标识号来自动解决冲突。

  - 通常，建议您执行日常备份，但如果您要进行大量更改，那么您可能希望安排更为频繁的备份。您在发生灾难期间可能丢失的信息量取决于您的备份频率，以及更改频率和更改量。

  - 可以在发生灾难或执行故障转移操作之前，先将响应组导入备份池。 提前导入响应组会减少停机时间，因为一旦将呼叫路由到备份池，就可以在备份池中还原 Lync Server 响应组服务。
    
    <div>
    

    > [!NOTE]  
    > 在故障转移完成之前，响应组应用程序无法访问驻留在非活动池中的任何代理。 在这段时间内，响应组应用程序将像这些代理不可用那样处理调用。

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>响应组灾难恢复过程

发生灾难时，可以使用以下任一恢复方法恢复响应组：

  - 故障转移至备份池，然后再故障转移回原始池。

  - 故障转移至备份池，用不同的完全限定域名 (FQDN) 创建新池，然后将响应组导入新池。

在灾难恢复的故障转移阶段，响应组驻留在多个池中：在主池（不可用）和备份池中。响应组在两个池中具有相同的名称和相同的所有者（主池），但具有不同的父级。

在通过创建具有不同 FQDN 的新池来恢复时，需要在导入响应组时将该新池指定为响应组的所有者。 除非或直到您结合使用 –OverwriteOwner 参数和 **Import-CsRgsConfiguration** cmdlet 来明确重新分配所有权，响应组的所有权将一直属于原始池。

<div>


> [!NOTE]  
> 如果在恢复 (期间重建了池，也需要使用– OverwriteOwner 参数，即响应组数据库为空) ，无论您是否使用相同的 FQDN。 如果不重建池，则无需使用 –OverwriteOwner 参数，但在将响应组导入回主池时，允许使用此参数。



</div>

您只能为每个池定义一组应用程序级响应组配置设置。 这些设置包括默认的保持音乐配置、默认的保持音乐音频文件、代理回响宽限期和调用上下文配置。 若要查看这些配置设置，请运行 **Get-CsRgsConfiguration** cmdlet。 有关 **CsRgsConfiguration** cmdlet 的详细信息，请参阅 [CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)。

通过将 **Import-CsRgsConfiguration** cmdlet 与 –ReplaceExistingSettings 参数结合使用可将这些应用程序级别的设置从一个池传送至其他池，但这样做会覆盖目标池中的设置。

<div>


> [!IMPORTANT]  
> 有关向其他池传送设置的这一约束仅适用于应用程序级别设置和默认的保持音乐音频文件。它不适用于代理组、队列、工作流、工作时间和假日集。



</div>

如果不想在灾难期间替换备份池中的应用程序级别设置并且主池无法恢复，则主池中的应用程序级别设置将丢失。如果在恢复期间需要创建新池来替换主池（具有同一 FQDN 或不同 FQDN），则无法恢复原始的应用程序级别设置。在此情况下，需要用这些设置配置新池并包括保持音乐音频文件。

如果决定在灾难期间使用 **Import-CsRgsConfiguration** cmdlet 来将应用程序级别的设置从主池传送至备份池，然后在恢复期间便可采用从主池向备份池传送设置的同样方式将设置从备份池传送至新池。

下表是恢复响应组时所涉及步骤的概述。

有关执行这些步骤的详细信息，请参阅 [Lync Server 2013 中的响应组灾难恢复过程](lync-server-2013-response-group-disaster-recovery-procedures.md)。

### <a name="response-group-disaster-recovery-steps"></a>响应组灾难恢复步骤

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>阶段</th>
<th>步骤</th>
<th>所需的组和角色</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>中断前</p></td>
<td><p>定期运行 <strong>CsRgsConfiguration</strong> cmdlet，以在部署响应组应用程序的所有前端池中创建所有响应组配置的备份。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>中断期间</p></td>
<td><p>运行 <strong>CsRgsConfiguration</strong> cmdlet，将备份的 Lync Server 响应组服务配置从主池导入到备份池。</p>
<div>

> [!NOTE]  
> 如果要将备份池中的应用程序级响应组设置替换为主池的设置，请使用– ReplaceExistingSettings 参数。 如果不从主池向备份池传送应用程序级别的设置，则无法恢复主池，您将丢失主池中的设置。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>导入后</p></td>
<td><p>使用– ShowAll 参数 (运行响应组 cmdlet，以显示所有响应组) 或– Owner 参数 (以仅显示导入的响应组) 以验证是否已将所有响应组配置导入备份池。</p>
<div>

> [!IMPORTANT]  
> 如果不使用 –ShowAll 参数或 –Owner 参数，导入备份池的响应组将不会列在 cmdlet 返回的结果中。


</div>
<p>运行以下 cmdlet：</p>
<ul>
<li><p><strong>CsRgsWorkflow</strong></p></li>
<li><p><strong>CsRgsQueue</strong></p></li>
<li><p><strong>CsRgsAgentGroup</strong></p></li>
<li><p><strong>CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>CsRgsHolidaySet</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>故障转移后</p></td>
<td><ul>
<li><p>对已导入备份池的响应组执行测试呼叫，并确认能够正确处理呼叫。</p></li>
<li><p>所有正式代理必须重新登录到它们在备份池中的正式组。</p></li>
<li><p>管理配置更改：</p>
<p>备份池中的响应组（无论是导入备份池中的还是由备份池所拥有）在出现故障时均可正常修改。</p>
<div>

> [!IMPORTANT]  
> 必须使用 Lync Server 命令行管理程序来管理已导入到备份池中的响应组。 当这些响应组位于备份池中时，不能使用 Lync Server 控制面板管理这些响应组。


</div></li>
</ul></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>恢复后，故障回复前</p></td>
<td><p>运行 <strong>Export-CsRgsConfiguration</strong> cmdlet，将 -Source 参数指定为备份池，而将 –Owner 参数指定为主池，以便从备份池导出由主池所拥有的响应组。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>故障回复后</p></td>
<td><ul>
<li><p>运行 <strong>Import-CsRgsConfiguration</strong> cmdlet 以将响应组导入回主池。</p>
<div>

> [!NOTE]  
> 如果无法恢复主池并且您要部署新池来替换它，可使用 –ReplaceExistingSettings 参数将应用程序级别的设置从备份池传送到新池。如果不从备份池传送设置，新池将使用默认设置。


</div></li>
<li><p>带 –ShowAll 参数（显示所有响应组）或 –Owner 参数（只显示已导入的响应组）运行以下 cmdlet，以确认所有响应组配置均已成功导入回主池：</p>
<ul>
<li><p><strong>CsRgsWorkflow</strong></p></li>
<li><p><strong>CsRgsQueue</strong></p></li>
<li><p><strong>CsRgsAgentGroup</strong></p></li>
<li><p><strong>CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>对导入回主池的响应组执行测试呼叫，并确认能够正确处理该呼叫。</p></li>
<li><p>或者，使用 –RemoveExportedConfiguration 参数对备份池运行 <strong>Export-CsRgsConfiguration</strong> cmdlet 以从备份池中删除主池所拥有的响应组。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

