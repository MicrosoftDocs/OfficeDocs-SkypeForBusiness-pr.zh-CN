---
title: Lync Server 2010 的前端中介服务设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 编辑此对话框中的中介服务器 PSTN 网关设置的属性。 定义以下设置：
ms.openlocfilehash: a70ec5e569b60c28e8ec91e86d09ac5f5285ee00
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371489"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的前端中介服务设置扩展器
 
编辑此对话框中的**中介服务器 PSTN 网关**设置的属性。 定义以下设置：
  
- 如果您想要将并置中介服务器与此前端服务器或前端池，请选择**并置中介服务器已启用**。
    
- **侦听端口**： 定义中介服务器将侦听的端口。 您可以定义用于**TLS**或传输层安全性或**TCP**的端口或传输控制协议。 可用的 tcp 端口条目，您必须为**启用 TCP 端口**选择复选框。 
    
    > [!IMPORTANT]
    > 请参阅确定如果您需要启用并定义端口值 TLS、 TCP 或同时公用电话交换网 (pstn) 网关的文档和配置设置。 TLS 是一种更安全协议证书用于对中介服务器和 PSTN 网关之间的通信进行加密。 并非所有 PSTN 网关都支持 TLS。 
  
- 当前关联的和现有的“**中继**”（即会话初始协议 (SIP) 中继）、“**网关**”（PSTN 网关或 IP-PBX）和“**站点**”（针对中继和网关配置的站点）的列表。
    
- 选择一个中继、网关和站点并单击“**设为默认值**”以将选择设置为此中介服务的默认值。选择当前的默认值并单击“**取消设为默认值**”以取消将选择设置为当前默认值。然后选择一个新的默认值并单击“**设为默认值**”。
    
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

