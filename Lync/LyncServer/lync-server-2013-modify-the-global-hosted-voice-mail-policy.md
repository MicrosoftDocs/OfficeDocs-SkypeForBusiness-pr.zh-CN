---
title: 'Lync Server 2013: 修改全局托管语音邮件策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4759fd0cfe4f8a4c55905b265c2418354a6a6dae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中修改全局托管语音邮件策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-24_

*全球*托管语音邮件策略与 Lync Server 2013 一起安装。 你可以对其进行修改以满足你的需求, 但不能重命名或删除它。 若要修改全局策略, 请使用 CsHostedVoicemailPolicy cmdlet 将参数设置为特定部署的相应值。

有关[CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet 的详细信息, 请参阅 Lync Server Management Shell 文档。

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>修改全局托管的语音邮件策略

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  运行 CsHostedVoicemailPolicy cmdlet 为你的环境设置全局策略参数。 例如，运行：
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    由于此命令不指定策略的标识参数, 因此 Windows PowerShell 命令行界面将在全局托管语音邮件策略上设置以下值:
    
      - **Destination**指定托管 Exchange UM 服务的完全限定的域名 (FQDN)。 此参数是可选的, 但如果你尝试为托管语音邮件启用用户, 并且用户分配的策略没有目标值, 则 enable 将失败。
    
      - **组织**指定家庭 Lync 服务器用户的 Exchange 租户的逗号分隔列表。 必须在托管 Exchange UM 服务上将每个租户指定为该租户的 FQDN。
    
    <div>
    

    > [!NOTE]  
    > 在前面的 cmdlet 示例中, 值 "corp1.litwareinc.com" 替换可能已存在于组织参数中的任何值。 例如, 如果策略已包含以逗号分隔的组织列表, 则将替换完整列表。 如果要将组织添加到列表, 而不是替换整个列表, 请运行类似如下的命令。

    
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

