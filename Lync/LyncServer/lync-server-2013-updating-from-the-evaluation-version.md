---
title: 'Lync Server 2013: 从评估版本更新'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b00fed276229cbaf0e960e28e622e490fb0bfbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>从 Lync Server 2013 的评估版本更新

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-06-20_

如果已安装 Microsoft Lync Server 2013 的评估版本, 则最终需要更新该安装软件的许可副本;这是因为评估版本在安装后将在180天内过期。 但是, 你无需完全卸载评估版本, 然后安装许可的版本。 在获取有效的授权密钥之后, 你可以通过在充当 Lync Server 前端服务器、Director 或 Edge 服务器的每台计算机上执行以下过程来更新 Lync Server 2013 的评估版本。 请注意, 您不必更新执行其他服务器角色 (如监视服务器或存档服务器) 的计算机。

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>从 Microsoft Lync Server 2013 的评估版本更新

要将计算机从 Lync Server 2013 的评估版本更新到软件的许可版本, 请执行以下操作:

**从 Microsoft Lync Server 2013 的评估版本更新**

1.  以本地管理员身份登录到计算机。

2.  单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server Management Shell**"。

3.  在 Lync Server 命令行管理器中, 键入以下命令, 然后按 ENTER:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    请注意, 你可能需要指定文件服务器 .msi 的完整路径。 此文件可在 Lync Server 卷媒体安装文件的 "设置" 文件夹中找到。

4.  在安装程序完成运行后, 在命令提示符处键入以下内容, 然后按 ENTER:
    
        Enable-CsComputer

5.  在运行 Lync Server 评估副本的任何其他前端服务器、控制器或边缘服务器上重复此过程。 还应在使用 Lync Server media 安装文件部署的任何分支机构服务器上执行此过程。

如果你不确定 Lync Server 的评估版本是否在给定计算机上运行, 你可以通过在 Lync Server Management Shell 中运行以下命令来验证该版本:

    Get-CsServerVersion

[CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet 将分析本地计算机并向后报告以下情况之一:

  - 已在计算机上安装 Lync Server 批量许可证密钥, 这意味着无需更新。

  - 已安装 Lync Server 试用版许可证密钥, 这意味着必须更新计算机。

  - 计算机上不需要批量许可证密钥。 仅在前端服务器、控制器和边缘服务器上需要从评估版更新到许可版本。

</div>

</div>

<span> </span>

</div>

</div>

</div>

