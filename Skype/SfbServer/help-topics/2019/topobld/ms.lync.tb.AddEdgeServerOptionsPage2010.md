---
title: 添加 Lync Server 2010 边缘服务器选项
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 定义新的边缘服务器或边缘池和显示定义的新服务器或池的功能的机会。 您可以选择的选项包括：
ms.openlocfilehash: d9dae42d815855cea4c7f07b484e026c72ce22cf
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19974013"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>添加 Lync Server 2010 边缘服务器选项
 
定义新的边缘服务器或边缘池和显示定义的新服务器或池的功能的机会。 您可以选择的选项包括：
  
- **使用单个 FQDN 和 IP 地址**： 选中的复选框 （如果您选择使用 IPv4 和 IPv6，则您将需要定义每个 IP 地址类型之一） 使用单个 IPv4 或 IPv6 地址和完全限定的域名 (FQDN) 的外部边缘接口。 
    
    > [!IMPORTANT]
    > 如果您选择此选项，您将使用只有一个 IP 地址，或一个 IPv4 和一个 IPv6，但必须将不同的端口号分配给每个边缘接口。 
  
- **启用联盟 （端口 5061）**： 如果您将与其他 SIP 联盟、 提供程序或使用会话初始协议 (SIP) 的托管的服务建立联盟，请选中此复选框。
    
- **此边缘池的外部 IP 地址由 NAT 转换**： 选中此复选框，如果您使用的边缘外部接口的专用 IP 地址并将提供一个网络地址转换 (NAT) 设备，以将边缘服务器或边缘池逻辑隐藏。
    
## <a name="see-also"></a>另请参阅

[规划外部用户访问](http://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)
  
[部署外部用户访问](http://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)