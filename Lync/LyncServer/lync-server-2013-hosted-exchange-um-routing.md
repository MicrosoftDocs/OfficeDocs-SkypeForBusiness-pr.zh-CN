---
title: Lync Server 2013：托管 Exchange UM 路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31091da9a80dc03c798cbf674c1c46e0ea7b901c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533109"
---
# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Lync Server 2013 中的托管 Exchange UM 路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

Exchange UM 路由应用程序在前端服务器上运行，以将呼叫路由到本地 Microsoft Exchange Server 统一消息 (UM) 部署或托管 Exchange UM 服务。

<div>

## <a name="the-exum-routing-application"></a>ExUM 路由应用程序

Lync Server 2013 Exchange UM 路由应用程序使用用户帐户设置中的信息和托管的语音邮件策略参数来确定如何路由托管语音邮件的呼叫，如下图所示。

**混合部署 Exchange UM 路由示例**

![本地 Lync Server Exchange UM 部署](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "本地 Lync Server Exchange UM 部署")

可以将 Exchange UM 路由配置为将呼叫路由到启用了本地 Exchange UM 的用户、已启用托管 Exchange UM 的用户或两者的组合。

例如，假设 Roy 的邮箱和 Exchange UM 服务托管在本地 Exchange 部署中。

  - 来自 Roy 的用户帐户的代理地址信息提供了 ExUM 路由应用程序用来将他的呼叫路由到内部部署 Exchange UM 服务器的信息。

Alice 的邮箱和 Exchange UM 服务位于托管的 Exchange 服务提供商的数据中心。 Exchange UM 呼叫的路由配置如下：

  - Alice 的用户帐户的 msExchUCVoiceMailSettings 属性中设置的值通知 ExUM 路由应用程序，在托管语音邮件策略中检查路由详细信息。
    
    <div>
    

    > [!NOTE]  
    > MsExchUCVoiceMailSettings 属性的值可由 Exchange 服务提供商或 Lync Server 2013 管理员进行设置。 在上图所示的示例中，CsHostedVoiceMail = 1)  (的值由 Lync Server 2013 管理员设置为为 Alice 启用托管语音邮件。 有关此属性的详细信息，请参阅 <A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013 中的托管 Exchange 用户管理</A>。

    
    </div>

  - 分配给 Alice 的用户帐户的托管语音邮件策略提供了路由详细信息：
    
      - 目标是托管 Exchange UM 服务提供商 (ls。ExUm。 \<hostedExchangeServer\>com 在此示例中) 。
    
      - 组织由租户 Id 标识，这些 Id 是位于 ls 上的 Exchange Server 租户的 SIP 消息的路由 Fqdn。ExUm。 \<hostedExchangeServer\>com (corp.contoso.com 和 corp.litwareinc.com 在此示例中) 。
        
        <div>
        

        > [!NOTE]  
        > Exchange Online 的 FQDN 为 exap.um.outlook.com。

        
        </div>
        
        有关详细信息，请参阅 [Lync Server 2013 中的托管语音邮件策略](lync-server-2013-hosted-voice-mail-policies.md)。

<div>


> [!NOTE]  
> 如果用户帐户中同时存在 msExchUCVoiceMailSettings 属性和 UM 代理地址设置，则优先使用 msExchUCVoiceMailSettings 属性。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

