---
title: 中介服务设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 对于中介服务器，可以指定以下各项：
ms.openlocfilehash: e322b2ffd383c2bd0170852a6fec6c3122251700
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-service-settings-expander"></a>中介服务设置扩展器
 
对于“**中介服务器**”，可以指定以下内容：
  
如果您正在配置中介服务器到前端池或标准版服务器，选择**搭配使用中介服务器已启用**复选框。 如果您选择不布置中介服务器，有此部分中没有可定义的设置。 
  
如果您已启用了中介服务器的配置，您需要在服务器上的传输层安全性 (TLS) 定义侦听的端口范围。 默认情况下，此端口为 5067。 如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。 这是一个可选设置，您应该参考网关要求或公用电话交换网 (PSTN) 要求以确定是否需要此设置。 默认情况下，TCP 端口值为 5068。
  
定义与按顺序排列的中介服务器相关联的 PSTN 网关。 如果您已经定义了网关，它们可中介服务器相关联。 
  
如果您有多个网关与中介服务器关联，关联的第一个网关将默认网关。 如果需要选择其他网关作为默认网关，请选择要设为默认值的网关，然后单击“**设为默认值**”。 若要取消选择网关作为默认网关，请单击“**取消设为默认值**”。
  
定义和配置为标准版服务器的企业版前端池的设置的详细信息，请参阅[定义和配置拓扑结构](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)，以及[部署中介服务器和定义等](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。
  

