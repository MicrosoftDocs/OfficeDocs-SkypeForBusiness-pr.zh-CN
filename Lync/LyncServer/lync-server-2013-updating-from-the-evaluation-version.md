---
title: Lync Server 2013：从评估版本更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 703362f34c367d301e7d47e1bdc65f16a497ce88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>从 Lync Server 2013 评估版更新

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-20_

如果已安装 Microsoft Lync Server 2013 评估版，则最终需要更新该安装软件的许可副本;这是因为评估版本在安装后会过期180天。 但是，在安装许可版本之前，您无需完全卸载此评估版本。 相反，在获得有效的许可密钥之后，可以通过在充当 Lync Server 前端服务器、控制器或边缘服务器的每台计算机上执行以下过程来更新 Lync Server 2013 的评估版。 注意，您无需更新担当其他服务器角色（如监控服务器或存档服务器）的计算机。

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>从 Microsoft Lync Server 2013 评估版更新

若要将计算机从 Lync Server 2013 评估版更新到软件的许可版本，请执行以下操作：

**从 Microsoft Lync Server 2013 评估版更新**

1.  以本地管理员身份登录到计算机。

2.  依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。

3.  在 Lync Server 命令行管理程序中，键入以下命令，然后按 ENTER：
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    注意，您可能需要指定文件 server.msi 的完整路径。 此文件可在 Lync Server 卷媒体安装文件的 Setup 文件夹中找到。

4.  安装程序完成运行后，在命令提示符中键入以下内容，然后按 Enter 键：
    
        Enable-CsComputer

5.  在运行 Lync Server 评估版评估副本的任何其他前端服务器、控制器或边缘服务器上重复此过程。 此外，还应在使用 Lync Server media 安装文件部署的任何分支机构服务器上执行此过程。

如果您不确定 Lync Server 的评估版是否在给定计算机上运行，则可以通过在 Lync Server 命令行管理程序中运行以下命令来验证这一点：

    Get-CsServerVersion

[Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet 将分析本地计算机并返回以下内容之一：

  - 已在计算机上安装了 Lync Server 批量许可证密钥，这意味着不需要进行更新。

  - 已安装 Lync Server 评估许可证密钥，这意味着必须更新计算机。

  - 计算机上无需批量许可证密钥。只有在前端服务器、控制器和边缘服务器上才需要从评估版本更新到许可版本。

</div>

</div>

<span> </span>

</div>

</div>

</div>

