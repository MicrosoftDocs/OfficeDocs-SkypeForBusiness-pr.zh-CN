---
title: Lync Server 2013：创建网站级托管语音邮件策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aeae2e533bd62cf1f3e24e7ceff69b870ebc7b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中创建网站级托管语音邮件策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-24_

*网站*策略可能会影响托管在定义了该策略的网站上的所有用户。 如果用户已配置为托管 Exchange UM 访问，并且尚未分配每用户策略，则应用网站策略。 如果尚未部署网站策略，则应用全局策略。

有关配置网站策略的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：

  - [新-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>创建网站托管语音邮件策略

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  运行 CsHostedVoicemailPolicy cmdlet 以创建策略。 例如，运行：
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    此示例创建一个具有网站范围的托管语音邮件策略，并设置以下参数：
    
      - **标识**指定策略的唯一标识符，其中包括范围。 对于具有网站范围的策略，必须在格式`site:` * \<名称\>* 中指定 Identity 参数值，例如。 `site:Redmond`
    
      - **Destination**指定托管 Exchange UM 服务的完全限定的域名（FQDN）。 此参数是可选的，但如果你尝试为托管语音邮件启用用户，并且用户分配的策略没有目标值，则 enable 将失败。
    
      - **说明**提供有关策略的可选描述性信息。
    
      - **组织**指定用于家庭 Lync Server 2013 用户的 Exchange 租户的逗号分隔列表。 必须在托管 Exchange UM 服务上将每个租户指定为该租户的 FQDN。

</div>

</div>

<span> </span>

</div>

</div>

</div>

