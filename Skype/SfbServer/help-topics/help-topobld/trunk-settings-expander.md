---
title: Trunk 设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 若要编辑或修改 SIP 中继的设置，请执行下列操作：
ms.openlocfilehash: 13ea9abfb6d53b57333c2c96b8a2f8adde963ebf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="trunk-settings-expander"></a>中继设置扩展器
 
若要编辑或修改 SIP 中继的设置，请执行下列操作：
  
 “**Trunk 名称**”是必填项，并唯一标识部署中的 SIP 中继。
  
 **关联的 PSTN 网关**：选择部署中已定义的现有 PSTN 网关。
  
 **IP/PSTN 网关的侦听端口**：指示网关要在其上侦听请求的 TCP/IP 端口。根据网关的供应商，所需的值可能会有所不同，但默认为端口 5067。
  
 **SIP 传输协议**：使用的协议可以是 TCP，也可以是 TLS。TLS 为默认选项。有关网关所支持的选项，请参考网关供应商文档。默认为 TLS，且如果网关支持 TLS，则应将其视为更安全的选择。
  
 **相关中介服务器**： 从部署与 SIP 中继选择现有的中介服务器。
  
> [!NOTE]
> 只有根主干可以使用 Lync Server 2010 或 Lync Server 2013 中介服务器相关联。 
  
 **相关中介服务器端口**： 所需的值，这设置为值中介服务器被配置为侦听。
  
![中继设置扩展器](../../media/Trunk_Settings_Expander.jpg)
  
## <a name="see-also"></a>另请参阅

#### 

[SIP 中继部署检查表](http://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)
  
[组件和 SIP 中继拓扑](http://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)

