---
title: Lync Server 2013：为托管 Exchange UM 创建联系人对象
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c783a79c6d3ed3cd0af47d53d136a47585cb94d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>在 Lync Server 2013 中为托管 Exchange UM 创建联系人对象

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-24_

以下过程介绍如何为托管 Exchange 统一消息 (UM) 创建自动助理 (AA) 或订阅者访问 (SA) 联系人对象。

有关详细信息，请参阅规划文档中的在[Lync Server 2013 中托管 Exchange 联系人对象管理](lync-server-2013-hosted-exchange-contact-object-management.md)。

有关配置 contact 对象的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - [新 CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> 在 Lync Server 2013 中可以为托管 Exchange UM 启用联系人对象之前，必须部署适用于这些对象的托管语音邮件策略。 有关详细信息，请参阅<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</A>。



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>为托管 Exchange UM 创建 AA 或 SA 联系人对象

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行 New-CsExUmContact cmdlet 创建部署所需的任何联系人对象。例如，运行以下命令创建 AA 和 SA 联系人对象：
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    这些示例设置了以下参数：
    
      - **SipAddress** 指定联系人对象的 SIP 地址。 该地址必须是尚未在 Active Directory 域服务中用于配置用户或联系人对象的地址。 此值必须采用 "sip：\<*sip 地址*\>" 的格式，如前面的示例中所示。
    
      - **RegistrarPool** 指定运行 Registrar 服务的池的完全限定域名 (FQDN)。
        
        <div class=" ">
        

        > [!NOTE]  
        > 在 Lync Server 2013 之前，不能将 Exchange UM 联系人对象移到作为 Lync Server 2013 部署一部分的池。

        
        </div>
    
      - **OU** 指定此联系人对象将位于的 Active Directory 组织单位。
    
      - **DisplayNumber** 指定联系人对象的电话号码。每个联系人对象的电话号码必须是唯一的。
    
      - **AutoAttendant** 指定联系人对象是否为自动助理。自动助理提供了一组语音提示，允许呼叫者导航电话系统并最终到达他们要联系的一方。为此参数指定 **False** 值（默认值）指示对象为订阅者访问联系人对象。

</div>

</div>

<span> </span>

</div>

</div>

</div>

