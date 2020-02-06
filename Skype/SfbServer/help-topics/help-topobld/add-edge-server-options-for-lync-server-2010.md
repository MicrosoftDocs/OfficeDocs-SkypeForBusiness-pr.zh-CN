---
title: 为 Lync Server 2010 添加 Edge Server 选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 定义新的边缘服务器或边缘池，并向用户提供定义新服务器或池功能的机会。 可供选择的选项包括：
ms.openlocfilehash: 983a8a6e4fdeea34930cc9adf2b2cb29e4c75759
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820984"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>为 Lync Server 2010 添加 Edge Server 选项

定义新的边缘服务器或边缘池，并向用户提供定义新服务器或池功能的机会。 可供选择的选项包括：

- **使用单个 FQDN 和 IP 地址**：选中复选框以使用单个 IPv4 或 ipv6 （如果选择使用 Ipv4 和 ipv6，则需要为外部边缘接口定义每个 IP 地址类型）地址和完全限定的域名（FQDN）。

    > [!IMPORTANT]
    > 如果选择此选项，你将仅使用一个 IP 地址，或使用一个 IPv4 和一个 IPv6，但必须为每个 Edge 接口分配不同的端口号。

- **启用联盟（端口5061）**：如果你将与使用会话初始协议（SIP）的其他 SIP 联合、提供程序或托管产品联盟，请选中此复选框。

- **此 Edge 池的外部 IP 地址由 NAT 转换**：如果你对 edge 外部接口使用专用 IP 地址，并且将提供网络地址转换（NAT）设备以逻辑方式放置边缘服务器或边缘池，请选中此复选框。

## <a name="see-also"></a>另请参阅

[规划外部用户访问](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[部署外部用户访问](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
