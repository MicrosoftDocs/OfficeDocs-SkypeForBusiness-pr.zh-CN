---
title: 'Lync Server 2013: 配置媒体端口范围设置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 300bec82443e1d2929df63a808cbe17c5bd6f9fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>在 Lync Server 2013 中配置媒体端口范围设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-18_

媒体端口范围设置会显著影响客户端性能, 因此应进行配置。 你可以使用 Lync Server 命令行管理程序配置这些设置。

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
<th>Lync Server Management Shell cmdlet</th>
<th>Cmdlet 参数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>指定服务器发送的端口范围是否应由客户端用于媒体和发送信号。 与 subvalues MinMediaPort 和 MaxMediaPort 结合使用。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>指定要用于媒体的起始端口号。 结合 MaxMediaPort 以指定端口的范围。 推荐的最小范围是40端口。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (表示用于客户端媒体的起始端口号)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>指定要用于媒体的最大端口号。 结合 MinMediaPort 以指定端口的范围。 推荐的最小范围是40端口。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (指明客户端介质可用的端口总数; 默认值为 40)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>配置媒体端口范围设置

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  运行以下 cmdlet：
    
        Get-CsConferencingConfiguration
    
    此 cmdlet 返回会议配置设置。

3.  通过要更改的参数和值运行以下 cmdlet (有关此 cmdlet 的参数的详细信息, 请参阅 Lync Server Management Shell 文档):
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > 你可以为特定网站创建其他会议配置设置集。 将<STRONG>CsConferencingConfiguration</STRONG> cmdlet 与网站标识结合使用。 为网站创建新的会议配置设置时, 网站设置优先于全局设置。 有关详细信息, 请参阅 Lync Server Management Shell 文档。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

