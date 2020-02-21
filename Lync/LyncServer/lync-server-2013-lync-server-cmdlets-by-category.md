---
title: Lync Server 2013： Lync Server cmdlet （按类别）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68764952ebfe2a45895e480d923d76a108fdda8e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a>Lync Server 2013 cmdlet （按类别）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2017-09-20_

Microsoft Lync Server 2013 随附了约550个 cmdlet，以允许管理员从命令行管理 Lync Server。 您可以从 Lync Server 命令行管理程序访问 cmdlet。 可通过键入类似如下的命令直接从命令行检索有关某个 cmdlet 的帮助：

    Get-Help New-CsVoicePolicy -Full

上述命令将检索提供的有关 **New-CsVoicePolicy** cmdlet 的所有帮助。 将对 **New-CsVoicePolicy** 的引用替换为要检索其帮助信息的 cmdlet 的名称。

若要检索可用于管理 Microsoft Lync Server 2013 的 cmdlet 的完整列表，请在 Lync Server 命令行管理程序命令提示符处键入以下内容：

    Get-Command * -Module Lync -CommandType cmdlet

如果不确定需要哪些 cmdlet，我们还提供了 cmdlet 的分类列表及其帮助主题。您将发现某些 cmdlet 出现在多个类别中，我们是有意这样划分的，因为这些 cmdlet 可以应用于多个产品领域。类别列表如下：

<div>


> [!NOTE]
> Skype for Business cmdlet reference 已移动到 docs.microsoft.com。 单击下面的链接将转到新的 docs.microsoft.com 页面。 现在，内容是开放的，可用于通过 GitHub 进行社区贡献。 对所做的贡献有兴趣？ 查看存储库中的自述文件：<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

<div>

## <a name="in-this-section"></a>本部分内容


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-user-management-cmdlets.md">Lync Server 2013 中的用户管理 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-voice-application-cmdlets.md">Lync Server 2013 中的语音应用程序 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-client-management-cmdlets.md">Lync Server 2013 中的客户端管理 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Lync Server 2013 中的高级企业语音 cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-im-and-presence-cmdlets.md">Lync Server 2013 中的 IM 和状态 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Lync Server 2013 中的 PSTN 连接 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencing-cmdlets.md">Lync Server 2013 中的会议 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-phones-and-devices-cmdlets.md">Lync Server 2013 中的电话和设备 cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Lync Server 2013 中的基础结构和部署 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Lync Server 2013 中的迁移和共存 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-security-cmdlets.md">Lync Server 2013 中的安全 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server 2013 中的 lync Server 命令行管理程序配置 cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Lync Server 2013 中的服务器角色和服务 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-mobility-cmdlets.md">Lync Server 2013 中的移动性 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-application-management-cmdlets.md">Lync Server 2013 中的应用程序管理 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Lync Server 2013 中的持久聊天服务器 cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Lync Server 2013 中的联盟和外部访问 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-centralized-logging-cmdlets.md">Lync Server 2013 中的集中日志记录 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-enterprise-voice-cmdlets.md">Lync Server 2013 中的企业语音 cmdlet</a></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server PowerShell 博客](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

