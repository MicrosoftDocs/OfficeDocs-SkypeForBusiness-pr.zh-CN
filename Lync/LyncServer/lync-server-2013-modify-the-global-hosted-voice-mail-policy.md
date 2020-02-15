---
title: Lync Server 2013：修改全局托管的语音邮件策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1746f622afb380f53a0109400a7d326b0b3c5de7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中修改全局托管语音邮件策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-24_

*全局*托管的语音邮件策略随 Lync Server 2013 一起安装。 可以根据需要修改该策略，但不能重命名或删除它。 若要修改全局策略，您可以针对特定的部署使用 Set-CsHostedVoicemailPolicy cmdlet 将参数设置为相应的值。

有关[CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>修改全局托管语音邮件策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行 Set-CsHostedVoicemailPolicy cmdlet，为您的环境设置全局策略参数。 例如，运行：
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    由于此命令不指定策略的 Identity 参数，因此 Windows PowerShell 命令行界面将在全局托管的语音邮件策略上设置以下值：
    
      - **Destination** 指定托管 Exchange UM 服务的完全限定域名 (FQDN)。此参数为可选参数，但如果尝试为用户启用托管语音邮件，而用户的已分配策略没有 Destination 值，则无法启用。
    
      - **组织**指定家庭 Lync Server 用户的 Exchange 租户的逗号分隔列表。 必须将每个租户指定为托管 Exchange UM 服务上租户的 FQDN。
    
    <div>
    

    > [!NOTE]  
    > 在前面的示例 cmdlet 中，“corp1.litwareinc.com”值替代可能已经显示在 Organization 参数中的任何值。例如，如果策略已包含以逗号分隔的组织列表，则会替换整个列表。如果要向列表中添加组织，而不是替换整个列表，可运行类似如下的命令。

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

