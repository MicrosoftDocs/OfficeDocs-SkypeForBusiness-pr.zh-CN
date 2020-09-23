---
title: 添加 Lync Server 2010 的边缘服务器选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 定义新的边缘服务器或边缘池，并向其提供定义新服务器或池的功能的机会。 可以选择的选项有：
ms.openlocfilehash: 273b2543fc3eea1373817ab38eab39379ec59132
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216593"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>添加 Lync Server 2010 的边缘服务器选项

定义新的边缘服务器或边缘池，并向其提供定义新服务器或池的功能的机会。 可以选择的选项有：

- **使用一个 FQDN 和 IP 地址**：选中此复选框可将单个 IPv4 或 IPv6（如果选择同时使用 IPv4 和 IPv6，则需要为每种 IP 地址类型定义一个）地址和完全限定的域名 (FQDN) 用于外部边缘接口。

    > [!IMPORTANT]
    > 如果选择此选项，则仅使用一个 IP 地址，或一个 IPv4 和一个 IPv6 地址，但是必须将不同的端口号分配给每个边缘接口。

- **启用联盟(端口 5061)**：如果要与使用会话初始协议 (SIP) 的其他 SIP 联盟、提供程序或托管服务进行联盟，则选中此复选框。

- **此边缘池的外部 IP 地址由 NAT 转换**：如果您对边缘外部接口使用专用 IP 地址，并且将提供网络地址转换 (NAT) 设备以在逻辑上放置边缘服务器或边缘池，请选中此复选框。

## <a name="see-also"></a>另请参阅

[规划外部用户访问](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[部署边缘服务器](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
