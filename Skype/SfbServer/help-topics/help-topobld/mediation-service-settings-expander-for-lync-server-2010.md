---
title: Lync Server 2010 的中介服务设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 通过定义以下属性编辑中介服务的属性：
ms.openlocfilehash: c0057157168667ea9ed0981390e59d5dfb1cd89e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285636"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的中介服务设置扩展器
 
通过定义以下属性编辑中介服务的属性：
  
- **侦听端口**：定义中介服务将侦听的 **TLS** 端口。默认情况下，该端口值为使用传输层安全性 (TLS) 的 TCP 5067
    
    或者，定义一个 **TCP** 端口值。默认情况下，该值为 TCP 5068。
    
    > [!NOTE]
    > 可通过选择“**启用 TCP 端口**”来启用 TCP 端口值设置。有关与中介服务通信所需的端口设置要求，请参阅公用电话交换网 (PSTN) 网关或 Internet 协议专用交换机 (IP-PBX) 的相关文档。 
  
- “**启用 TCP 端口**”定义来自 PSTN 网关或 IP-PBX 的 TCP 通信的端口值。
    
- 当前关联的和现有的“**中继**”（即会话初始协议 (SIP) 中继）、“**网关**”（PSTN 网关或 IP-PBX）和“**站点**”（针对中继和网关配置的站点）的列表。
    
- 选择一个中继、网关和站点并单击“**设为默认值**”以将选择设置为此中介服务的默认值。选择当前的默认值并单击“**取消设为默认值**”以取消将选择设置为当前默认值。然后选择一个新的默认值并单击“**设为默认值**”。
    
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

