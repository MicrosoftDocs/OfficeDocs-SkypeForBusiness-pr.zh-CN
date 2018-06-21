---
title: 添加 Survivable Branch Appliance PSTN
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 要在分支站点为 Survivable Branch appliance 定义公用电话交换网 (pstn) 网关，请指定以下内容：
ms.openlocfilehash: 7357beacc93e9fbfede068802c5e849416096a0e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19996882"
---
# <a name="add-survivable-branch-appliance-pstn"></a>添加 Survivable Branch Appliance PSTN
 
要在分支站点为 Survivable Branch appliance 定义公用电话交换网 (pstn) 网关，请指定以下内容： 
  
- 完全限定的域名 (FQDN) 或 IP 地址的对等网关的 Survivable Branch Appliance 或 Survivable Branch Server 相关联的路由入站和出站 PSTN 呼叫。
    
    > [!IMPORTANT]
    > 如果您要定义 Survivable Branch Appliance，这是指 Survivable Branch Appliance 内的中介服务器将连接的 PSTN 连接的网关。 
  
- 将用于会话初始协议 (SIP) 消息的侦听端口。默认情况下，网关、专用交换机 (PBX) 或会话边界控制器 (SBC) 上的传输控制协议 (TCP) 端口为 5066，传输层安全性 (TLS) 的端口为 5067。在分支站点的 Survivable Branch Appliance 上，TCP 的默认端口为 5081，TLS 的默认端口为 5082。
    
- 出于安全考虑，强烈建议使用 TLS。 如果您要定义 Survivable Branch Appliance，请参阅 Survivable Branch Appliance 供应商文档来验证您 Survivable Branch Appliance 支持 TLS 协议。
    
    > [!IMPORTANT]
    > 出于安全考虑，强烈建议部署可以使用 TLS 的网关。 
  
> [!NOTE]
> 如果要添加 PSTN 网关，可以稍后对其进行设置，但在定义和配置 PSTN 网关之前，完整功能将受到限制。 
  

