---
title: Lync Server 2013：配置媒体端口范围设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cfde603ace9036ba547ffb0a7ee80c1963ae6cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>在 Lync Server 2013 中配置媒体端口范围设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-18_

媒体端口范围设置可显著影响客户端性能，应对其进行配置。 您可以使用 Lync Server 命令行管理程序配置这些设置。

### <a name="media-port-range-settings"></a>媒体端口范围设置

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>设置</th>
<th>说明</th>
<th>Lync Server 命令行管理程序 cmdlet</th>
<th>Cmdlet 参数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>指定服务器发送的端口范围是否应由客户端用于媒体和信号。与子值 MinMediaPort 和 MaxMediaPort 结合使用。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>指定用于媒体的起始端口号。与 MaxMediaPort 一起指定端口范围。建议的最小范围为 40 个端口。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort（代表用于客户端媒体的起始端口号）</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>指定用于媒体的最高端口号。与 MinMediaPort 一起指定端口范围。建议的最小范围为 40 个端口。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange（指示可用于客户端媒体的端口总数；默认值为 40）</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>配置媒体端口范围设置

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行以下 cmdlet：
    
        Get-CsConferencingConfiguration
    
    此 cmdlet 返回会议配置设置。

3.  使用要更改的参数和值运行以下 cmdlet （有关此 cmdlet 的参数的详细信息，请参阅 Lync Server 命令行管理程序文档）：
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > 可为特定站点创建其他会议配置设置集。 使用具有站点标识的 <STRONG>New-CsConferencingConfiguration</STRONG> cmdlet。 在为站点创建新的会议配置设置时，站点设置优先于全局设置。 有关详细信息，请参阅 Lync Server 命令行管理程序文档。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

