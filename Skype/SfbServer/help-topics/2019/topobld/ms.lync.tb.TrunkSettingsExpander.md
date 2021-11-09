---
title: Trunk 设置扩展器
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑或修改 SIP 中继的设置，请执行下列操作：
ms.openlocfilehash: 922e401ea74b554681dadbc94b7c7f4178a618e8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829226"
---
# <a name="trunk-settings-expander"></a>中继设置扩展器

若要编辑或修改 SIP 中继的设置，请执行下列操作：

 “Trunk 名称”是必填项，并唯一标识部署中的 SIP 中继。

 **关联的 PSTN 网关**：选择部署中已定义的现有 PSTN 网关。

 **IP/PSTN 网关的侦听端口**：指示网关要在其上侦听请求的 TCP/IP 端口。根据网关的供应商，所需的值可能会有所不同，但默认为端口 5067。

 **SIP 传输协议**：使用的协议可以是 TCP，也可以是 TLS。TLS 为默认选项。有关网关所支持的选项，请参考网关供应商文档。默认为 TLS，且如果网关支持 TLS，则应将其视为更安全的选择。

 **关联的中介服务器**：从部署中选择现有中介服务器以与 SIP 中继关联。

> [!NOTE]
> 只有根中继可以与中介服务器关联。

 **关联的中介服务器端口**：一个必需值，设置为中介服务器配置为侦听的值。

![中继设置扩展器。](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>另请参阅

[SIP 中继部署清单](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[用于 SIP 中继的组件和拓扑](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)