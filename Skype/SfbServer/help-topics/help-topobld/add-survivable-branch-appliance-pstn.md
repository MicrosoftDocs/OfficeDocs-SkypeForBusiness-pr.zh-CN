---
title: 添加 Survivable Branch Appliance PSTN
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 若要定义的分支站点高存活力分支装置公用交换的电话网络 (PSTN) 网关，指定以下项：
ms.openlocfilehash: cefdc46eb2f5b7573e5e5bd9acb93cb5ab384622
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-survivable-branch-appliance-pstn"></a>添加 Survivable Branch Appliance PSTN
 
若要定义的分支站点高存活力分支装置公用交换的电话网络 (PSTN) 网关，指定以下项： 
  
- 完全限定的域名称 (FQDN) 或 IP 地址，对高存活力的分支装置或自动恢复分支服务器程序与入站和出站路由的网关等 PSTN 调用。
    
    > [!IMPORTANT]
    > 如果您正在定义一个高存活力的分支装置，这是高存活力的分支装置内的中介服务器将连接的 PSTN 连接的网关。 
  
- 将用于会话初始协议 (SIP) 消息的侦听端口。默认情况下，网关、专用交换机 (PBX) 或会话边界控制器 (SBC) 上的传输控制协议 (TCP) 端口为 5066，传输层安全性 (TLS) 的端口为 5067。在分支站点的 Survivable Branch Appliance 上，TCP 的默认端口为 5081，TLS 的默认端口为 5082。
    
- 出于安全考虑，强烈建议使用 TLS。 如果您正在定义一个高存活力的分支装置，参考高存活力的分支装置供应商文档，验证您高存活力的分支装置支持 TLS 协议。
    
    > [!IMPORTANT]
    > 出于安全考虑，强烈建议部署可以使用 TLS 的网关。 
  
> [!NOTE]
> 如果要添加 PSTN 网关，可以稍后对其进行设置，但在定义和配置 PSTN 网关之前，完整功能将受到限制。 
  

