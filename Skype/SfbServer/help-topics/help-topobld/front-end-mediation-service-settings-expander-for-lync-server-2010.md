---
title: Lync Server 2010 的前端中介服务设置扩展器
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 在此对话框中编辑“中介服务器 PSTN 网关”设置的属性。定义以下设置：
ms.openlocfilehash: 81cd0fb38aa10cdd5603cc3ddddc0f7c9a48608b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778482"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>适合于 Lync Server 2010 的前端中介服务设置扩展器
 
在此对话框中编辑“中介服务器 PSTN 网关”设置的属性。定义以下设置：
  
- 如果要将 **中介服务器** 与前端服务器或前端池并并，请选择"并排中介服务器已启用"。
    
- **侦听端口**：定义中介服务器将侦听的端口。 可以为 **TLS**（即传输层安全性）或 **TCP**（即传输控制协议）定义端口。 要让 TCP 端口输入可用，必须选中“启用 TCP 端口”复选框。 
    
    > [!IMPORTANT]
    > 请参阅公用电话交换网 (PSTN) 网关的文档和配置设置，以确定是需要启用并定义端口值 TLS 和/或 TCP。 TLS 是一种更安全的协议，使用证书加密中介服务器和 PSTN 网关之间的通信。 并非所有的 PSTN 网关都支持 TLS。 
  
- 当前关联的和现有的“中继”（即会话初始协议 (SIP) 中继）、“网关”（PSTN 网关或 IP-PBX）和“站点”（针对中继和网关配置的站点）的列表。
    
- 选择一个中继、网关和站点并单击“设为默认值”以将选择设置为此中介服务的默认值。选择当前的默认值并单击“取消设为默认值”以取消将选择设置为当前默认值。然后选择一个新的默认值并单击“设为默认值”。
    
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

