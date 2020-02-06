---
title: 添加 Survivable Branch Appliance PSTN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 若要为分支站点上的 Survivable 分支装置定义公共交换电话网络（PSTN）网关，请指定以下内容：
ms.openlocfilehash: a20c2d4296b7e262cf73ef89b4c20c54eaa3ad0e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820584"
---
# <a name="add-survivable-branch-appliance-pstn"></a>添加 Survivable Branch Appliance PSTN
 
若要为分支站点上的 Survivable 分支装置定义公共交换电话网络（PSTN）网关，请指定以下内容： 
  
- 网关对等的完全限定的域名（FQDN）或 IP 地址 Survivable 分支装置或 Survivable 分支服务器与路由入站和出站 PSTN 呼叫相关联。
    
    > [!IMPORTANT]
    > 如果你要定义 Survivable 分支设备，这是 Survivable 分支设备中的中介服务器将连接到 PSTN 连接的网关。 
  
- 将用于会话初始协议 (SIP) 消息的侦听端口。默认情况下，网关、专用交换机 (PBX) 或会话边界控制器 (SBC) 上的传输控制协议 (TCP) 端口为 5066，传输层安全性 (TLS) 的端口为 5067。在分支站点的 Survivable Branch Appliance 上，TCP 的默认端口为 5081，TLS 的默认端口为 5082。
    
- 出于安全考虑，强烈建议使用 TLS。 如果你要定义 Survivable 分支设备，请参阅 Survivable 分支设备供应商文档，以验证你的 Survivable 分支设备是否支持 TLS 协议。
    
    > [!IMPORTANT]
    > 出于安全考虑，强烈建议部署可以使用 TLS 的网关。 
  
> [!NOTE]
> 如果要添加 PSTN 网关，可以稍后对其进行设置，但在定义和配置 PSTN 网关之前，完整功能将受到限制。 
  

