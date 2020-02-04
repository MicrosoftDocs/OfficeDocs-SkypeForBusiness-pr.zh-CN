---
title: Lync Server 2013：规划响应组灾难恢复
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
ms.openlocfilehash: db3a196a258198fe0bc65b533841544decd96aa2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中规划响应组灾难恢复

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

本部分介绍了一些为灾难恢复准备响应组的方法，并提供了灾难恢复过程的概述。

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>准备响应组灾难恢复

在准备和执行灾难恢复过程时，请牢记以下事项。

<div>


> [!NOTE]  
> 在共存环境中，本文档中所述的灾难恢复过程仅支持 Lync Server 2013 响应组。



</div>

  - 在执行容量规划时规划灾难恢复。 对于灾难恢复容量，配对池中的每个池都应该能够处理两个池中所有响应组的工作负荷。 有关响应组容量规划的详细信息，请参阅[Lync Server 2013 中的 "响应" 组的容量规划](lync-server-2013-capacity-planning-for-response-group.md)。

  - 通过使用本文档中所述的 export 过程，对部署了响应组应用程序的所有前端池中的所有响应组配置定期制作备份副本。 有关详细信息，请参阅[Lync Server 2013 中的响应组灾难恢复过程](lync-server-2013-response-group-disaster-recovery-procedures.md)。 将备份副本保存在安全的位置。

  - 为您用于响应组应用程序的所有原始音频文件保留一个单独的备份副本，包括所有录制和包含音乐的文件。 将备份文件保留在安全的位置。

  - 对于 Lync Server 2013 灾难恢复，所有响应组设置在你的部署中必须具有唯一的名称。 此要求适用于工作流、队列、代理组、假日集和工作时间。 当主池和备份池仍处于活动状态时，以及在你需要启动任何故障转移过程之前，应验证是否满足此要求。 如果在将响应组数据导入到备份池时遇到名称冲突，则导入失败。 若要完成导入和故障转移过程，你需要通过在备份池中重命名响应组对象来解决名称冲突，或者通过将**CsRgsConfiguration** cmdlet 与-ResolveNameConflicts 参数一起使用，通过将唯一的识别号附加到响应组对象来自动解决冲突。

  - 一般情况下，我们建议你执行每日备份，但如果你有大量更改，你可能希望计划更频繁的备份。 灾难发生时可能会丢失的信息量取决于备份的频率，以及更改的频率和数量。

  - 在发生灾难或故障转移操作之前，可以将响应组导入到备份池。 快速导入响应组会减少停机时间，因为一旦呼叫路由到备份池，就可以在备份池中还原 Lync Server 响应组服务。
    
    <div>
    

    > [!NOTE]  
    > 在故障转移完成之前，响应组应用程序无法访问驻留在非活动池中的任何代理。 在这段时间内，响应组应用程序处理的调用如同这些代理不可用。

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>响应组灾难恢复过程

发生灾难时，您可以使用以下任一恢复方法恢复响应组：

  - 故障转移到备份池，然后故障回复到原始池。

  - 故障转移到备份池，使用不同的完全限定的域名（FQDN）创建新池，然后将响应组导入新池。

在灾难恢复的故障转移阶段，响应组位于多个池中：在主池（不可用）和备份池中。 两个池中的响应组具有相同的名称和相同的所有者（主池），但它们具有不同的父池。

通过使用不同的 FQDN 创建新池进行恢复时，你需要在导入时将新的池分配为响应组的所有者。 除非使用-OverwriteOwner 参数和**CsRgsConfiguration** cmdlet 显式重新分配所有权，否则响应组的所有权将保留原始池。

<div>


> [!NOTE]  
> 如果你在恢复期间（即，"响应组" 数据库为空），则你还需要使用– OverwriteOwner 参数，无论你是否使用相同的 FQDN。 如果未重新生成池，则无需使用– OverwriteOwner 参数，但可以在将响应组重新导入到主池时使用此参数。



</div>

每个池只能定义一组应用程序级响应组配置设置。 这些设置包括默认的音乐保留配置、默认的音乐保留音频文件、代理 ringback 宽限期和呼叫上下文配置。 若要查看这些配置设置，请运行**CsRgsConfiguration** cmdlet。 有关**CsRgsConfiguration** cmdlet 的详细信息，请参阅[CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)。

你可以通过使用**CsRgsConfiguration** cmdlet 和-ReplaceExistingSettings 参数将这些应用程序级别的设置从一个池中转移到另一个池中，但这样做会覆盖目标池中的设置。

<div>


> [!IMPORTANT]  
> 有关将设置转移到另一个池的此约束条件仅适用于应用程序级设置和默认的音乐保留音频文件。 不适用于代理组、队列、工作流、营业时间和假日集。



</div>

如果你不希望在灾难期间替换备份池中的应用程序级设置，并且无法恢复主池，则会丢失主池中的应用程序级别设置。 如果在恢复期间需要创建新池来替换主池，使用相同的 FQDN 或不同的 FQDN，则不能恢复原始的应用程序级设置。 在这种情况下，你需要配置具有这些设置的新池，并包括 "音乐保留" 音频文件。

如果你决定使用**CsRgsConfiguration** cmdlet 在灾难期间将应用程序级别的主池中的应用程序级别设置转移到备份池，则可以在恢复期间将备份池中的设置转移到新池，方法与将它们从主池转移到备份池的方式相同。

下表概述了恢复响应组所涉及的步骤。

有关执行这些步骤的详细信息，请参阅[Lync Server 2013 中的响应组灾难恢复过程](lync-server-2013-response-group-disaster-recovery-procedures.md)。

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
<td><p>停机前</p></td>
<td><p>定期运行<strong>CsRgsConfiguration</strong> cmdlet，以在部署响应组应用程序的所有前端池内创建所有响应组配置的备份。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>停机期间</p></td>
<td><p>运行<strong>CsRgsConfiguration</strong> cmdlet 以将备份的 Lync Server 响应组服务配置从主池中导入到备份池。</p>
<div>

> [!NOTE]  
> 如果要使用主池中的设置替换备份池中的应用程序级响应组设置，请使用– ReplaceExistingSettings 参数。 如果不将应用程序级别的设置从主池转移到备份池，并且无法恢复主池，则将丢失主池中的设置。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>导入后</p></td>
<td><p>通过-ShowAll 参数（用于显示所有响应组）或– Owner 参数（用于显示 "仅导入的响应组"）运行响应组 cmdlet，验证是否已将所有响应组配置导入到备份池中。</p>
<div>

> [!IMPORTANT]  
> 如果您不使用– ShowAll 参数或-Owner 参数，则导入到备份池中的响应组将不会在 cmdlet 返回的结果中列出。


</div>
<p>运行以下 cmdlet：</p>
<ul>
<li><p><strong>CsRgsWorkflow</strong></p></li>
<li><p><strong>CsRgsQueue</strong></p></li>
<li><p><strong>CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>CsRgsHolidaySet</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>故障转移后</p></td>
<td><ul>
<li><p>将测试呼叫放置到已导入到备份池中的响应组，并验证是否正确处理了该呼叫。</p></li>
<li><p>所有正式代理必须再次登录到备份池上的正式组。</p></li>
<li><p>管理配置更改：</p>
<p>备份池中的响应组，无论是导入到备份池还是由备份池拥有，都可以在中断期间进行正常修改。</p>
<div>

> [!IMPORTANT]  
> 必须使用 Lync Server Management Shell 管理导入到备份池中的响应组。 当这些响应组位于备份池中时，无法使用 Lync Server "控制面板" 管理这些响应组。


</div></li>
</ul></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>恢复后，在故障回复之前</p></td>
<td><p>运行<strong>CsRgsConfiguration</strong> cmdlet，将-Source 参数指定为备份池，并将– Owner 参数用作主池，以便从备份池中导出主池拥有的响应组。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>故障回复后</p></td>
<td><ul>
<li><p>运行<strong>CsRgsConfiguration</strong> cmdlet 以将响应组导入回主池。</p>
<div>

> [!NOTE]  
> 如果无法恢复主池，并且你部署新池以替换它，请使用-ReplaceExistingSettings 参数将应用程序级别的设置从备份池传输到新池。 如果未从备份池中传输设置，新池将使用默认设置。


</div></li>
<li><p>通过-ShowAll 参数（用于显示所有响应组）或– Owner 参数（仅显示导入的响应组）运行以下 cmdlet，验证是否已将所有响应组配置成功导入到主池：</p>
<ul>
<li><p><strong>CsRgsWorkflow</strong></p></li>
<li><p><strong>CsRgsQueue</strong></p></li>
<li><p><strong>CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>将测试呼叫放入已导入到主池的响应组，并验证是否正确处理了该呼叫。</p></li>
<li><p>（可选）使用-RemoveExportedConfiguration 参数在备份池中运行<strong>Export CsRgsConfiguration</strong> cmdlet，以从备份池中删除主池拥有的响应组。</p></li>
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

