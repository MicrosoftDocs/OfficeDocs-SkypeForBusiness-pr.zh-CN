---
title: 配置与会页面
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07c3797f62fb1d6b7df0274d26fb1ddde706a66a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a>配置与会页面

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-12-14_

当用户单击会议请求中的会议链接时, 会议加入页面检测是否已在用户的计算机上安装了 Lync 2013 客户端。 如果已安装客户端, 该客户端将打开并加入会议。 如果未安装客户端, 则默认情况下将打开2013版本的 Microsoft Lync Web 应用。

如果您希望允许用户通过 Office Communicator 2007 R2 或 Lync 2010 助理加入会议, 则可以修改会议加入页面的行为。 这些配置选项已从 Lync Server 2013 控制面板中删除, 但你通过使用 CsWebServiceConfiguration cmdlet 进行配置。

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a>会议加入页 CsWebServiceConfiguration 参数

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>CsWebServiceConfiguration 参数</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>如果设置为 True, 则通过使用 Lync 之外的客户端应用程序加入会议的用户将有机会通过使用 Office Communicator 2007 R2 加入会议。 默认值为 False。</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>当设置为 True 时, 用于加入联机会议的备用选项 (如 Office Communicator 2007 R2) 将自动展开并向用户显示。 当设置为 False (默认值) 时, 这些选项将可用, 但用户将必须显示其自身的选项列表。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>使用 Lync Server 2013 命令行管理程序配置会议加入页面

1.  启动 Lync Server 2013 命令行管理程序: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server Management Shell**"。

2.  运行以下 cmdlet：
    
        Get-CsWebServiceConfiguration
    
    此 cmdlet 返回 web 服务配置设置。

3.  运行以下命令, 将参数设置为 True 或 False, 具体取决于你的首选项 (有关此 cmdlet 的参数的详细信息, 请参阅 Lync Server 2013 管理外壳文档):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

