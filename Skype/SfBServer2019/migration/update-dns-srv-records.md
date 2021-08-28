---
title: 更新 DNS SRV 记录
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 要成功完成此过程，您应该以 Domain Admins 组或 DnsAdmins 组的成员身份登录到服务器或域。
ms.openlocfilehash: 1b88ada924cbf2cf7f4153acda54584d81946cb0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579416"
---
# <a name="update-dns-srv-records"></a>更新 DNS SRV 记录

要成功完成此过程，您应该以 Domain Admins 组或 DnsAdmins 组的成员身份登录到服务器或域。
  
本主题介绍如何在迁移到 2019 (DNS) 更新域名系统Skype for Business Server DNS 记录。 在所有用户都移至 Skype for Business Server 2019 之后，但在停用旧池或控制器之前，必须更新内部 DNS 中每个 SIP 域的 DNS SRV 记录。 此过程假定内部 DNS 具有 SIP 用户域的区域。
  
## <a name="to-configure-a-dns-srv-record"></a>配置 DNS SRV 记录

1. 在 DNS 服务器上，单击“开始”，再单击“管理工具”，然后单击“DNS”。
    
2. 在 SIP 域的控制台树中，展开"前向查找区域"，展开安装 Skype for Business Server 2019 的 SIP 域，然后导航到"_tcp"**设置**。 
    
3. 在右窗格中，右 **键单击**"_sipinternaltls并选择"**属性"。**
    
4. 在 **"提供此服务的主机"** 中，更新主机 FQDN 以指向 Skype for Business Server 2019 池。
    
5. 单击“**确定**”。
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>验证是否可以解析前端池或 Standard Edition Server 的 FQDN

1. 登录到域中的客户端计算机。
    
2. 单击“开始”，再单击“运行”。
    
3. 在"**打开"** 框中，键入 cmd，然后单击"确定 **"。**
    
4. 在命令提示符下，键入 nslookup _\<FQDN of the Front End pool\>_ 或  _\<FQDN of the Standard Edition server\>_ ，然后按 Enter。
    
5. 验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。
    

