---
title: Web 服务设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: 从拓扑生成器内，你可以修改用于内部和外部 web 服务的端口设置。 此外，如果你要部署域名系统（DNS）负载平衡，可以使用拓扑生成器来配置池的完全限定的域名（FQDN），该域名解析为该池中所有服务器的物理 IP 地址。
ms.openlocfilehash: fddcaa00de9b8a8d74e209790b429280901b037c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701337"
---
# <a name="web-services-settings-expander"></a>Web 服务设置扩展器
 
从拓扑生成器内，你可以修改用于内部和外部 web 服务的端口设置。 此外，如果你要部署域名系统（DNS）负载平衡，可以使用拓扑生成器来配置池的完全限定的域名（FQDN），该域名解析为该池中所有服务器的物理 IP 地址。
  
### <a name="editing-web-services-settings"></a>编辑 Web 服务设置

1. 选择相应的 Standard Edition 前端服务器或相应的 Enterprise Edition 前端池，然后单击“**编辑属性**”。
    
2. 在“**编辑属性**”对话框中，单击“**Web 服务**”选项卡。
    
    > [!CAUTION]
    > 如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。 例如，如果你将前端服务器的外部 Web 服务 FQDN 定义为**pool01.contoso.com**，则不能将**Pool01.contoso.com**用于其他前端池或前端服务器。 如果你还部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须是任何其他 Director 或控制器池以及任何前端池或前端服务器的唯一。 如果你决定使用自定义的 FQDN 替代内部 web 服务，则每个 FQDN 都必须与任何其他前端池、Director 或控制器池唯一。
  
3. 如果要编辑 Enterprise Edition 池的属性，则可以选择“**覆盖 FQDN**”。 仅在使用域名系统 (DNS) 负载平衡时，才能选择此选项。 如果正在使用 DNS 负载平衡，请选择“**覆盖 FQDN**”，然后在文本框中键入池的 FQDN，该 FQDN 会解析为该池中所有服务器的物理 IP 地址。 如果没有使用 DNS 负载平衡且没有选择“**覆盖 FQDN**”，则无法更改内部 Web 服务 FQDN。 内部 web 服务 FQDN 是内部用户用于连接到 Skype for Business 服务器的 URL。
    
4. 或者，为“**侦听端口**”和“**已发布端口**”输入新的 HTTP、HTTPS 或 HTTP 和 HTTPS 的值。侦听端口是 Internet 信息服务 (IIS) 用于侦听传入会话初始协议 (SIP) 流量的端口；已发布端口是在负载平衡器或反向代理服务器上配置的端口，同样用于侦听传入 SIP 流量。默认情况下，HTTP 侦听端口和 HTTP 已发布端口均设置为端口 80；对应的 HTTPS 端口均设置为 443。两个 HTTP 已发布端口的默认值为 8080，对应的 HTTPS 端口则设置为 4443。
    
5. 单击“**确定**”。
    
如果修改内部 FQDN 或任何侦听端口分配，则必须在池中的所有服务器上重新运行本地设置才能使那些更改生效。
  

