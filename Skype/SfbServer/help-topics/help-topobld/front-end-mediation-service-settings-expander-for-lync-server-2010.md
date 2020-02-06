---
title: 适合于 Lync Server 2010 的前端中介服务设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 在此对话框中编辑中介服务器 PSTN 网关设置的属性。 定义以下设置：
ms.openlocfilehash: dfe3defeb7cdce787321a401ca2a5450ee6b4ab8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819874"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>适合于 Lync Server 2010 的前端中介服务设置扩展器
 
在此对话框中编辑**中介服务器 PSTN 网关**设置的属性。 定义以下设置：
  
- 如果想要通过此前端服务器或前端池 collocate 中介服务器，请选择 "**启用的 Collocated 中介服务器**"。
    
- **侦听端口**：定义中介服务器将侦听的端口。 你可以为**TLS**或传输层安全性、 **TCP**或传输控制协议定义端口。 若要使 TCP 的端口项可用，必须选中 "**启用 tcp 端口**" 复选框。 
    
    > [!IMPORTANT]
    > 请参阅公共交换电话网络（PSTN）网关的文档和配置设置，确定是否需要启用和定义 TLS、TCP 或两者的端口值。 TLS 是一种更安全的协议，使用证书加密中介服务器和 PSTN 网关之间的流量。 并非所有 PSTN 网关都支持 TLS。 
  
- 当前关联的和现有的“**中继**”（即会话初始协议 (SIP) 中继）、“**网关**”（PSTN 网关或 IP-PBX）和“**站点**”（针对中继和网关配置的站点）的列表。
    
- 选择一个中继、网关和站点并单击“**设为默认值**”以将选择设置为此中介服务的默认值。选择当前的默认值并单击“**取消设为默认值**”以取消将选择设置为当前默认值。然后选择一个新的默认值并单击“**设为默认值**”。
    
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

