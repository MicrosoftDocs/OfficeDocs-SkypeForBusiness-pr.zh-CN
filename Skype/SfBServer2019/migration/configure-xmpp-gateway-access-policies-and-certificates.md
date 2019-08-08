---
title: 配置 XMPP 网关访问策略和证书
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'XMPP 联合身份验证基于可扩展消息和状态协议 (XMPP) 定义外部部署。 XMPP 配置允许用户通过以下方式访问 XMPP 域用户:'
ms.openlocfilehash: 01adcbe06718068e84844f704858e04198b197b2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239289"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>配置 XMPP 网关访问策略和证书

XMPP 联合身份验证基于可扩展消息和状态协议 (XMPP) 定义外部部署。 XMPP 配置允许用户通过以下方式访问 XMPP 域用户:
  
- 即时消息和联机状态-仅限人员
    
- 在 Skype for Business 客户端中创建 XMPP 联盟联系人
    
为支持 XMPP 联盟伙伴的策略配置策略时, 这些策略适用于 XMPP 联盟域的用户, 但不适用于会话初始协议 (SIP) 即时消息 (IM) 服务提供商或 SIP 联盟域的用户。 为你希望允许用户添加联系人并与之通信的每个 XMPP 联盟域配置 XMPP 联盟合作伙伴。 策略准备好后, 您需要配置 XMPP 网关证书。 
  
> [!NOTE]
> XMPP 功能在 Skype for business Server 2019 中已弃用, 但可以继续在与 Skype for business Server 2019 共存的旧服务器中使用。 确保已部署旧服务器 (Skype for Business Server 2015/Lync Server 2013) XMPP 网关, 并将访问策略配置为为旧版 XMPP 网关启用用户。 有关详细信息, 请参阅[迁移 XMPP 联合身份验证](migrating-xmpp-federation.md)。 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>将外部访问策略配置为为旧版 XMPP 网关启用用户

1. 打开旧的 Skype for Business 服务器控制面板。
    
2. 在左侧导航栏中, 单击 "**联盟和外部访问**", 然后单击 "**外部访问策略**"。
    
3. 单击“**新建**”，然后单击“**用户策略**”。
    
4. 输入外部 access 用户策略的名称。
    
5. 提供外部 access 用户策略的说明。
    
6. 选择 "**启用与联盟用户的通信**"。
    
7. 选择 "**启用与 XMPP 联盟用户的通信**"。
    
8. 单击 "**提交**" 将更改保存到 "网站" 或 "用户策略"。 
    

