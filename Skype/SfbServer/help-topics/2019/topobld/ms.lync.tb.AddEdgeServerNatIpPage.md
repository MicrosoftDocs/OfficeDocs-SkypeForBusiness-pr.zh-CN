---
title: 添加边缘服务器 NAT IP
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: 公共 IP 地址是网络地址转换 (NAT) 使用的 IP 地址。IP 地址必须为公共可路由的地址。由于在此向导的“选择功能”页上选择了“此边缘池的外部 IP 地址由 NAT 转换”选项，因此这一点是必需的。
ms.openlocfilehash: 15d270032ea0ba60d53962085cd63a70f775d02d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398225"
---
# <a name="add-edge-server-nat-ip"></a>添加边缘服务器 NAT IP

公共 IP 地址是网络地址转换 (NAT) 使用的 IP 地址。IP 地址必须为公共可路由的地址。由于在此向导的“选择功能”页上选择了“此边缘池的外部 IP 地址是由 NAT 转换的”选项，因此这一点是必需的。

> [!NOTE]
> 网络地址转换 (NAT) 允许专用网络（例如 192.168.0.0 范围）上的客户端或服务器通过公共 Internet 网络与远程网络上的系统进行通信。NAT 通过使用外部接口上的单个公共 IP 地址并将内部 IP 地址与一个公共 IP 地址相关联而起作用。NAT 映射可将内部地址映射到外部公共 IP 地址。远程系统只能看到源的公共地址。远程系统响应源，而源将参考 NAT 映射来确定应当将响应返回到哪个内部 IP 地址。

可以在部署初始拓扑时或在部署后添加对外部用户访问的支持。有关向现有拓扑中添加边缘服务器的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。