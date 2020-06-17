---
title: 配置 XMPP 网关访问策略和证书
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: XMPP 联盟可根据可扩展消息传递和状态协议 (XMPP) 定义外部部署。 通过 XMPP 配置，用户可以通过以下方式访问 XMPP 域用户：
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753932"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>配置 XMPP 网关访问策略和证书

XMPP 联盟可根据可扩展消息传递和状态协议 (XMPP) 定义外部部署。 通过 XMPP 配置，用户可以通过以下方式访问 XMPP 域用户：
  
- 即时消息和状态-仅限人员
    
- 在 Skype for Business 客户端中创建 XMPP 联盟联系人
    
为支持 XMPP 联盟伙伴配置策略时，这些策略适用于 XMPP 联盟域的用户，但不适用于会话初始协议（SIP）即时消息（IM）服务提供商或 SIP 联盟域的用户。 为您希望允许用户添加联系人并与之通信的每个 XMPP 联盟域配置 XMPP 联盟伙伴。 在制定好这些策略之后，您需要配置 XMPP 网关证书。 
  
> [!NOTE]
> XMPP 功能在 Skype for business Server 2019 中已弃用，但可在与 Skype for business Server 2019 共存的旧服务器中继续进行。 确保已部署旧版服务器（Skype for Business Server 2015/Lync Server 2013） XMPP 网关，并已将访问策略配置为为用户启用旧版 XMPP 网关。 有关详细信息，请参阅[迁移 XMPP 联合](migrating-xmpp-federation.md)。 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>配置外部访问策略以为用户启用旧版 XMPP 网关

1. 打开旧版 Skype for Business Server 控制面板。
    
2. 在左侧导航栏中，单击“联盟和外部访问”****，然后单击“外部访问策略”****。
    
3. 单击 **“新建”**，然后单击 **“用户策略”**。
    
4. 输入外部访问用户策略的名称。
    
5. 提供外部访问用户策略的说明。
    
6. 选中“启用与联盟用户的通信”****。
    
7. 选中“启用与 XMPP 联盟用户的通信”****。
    
8. 单击“提交”**** 保存对站点或用户策略的更改。 
    

