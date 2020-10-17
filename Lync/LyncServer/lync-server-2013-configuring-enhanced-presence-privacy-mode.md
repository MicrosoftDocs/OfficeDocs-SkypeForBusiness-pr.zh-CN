---
title: Lync Server 2013：配置增强状态隐私模式
description: Lync Server 2013：配置增强状态隐私模式。
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
ms.openlocfilehash: c8eab347d233c23a9a4becf119dee673d3021dfa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548448"
---
# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>在 Lync Server 2013 中配置增强状态隐私模式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-12-08_

使用增强状态隐私模式，用户可以限制其状态信息，使其仅对 Lync 2013 联系人列表中列出的联系人可见。 **CsPrivacyConfiguration**   和**CsPrivacyConfiguration** cmdlet 具有一个 EnablePrivacyMode 参数，用于控制此选项。 当 EnablePrivacyMode 设置为 True 时，在 Lync 2013 状态选项中，将状态信息限制为联系人的选项将变为可用状态。 当 EnablePrivacyMode 设置为 False 时，用户可以选择始终允许所有人查看其状态信息，或者遵循管理员对隐私模式所做的任何后续更改。

<div>


> [!IMPORTANT]  
> Lync 2013 和 Lync 2010 隐私设置不是由 Microsoft Office Communicator 2007 R2 或 Microsoft Office Communicator 2007)  (的早期版本所接受的。 如果允许早期版本的 Office Communicator 登录，则未被授权查看的 Lync 2013 用户的状态、联系人信息或图片可能会被他人查看。 此外，如果用户稍后使用 Communicator 的早期版本登录，则会重置 Lync 2013 用户的隐私设置。<BR>出于这些原因，在迁移方案中，在启用增强状态隐私模式之前： 
> <UL>
> <LI>
> <P>确保每个用户安装了 Lync 2013。</P>
> <LI>
> <P>定义客户端版本策略规则以阻止以前版本的 Communicator 登录。</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>启用增强状态隐私模式

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行以下命令：
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    此命令将为组织中当前使用的所有隐私配置设置启用隐私模式。 有关 Lync Server 增强状态隐私模式策略配置如何管理 Lync 2013 客户端的联系人状态的详细信息，请参阅 Microsoft 知识库文章 [启用 Lync Server 增强状态隐私模式将某些 Lync 联系人的状态状态更新为 "不可用"](https://support.microsoft.com/kb/3020057)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[新 CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

