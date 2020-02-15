---
title: Lync Server 2013：配置会议加入页面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a62ac96688887e9d5ee66f0f0439a73941db3563
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>在 Lync Server 2013 中配置会议加入页

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-12-14_

当用户单击会议请求中的会议链接时，"会议加入" 页将检测用户计算机上是否已安装 Lync 2013 客户端。 如果已安装客户端，则将打开该客户端并加入会议。 如果未安装客户端，则默认情况下会打开2013版本的 Lync Web App。

如果您希望允许用户加入使用 Office Communicator 2007 R2 或 Lync 2010 助理的会议，则可以修改会议加入页面的行为。 这些配置选项已从 Lync Server 2013 控制面板中删除，但你可以使用 CsWebServiceConfiguration cmdlet 对其进行配置。

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>与会页面 Set-CsWebServiceConfiguration 参数

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Set-CsWebServiceConfiguration 参数</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>如果设置为 True，则通过使用 Lync 之外的客户端应用程序加入会议的用户将有机会通过使用 Office Communicator 2007 R2 加入会议。 默认值为 False。</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>设置为 True 时，用于加入联机会议的备用选项（如 Office Communicator 2007 R2）将自动展开并显示给用户。设置为 False（默认值）时，这些选项仍然可用，但用户必须自己操作才能显示选项列表。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>使用 Lync Server 2013 命令行管理程序配置会议加入页

1.  启动 Lync Server 2013 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。

2.  若要查看 Web 服务配置设置，请运行以下 cmdlet：
    
        Get-CsWebServiceConfiguration

3.  运行以下命令，将参数设置为 True 或 False，具体取决于你的首选项（有关此 cmdlet 的参数的详细信息，请参阅 Lync Server 2013 命令行管理程序文档中的[CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) ）：
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a>另请参阅


[CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

