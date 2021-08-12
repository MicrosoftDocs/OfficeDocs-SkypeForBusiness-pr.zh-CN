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
description: XMPP 联盟可根据可扩展消息传递和状态协议 (XMPP) 定义外部部署。 XMPP 配置允许用户通过：访问 XMPP 域用户：
ms.openlocfilehash: 31d3c2a4b4d16407a30eb755e8b18b3ddf1a1b31c342ed6ff3384bbcef3afbc6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296019"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>配置 XMPP 网关访问策略和证书

XMPP 联盟可根据可扩展消息传递和状态协议 (XMPP) 定义外部部署。 XMPP 配置允许用户通过：访问 XMPP 域用户：
  
- IM 和状态 - 仅个人对个人
    
- 在客户端中创建 XMPP Skype for Business联系人
    
配置支持 XMPP 联盟伙伴的策略时，这些策略适用于 XMPP 联盟域的用户，但不适用于会话初始协议 (SIP) 即时消息 (IM) 服务提供商或 SIP 联盟域的用户。 您可以为希望允许用户添加联系人并进行通信的每个 XMPP 联盟域配置一个 XMPP 联盟伙伴。 在制定好这些策略之后，您需要配置 XMPP 网关证书。 
  
> [!NOTE]
> XMPP 功能在 Skype for Business Server 2019 中已弃用，但可在与 Skype for Business Server 2019 共存的旧服务器中继续使用。 确保已部署旧版服务器 (Skype for Business Server 2015/ Lync Server 2013) XMPP 网关，并配置了访问策略以启用旧 XMPP 网关的用户。 有关详细信息，请参阅 [迁移 XMPP 联盟](migrating-xmpp-federation.md)。 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>配置外部访问策略以为用户启用旧版 XMPP 网关

1. 打开旧版"Skype for Business Server控制面板"。
    
2. 在左侧导航栏中，单击“联盟和外部访问”，然后单击“外部访问策略”。
    
3. 单击 **“新建”**，然后单击 **“用户策略”**。
    
4. 输入外部访问用户策略的名称。
    
5. 提供外部访问用户策略的说明。
    
6. 选中“启用与联盟用户的通信”。
    
7. 选中“启用与 XMPP 联盟用户的通信”。
    
8. 单击“提交”保存对站点或用户策略的更改。 
    

