---
title: Lync Server 2013：托管 Exchange UM 路由
TOCTitle: 托管 Exchange UM 路由
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398512(v=OCS.15)
ms:contentKeyID: 49313157
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的托管 Exchange UM 路由

 

_**上一次修改主题：** 2012-10-01_

Exchange UM 路由应用程序在 前端服务器上运行，以将呼叫路由到本地 Microsoft Exchange Server 统一消息 (UM) 部署或托管 Exchange UM 服务。

## ExUM 路由应用程序

Lync Server 2013Exchange UM 路由应用程序使用用户帐户设置和托管语音邮件策略参数中的信息来确定如何为托管语音消息路由呼叫，如下图所示。

**混合部署 Exchange UM 路由示例**

![内部 Lync Server Exchange UM 部署](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "内部 Lync Server Exchange UM 部署")

Exchange UM 路由可配置为将呼叫路由到已为其启用本地 Exchange UM 的用户和/或已为其启用托管 Exchange UM 的用户。

例如，假设 Roy 的邮箱和 Exchange UM 服务位于一个本地 Exchange 部署中。

  - Roy 的用户帐户的代理地址信息提供了 ExUM 路由应用程序用于将其呼叫路由至本地 Exchange UM 服务器的信息。

Alice 的邮箱和 Exchange UM 服务位于某个托管 Exchange 服务提供商的数据中心内。她的 Exchange UM 呼叫的路由配置如下：

  - Alice 的用户帐户的 msExchUCVoiceMailSettings 属性中设置的值通知 ExUM 路由应用程序，在托管语音邮件策略中检查路由详细信息。
    
    > [!NOTE]  
    > msExchUCVoiceMailSettings 属性的值可以由 Exchange 服务提供商或 Lync Server 2013 管理员进行设置。在上图显示的示例中，值 (CsHostedVoiceMail=1) 由 Lync Server 2013 管理员设置，以便为 Alice 启用托管语音邮件。有关此属性的详细信息，请参阅 <a href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013 中的托管 Exchange 用户管理</a>。
    


  - 分配给 Alice 的用户帐户的托管语音邮件策略提供了路由详细信息：
    
      - 目标是托管 Exchange UM 服务提供商（此示例中为 ls.ExUm.*\<hostedExchangeServer\>*.com）。
    
      - 组织由租户 ID 进行标识，租户 ID 是位于 ls.ExUm.*\<hostedExchangeServer\>*.com 上 Exchange Server 租户的 SIP 消息的路由 FQDN（本例中为 corp.contoso.com 和 corp.litwareinc.com）。
        
        > [!NOTE]  
		> Exchange Online 的 FQDN 为 exap.um.outlook.com。
        
        
        有关详细信息，请参阅 [Lync Server 2013 中的托管语音邮件策略](lync-server-2013-hosted-voice-mail-policies.md)。

> [!NOTE]  
> 如果用户帐户中同时存在 msExchUCVoiceMailSettings 属性和 UM 代理地址设置，则优先使用 msExchUCVoiceMailSettings 属性。


