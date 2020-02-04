---
title: Lync Server 2013：配置增强的状态隐私模式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cc68ad4e3200a268a2a6ea901167f211942c015
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>在 Lync Server 2013 中配置增强的联机状态隐私模式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-12-08_

通过 "增强状态隐私" 模式，用户可以限制其状态信息，使其仅对 Lync 2013 联系人列表中列出的联系人可见。 **CsPrivacyConfiguration** 和**CsPrivacyConfiguration** cmdlet 具有 EnablePrivacyMode 参数，该参数控制此选项。 当 EnablePrivacyMode 设置为 True 时，将 "Lync 2013 状态" 选项中的 "限制联系人的状态信息" 选项变为可用。 当 EnablePrivacyMode 设置为 False 时，用户可以选择始终允许所有人查看其状态信息，或遵循管理员对隐私模式所做的任何未来更改。

<div>


> [!IMPORTANT]  
> Lync 2013 和 Lync 2010 隐私设置不会被以前的版本（Microsoft Office Communicator 2007 R2 或 Microsoft Office Communicator 2007）所认可。 如果允许以前版本的 Office Communicator 登录，则 Lync 2013 用户的状态、联系人信息或图片可由未经授权查看的人员查看。 此外，如果用户稍后使用 Communicator 的早期版本登录，则将重置 Lync 2013 用户的隐私设置。<BR>因此，在迁移方案中，在启用 "增强状态隐私模式" 之前，请执行以下操作： 
> <UL>
> <LI>
> <P>确保每位用户安装了 Lync 2013。</P>
> <LI>
> <P>定义客户端版本策略规则以阻止以前版本的 Communicator 登录。</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>启用 "增强状态隐私模式"

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  运行以下命令：
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    此命令将为组织中当前使用的所有隐私配置设置启用隐私模式。 有关 Lync Server 增强状态隐私模式策略配置如何管理 Lync 2013 客户端的联系人状态的详细信息，请参阅 Microsoft 知识库文章[启用 Lync Server 增强状态隐私模式将某些 Lync 联系人的状态更新为 "不可用"](http://support.microsoft.com/kb/3020057)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[新-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

