---
title: 添加 Lync Server 2010 中的边缘服务器选项
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 定义新的边缘服务器或池边缘，将新的服务器或池的功能定义的机会提供。 您可以选择的选项有：
ms.openlocfilehash: c031480dd3553aa4fc1ca2f2a8ddd03f67d9bc02
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>添加 Lync Server 2010 中的边缘服务器选项
 
定义新的边缘服务器或池边缘，将新的服务器或池的功能定义的机会提供。 您可以选择的选项有：
  
- **使用单个的 FQDN 和 IP 地址**： 选中复选框 （如果您选择使用 IPv4 和 IPv6，则将需要定义每个 IP 地址类型之一） 使用单个 IPv4 或 IPv6 地址和完全限定的域名称 (FQDN) 为外部边缘的接口。 
    
    > [!IMPORTANT]
    > 如果您选择此选项，您将使用只有一个 IP 地址，或一个 IPv4 和一个 IPv6，但您必须为每个边界面分配不同的端口号。 
  
- **启用联盟 （端口 5061）**： 选中此复选框，如果您将与其他 SIP 联合体、 提供者或使用会话初始化协议 (SIP) 的托管的服务联盟。
    
- **此边池的外部 IP 地址翻译通过 NAT**： 选中此复选框，如果对于边缘外部接口使用专用 IP 地址，并且将提供网络地址转换 (NAT) 设备将边缘服务器或逻辑上边缘池隐藏。
    
## <a name="see-also"></a>另请参阅

#### 

[为外部用户访问计划](http://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)
  
[部署的外部用户访问权限](http://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)

