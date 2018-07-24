---
title: 中介服务设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 对于“中介服务器”，可以指定以下内容：
ms.openlocfilehash: 3f9e5781202060215e76ad431dc05497387547a3
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21069185"
---
# <a name="mediation-service-settings-expander"></a>中介服务设置扩展器
 
对于“**中介服务器**”，可以指定以下内容：
  
如果您并置中介服务器上的前端池或 Standard Edition server，选择**并置中介服务器已启用**复选框。 如果您选择将中介服务器并置，没有在此部分可定义设置。 
  
如果已启用并置的中介服务器，您需要在服务器上的传输层安全性 (TLS) 定义的侦听端口范围。 默认情况下，此端口为 5067。 如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。 这是一个可选设置，您应该参考网关要求或公用电话交换网 (PSTN) 要求以确定是否需要此设置。 默认情况下，TCP 端口值为 5068。
  
定义与并置的中介服务器关联的 PSTN 网关。 如果已定义网关，它们将可用于与中介服务器相关联。 
  
如果您有多个网关与中介服务器相关联，关联的第一个网关将默认网关。 如果需要选择其他网关作为默认网关，请选择要设为默认值的网关，然后单击“**设为默认值**”。 若要取消选择网关作为默认网关，请单击“**取消设为默认值**”。
  
有关定义和配置设置的 Enterprise Edition 前端池或 Standard Edition server 的详细信息，请参阅[Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)和[Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。
  

