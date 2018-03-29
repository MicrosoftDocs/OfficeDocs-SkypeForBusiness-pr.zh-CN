---
title: Lync Server 2010 中的前端采集转送服务设置扩展
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 编辑此对话框中的中介服务器 PSTN 网关设置的属性。 定义下列设置：
ms.openlocfilehash: e3ec392aac08121296769a9d5170886c61c7511b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Lync Server 2010 中的前端采集转送服务设置扩展
 
编辑此对话框中的**中介服务器 PSTN 网关**设置的属性。 定义下列设置：
  
- 如果您想要配置与此前端服务器或前端池中介服务器，请选择**搭配使用中介服务器启用了**。
    
- **侦听端口**： 定义中介服务器将侦听的端口。 您可以定义一个用于**TLS**或传输层安全性或**TCP**，端口或传输控制协议。 可用的 TCP 端口条目，您必须**启用 TCP**端口选择复选框。 
    
    > [!IMPORTANT]
    > 请参阅以确定是否您需要启用并定义端口值 TLS 和 / 或 TCP 公用交换的电话网络 (PSTN) 网关的文档和配置设置。 TLS 是更安全的协议，使用证书来加密中介服务器和 PSTN 网关之间的通信。 不是所有的 PSTN 网关支持 TLS。 
  
- 当前关联的和现有的“**中继**”（即会话初始协议 (SIP) 中继）、“**网关**”（PSTN 网关或 IP-PBX）和“**站点**”（针对中继和网关配置的站点）的列表。
    
- 选择一个中继、网关和站点并单击“**设为默认值**”以将选择设置为此中介服务的默认值。选择当前的默认值并单击“**取消设为默认值**”以取消将选择设置为当前默认值。然后选择一个新的默认值并单击“**设为默认值**”。
    
 **确定** 接受更改并通过对话框提交更改。
  
 **取消** 放弃更改并关闭对话框。
  
 **帮助** 显示此帮助屏幕。
  

