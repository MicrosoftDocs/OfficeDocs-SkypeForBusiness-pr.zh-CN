---
title: 边缘设置扩展器
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 要编辑包含单个或多个服务器的现有边缘池的设置，可参考以下各节内容：
ms.openlocfilehash: e0ad220836bb1a72ebf762e866ab6d3e4a7cd2fb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852166"
---
# <a name="edge-settings-expander"></a>边缘设置扩展器

要编辑包含单个或多个服务器的现有边缘池的设置，可参考以下各节内容：

- 常规设置

- 下一个跃点选择设置

- 边缘服务器配置



## <a name="general-settings"></a>常规设置

边缘服务器池的内部池完全限定域名 (FQDN)。编辑池的 FQDN 以更改此设置。

如果要设置与 Lync Server 2013、Microsoft Lync Server 2010 或 Microsoft Office Communications Server 2007 R2 受信任伙伴的联盟，请选中"为此边缘池启用联盟 **(端口 5061) "** 复选框。

选中“为此边缘池启用 XMPP 联盟”可启用 XMPP 联盟。

为“内部配置复制端口(HTTPS)”指定端口号。

## <a name="next-hop-selection-settings"></a>下一个跃点选择设置

若要设置或修改边缘服务器用于与内部基础结构通信的"下一个跃点池"，请从下拉列表框中选择控制器、控制器池、前端服务器或前端服务器池。 只有已在拓扑生成器中配置的控制器或前端会进行选择。

## <a name="edge-server-configuration"></a>边缘服务器配置

要编辑或指定边缘服务器的“外部设置”的设置，首先必须确定 SIP 访问、Web 会议和音频/视频服务是否要使用单独的 IP 地址。

如果它们都要使用单独的 IP 地址，请选中“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”复选框。每个服务必须具有为其创建的对应 DNS 主机 (A) 记录。

对于每个面向外部的服务，指定 FQDN 和关联端口。例如，“SIP 访问”将使用 sip.contoso.com 和关联端口 5061。

> [!IMPORTANT]
> 如果为每个面向外部的服务选择单独的 FQDN，则每个服务必须具有与其关联的唯一端口值。 默认情况下，SIP 在端口 5061/TLS 上，Web 会议边缘服务在端口 444/TLS 上，A/V 会议服务器在端口 443/TLS 上。 如果对这些设置进行任何更改，包括使用单独的 FQDN 和 IP 地址或端口，则必须更新将依赖最初配置的值的其他所有服务。

如果确定组织要为面向外部的服务使用单个 FQDN 和 IP 地址，请清除“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”复选框。然后，可以编辑“SIP 访问”池 FQDN 和端口值（如有必要）。

> [!IMPORTANT]
> 如果对这些设置进行任何更改，包括使用单独的 FQDN 和 IP 地址或端口，则必须更新将依赖最初配置的值的其他所有服务。

## <a name="see-also"></a>另请参阅

有关定义和配置边缘服务设置的详细信息，请参阅[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。