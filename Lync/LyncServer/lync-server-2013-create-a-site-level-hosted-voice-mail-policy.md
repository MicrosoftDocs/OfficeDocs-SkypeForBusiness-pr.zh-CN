---
title: Lync Server 2013：创建网站级别托管的语音邮件策略
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
ms.openlocfilehash: e23f14b1db7c846d5dbaa0aa6861274a7b6a2611
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501879"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中创建网站级别托管的语音邮件策略

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-24_

*站点* 策略可以影响在为其定义策略的站点上承载的所有用户。如果已为用户配置托管 Exchange UM 访问且未向用户分配每用户策略，则将应用站点策略。如果尚未部署站点策略，则将应用全局策略。

有关配置网站策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - [新 CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>创建站点托管语音邮件策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行 New-CsHostedVoicemailPolicy cmdlet 创建策略。例如，运行：
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    本示例创建 site 作用域的托管语音邮件策略，并设置以下参数：
    
      - **Identity** 为策略指定唯一标识符，其中包含作用域。 对于具有站点范围的策略，必须使用格式 `site:` *\<name\>* （例如，）指定 Identity 参数值 `site:Redmond` 。
    
      - **Destination** 指定托管 Exchange UM 服务的完全限定域名 (FQDN)。此参数为可选参数，但如果尝试为用户启用托管语音邮件，而用户的已分配策略没有 Destination 值，则无法启用。
    
      - **Description** 提供有关策略的可选描述性信息。
    
      - **组织** 指定 Home Lync Server 2013 用户的 Exchange 租户的逗号分隔列表。 必须将每个租户指定为托管 Exchange UM 服务上租户的 FQDN。

</div>

</div>

<span> </span>

</div>

</div>

</div>

