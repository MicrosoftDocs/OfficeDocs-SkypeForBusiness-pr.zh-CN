---
title: 添加 Survivable Branch Appliance PSTN
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: 若要在分支站点为 Survivable Branch Appliance 定义公用电话交换网 (PSTN) 网关，请指定以下内容：
ms.openlocfilehash: 1b8470f88217a5ded93094bc83cc0f31c8c916ca
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745088"
---
# <a name="add-survivable-branch-appliance-pstn"></a>添加 Survivable Branch Appliance PSTN
 
若要在分支站点为 Survivable Branch Appliance 定义公用电话交换网 (PSTN) 网关，请指定以下内容： 
  
- 与 Survivable Branch Appliance 或 Survivable Branch Server 关联且用于路由入站和出站 PSTN 呼叫的对等网关的完全限定域名 (FQDN) 或 IP 地址。
    
    > [!IMPORTANT]
    > 如果要定义 Survivable Branch Appliance，这是 Survivable Branch Appliance 内的中介服务器为实现 PSTN 连接而连接的网关。 
  
- 将用于会话初始协议 (SIP) 消息的侦听端口。默认情况下，网关、专用交换机 (PBX) 或会话边界控制器 (SBC) 上的传输控制协议 (TCP) 端口为 5066，传输层安全性 (TLS) 的端口为 5067。在分支站点的 Survivable Branch Appliance 上，TCP 的默认端口为 5081，TLS 的默认端口为 5082。
    
- 出于安全考虑，强烈建议使用 TLS。如果要定义 Survivable Branch Appliance，请参考 Survivable Branch Appliance 供应商文档，以验证 Survivable Branch Appliance 是否支持 TLS 协议。
    
    > [!IMPORTANT]
    > 出于安全考虑，强烈建议部署可以使用 TLS 的网关。 
  
> [!NOTE]
> 如果要添加 PSTN 网关，可以稍后对其进行设置，但在定义和配置 PSTN 网关之前，完整功能将受到限制。 
  

