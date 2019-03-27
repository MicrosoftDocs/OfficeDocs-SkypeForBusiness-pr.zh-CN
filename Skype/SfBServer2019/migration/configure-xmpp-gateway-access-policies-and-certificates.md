---
title: 配置 XMPP 网关访问策略和证书
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: XMPP 联盟定义基于可扩展消息和状态协议 (XMPP) 外部部署。 XMPP 配置允许用户通过 XMPP 域用户访问：
ms.openlocfilehash: 65ef8904660eaa75ddd10238a6561ea91b9f7278
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889971"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>配置 XMPP 网关访问策略和证书

XMPP 联盟定义基于可扩展消息和状态协议 (XMPP) 外部部署。 XMPP 配置允许用户通过 XMPP 域用户访问：
  
- IM 和状态-仅限于面对面
    
- 创建 XMPP 联盟中的商业客户端 Skype 联系人
    
在配置策略支持 XMPP 联盟伙伴、 的策略应用于 XMPP 联盟域用户，但不是向用户的会话初始协议 (SIP) 即时消息 (IM) 服务提供程序或 SIP 联盟域。 配置您想要让用户添加联系人并与之通信的每个 XMPP 联盟域 XMPP 联盟的伙伴。 位置策略后，您需要配置 XMPP 网关证书。 
  
> [!NOTE]
> XMPP 功能在 Skype 中的业务服务器 2019年已弃用，但可以继续使用在旧服务器以与 Skype 的业务服务器 2019年的共存。 请确保您已经部署了旧服务器 (业务服务器 2015年的 Skype / Lync Server 2013) XMPP 网关，并配置用户启用旧的 XMPP 网关访问策略。 有关详细信息，请参阅[迁移 XMPP 联盟](migrating-xmpp-federation.md)。 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>旧的 XMPP 网关配置为启用用户外部访问策略

1. 打开业务 Server Control Panel 旧 Skype。
    
2. 在左侧的导航栏中，单击**联盟和外部访问**，然后单击**外部访问策略**。
    
3. 单击“**新建**”，然后单击“**用户策略**”。
    
4. 输入外部访问用户策略的名称。
    
5. 提供外部访问用户策略的说明。
    
6. 选择**启用与联盟用户的通信**。
    
7. 选择**启用与 XMPP 联盟通信用户**。
    
8. 单击**提交**以保存对站点或用户策略所做的更改。 
    

