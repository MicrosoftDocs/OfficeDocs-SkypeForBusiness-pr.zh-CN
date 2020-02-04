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
ms.openlocfilehash: e04198813f7bb0647671dbb23e12889b108ee846
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Lync Server 2013 中的托管 Exchange UM 路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-01_

Exchange UM 路由应用程序在前端服务器上运行，用于将呼叫路由到本地 Microsoft Exchange Server 统一消息（UM）部署或托管 Exchange UM 服务。

<div>

## <a name="the-exum-routing-application"></a>ExUM 路由应用程序

Lync Server 2013 Exchange UM 路由应用程序使用来自用户帐户设置的信息，并使用托管的语音邮件策略参数确定如何路由托管语音消息的呼叫，如下图所示。

**混合部署 Exchange UM 路由的示例**

![本地 Lync Server Exchange UM 部署](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "本地 Lync Server Exchange UM 部署")

Exchange UM 路由可以配置为将呼叫路由到已启用本地 Exchange UM 的用户，或者连接到已启用托管 Exchange UM 的用户或两者的组合。

例如，假设 Roy 的邮箱和 Exchange UM 服务托管在本地 Exchange 部署中。

  - Roy 的用户帐户中的代理地址信息提供 ExUM 路由应用程序用于将其调用路由到本地 Exchange UM 服务器的信息。

Alice 的邮箱和 Exchange UM 服务位于托管 Exchange 服务提供商的数据中心。 按如下方式配置 Exchange UM 呼叫的路由：

  - 在刘爱琳的用户帐户的 msExchUCVoiceMailSettings 属性中设置的值指示 ExUM 路由应用程序在托管语音邮件策略中检查路由详细信息。
    
    <div>
    

    > [!NOTE]  
    > MsExchUCVoiceMailSettings 属性的值可以由 Exchange 服务提供商或 Lync Server 2013 管理员进行设置。 在上图所示的示例中，此值（CsHostedVoiceMail = 1）是由 Lync Server 2013 管理员设置的，用于为刘爱琳启用托管语音邮件。 有关此属性的详细信息，请参阅<A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013 中的 "托管 Exchange 用户管理"</A>。

    
    </div>

  - 分配给刘爱琳的用户帐户的托管语音邮件策略提供路由详细信息：
    
      - 目标是托管 Exchange UM 服务提供商（ls）。ExUm.\<此\>示例中的 hostedExchangeServer）。
    
      - 组织由租户 Id 标识，这些 Id 是位于 ls 上的 Exchange Server 租户的 SIP 消息的路由 Fqdn。ExUm.\<hostedExchangeServer\>（此示例中为 corp.contoso.com 和 corp.litwareinc.com）。
        
        <div>
        

        > [!NOTE]  
        > Exchange Online 的 FQDN 为 exap.um.outlook.com。

        
        </div>
        
        有关详细信息，请参阅[Lync Server 2013 中的托管语音邮件策略](lync-server-2013-hosted-voice-mail-policies.md)。

<div>


> [!NOTE]  
> 如果用户帐户中同时存在 msExchUCVoiceMailSettings 属性和 UM 代理地址设置，则 msExchUCVoiceMailSettings 属性优先。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

