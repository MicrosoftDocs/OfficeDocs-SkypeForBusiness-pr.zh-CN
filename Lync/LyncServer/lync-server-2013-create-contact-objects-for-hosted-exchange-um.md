---
title: Lync Server 2013：为托管 Exchange UM 创建联系人对象
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0ce65ed39e67068fcd57aba1177ecb72f553ccf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>在 Lync Server 2013 中为托管 Exchange UM 创建联系人对象

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-24_

以下过程介绍了如何为托管 Exchange 统一消息 (UM) 创建自动助理 (AA) 或订阅者访问 (SA) 联系人对象。

有关详细信息, 请参阅规划文档中[Lync Server 2013 中的托管 Exchange 联系人对象管理](lync-server-2013-hosted-exchange-contact-object-management.md)。

有关配置联系人对象的详细信息, 请参阅以下 cmdlet 的 Lync Server Management Shell 文档:

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> 在 Lync Server 2013 中可以为托管 Exchange UM 启用联系人对象之前, 必须部署适用于它们的托管语音邮件策略。 有关详细信息, 请参阅<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</A>。



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>为托管 Exchange UM 创建 AA 或 SA 联系人对象

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  运行 CsExUmContact cmdlet 以创建你的部署所需的任何联系人对象。 例如, 运行以下内容创建 AA 和 SA 联系人对象:
    
       ```
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    这些示例设置以下参数:
    
      - **SipAddress**指定 contact 对象的 SIP 地址。 这必须是尚未用于配置 Active Directory 域服务中的用户或联系人对象的地址。 此值必须采用 "sip:\<*sip 地址*\>" 格式, 如前面的示例中所示。
    
      - **RegistrarPool**指定运行注册机构服务的池的完全限定的域名 (FQDN)。
        
        <div class=" ">
        

        > [!NOTE]  
        > 在 Lync Server 2013 之前, 无法将 Exchange UM 联系人对象移到属于 Lync Server 2013 部署的池。

        
        </div>
    
      - **OU**指定此联系人对象将位于的 Active Directory 组织单位。
    
      - **DisplayNumber**指定 contact 对象的电话号码。 每个联系人对象的电话号码必须是唯一的。
    
      - 自动**助理**指定联系人对象是否为自动助理。 自动助理提供一组语音提示, 允许呼叫者在电话系统中导航, 并联系他们想要联系的对方。 此参数的值**False** (默认值) 表示订阅者访问联系人对象。

</div>

</div>

<span> </span>

</div>

</div>

</div>

