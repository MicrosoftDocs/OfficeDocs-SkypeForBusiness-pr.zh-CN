---
title: Trunk 设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 若要编辑或修改 SIP 中继的设置，请执行下列操作：
ms.openlocfilehash: aa3c8dd622e64bcd063e84d1f6e19278af9a6cff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819144"
---
# <a name="trunk-settings-expander"></a>中继设置扩展器

若要编辑或修改 SIP 中继的设置，请执行下列操作：

 “**Trunk 名称**”是必填项，并唯一标识部署中的 SIP 中继。

 **关联的 PSTN 网关**：选择部署中已定义的现有 PSTN 网关。

 **IP/PSTN 网关的侦听端口**：指示网关要在其上侦听请求的 TCP/IP 端口。根据网关的供应商，所需的值可能会有所不同，但默认为端口 5067。

 **SIP 传输协议**：使用的协议可以是 TCP，也可以是 TLS。TLS 为默认选项。有关网关所支持的选项，请参考网关供应商文档。默认为 TLS，且如果网关支持 TLS，则应将其视为更安全的选择。

 **关联的中介服务器**：从部署中选择现有中介服务器以与 SIP 主干相关联。

> [!NOTE]
> 只有根干线才能与 Lync Server 2010 或 Lync Server 2013 中介服务器相关联。

 **关联的中介服务器端口**：一个必需值，它设置为中介服务器配置为侦听的值。

![中继设置扩展器](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>另请参阅

[SIP 中继部署清单](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[SIP 中继的组件和拓扑](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
