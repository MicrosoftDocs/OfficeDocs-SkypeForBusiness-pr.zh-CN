---
title: 添加 Lync Server 2010 的边缘服务器选项
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 定义新的边缘服务器或边缘池，并有机会定义新服务器或池的功能。 可以选择的选项有：
ms.openlocfilehash: 0c02e03a1e0e1a8c8455be48915f1c488f4d021f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845535"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>添加 Lync Server 2010 的边缘服务器选项

定义新的边缘服务器或边缘池，并有机会定义新服务器或池的功能。 可以选择的选项有：

- **使用一个 FQDN 和 IP 地址**：选中此复选框可将单个 IPv4 或 IPv6（如果选择同时使用 IPv4 和 IPv6，则需要为每种 IP 地址类型定义一个）地址和完全限定的域名 (FQDN) 用于外部边缘接口。

    > [!IMPORTANT]
    > 如果选择此选项，则仅使用一个 IP 地址，或一个 IPv4 和一个 IPv6 地址，但是必须将不同的端口号分配给每个边缘接口。

- **启用联盟(端口 5061)**：如果要与使用会话初始协议 (SIP) 的其他 SIP 联盟、提供程序或托管服务进行联盟，则选中此复选框。

- 此边缘池的外部 IP 地址由 **NAT** 转换：如果将专用 IP 地址用于边缘外部接口，并提供网络地址转换 (NAT) 设备以在逻辑上隐藏边缘服务器或边缘池，请选中此复选框。

## <a name="see-also"></a>另请参阅

[规划外部用户访问](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)

[部署边缘服务器](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-external-user-access)