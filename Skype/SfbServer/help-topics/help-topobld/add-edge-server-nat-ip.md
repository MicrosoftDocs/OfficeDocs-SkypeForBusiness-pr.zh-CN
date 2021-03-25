---
title: 添加边缘服务器 NAT IP
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: 公共 IP 地址是网络地址转换 (NAT) 使用的 IP 地址。 IP 地址必须为公共可路由的地址。 由于在此向导的“选择功能”页上选择了“此边缘池的外部 IP 地址由 NAT 转换”选项，因此这一点是必需的。
ms.openlocfilehash: cf5cb61dce8d71e97ba3977e241df4480c30a403
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119811"
---
# <a name="add-edge-server-nat-ip"></a>添加边缘服务器 NAT IP

公共 IP 地址是网络地址转换 (NAT) 使用的 IP 地址。IP 地址必须为公共可路由的地址。由于在此向导的“选择功能”页上选择了“此边缘池的外部 IP 地址是由 NAT 转换的”选项，因此这一点是必需的。

> [!NOTE]
> 网络地址转换 (NAT) 允许专用网络（例如 192.168.0.0 范围）上的客户端或服务器通过公共 Internet 网络与远程网络上的系统进行通信。NAT 通过使用外部接口上的单个公共 IP 地址并将内部 IP 地址与一个公共 IP 地址相关联而起作用。NAT 映射可将内部地址映射到外部公共 IP 地址。远程系统只能看到源的公共地址。远程系统响应源，而源将参考 NAT 映射来确定应当将响应返回到哪个内部 IP 地址。

可以在部署初始拓扑时或在部署后添加对外部用户访问的支持。 有关向现有拓扑中添加边缘服务器的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。