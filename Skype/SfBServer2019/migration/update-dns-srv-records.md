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
localization_priority: Normal
description: 若要成功完成此过程，您应以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录到服务器或域。
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753264"
---
# <a name="update-dns-srv-records"></a>更新 DNS SRV 记录

若要成功完成此过程，您应以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录到服务器或域。
  
本主题介绍了如何在迁移到 Skype for business Server 2019 之后更新域名系统（DNS）记录。 在所有用户都已移动到 Skype for business Server 2019 中，但在旧池或控制器退役之前，必须在每个 SIP 域的内部 DNS 中更新 DNS SRV 记录。 此过程假定内部 DNS 具有 SIP 用户域的区域。
  
## <a name="to-configure-a-dns-srv-record"></a>配置 DNS SRV 记录

1. 在 DNS 服务器上，单击“开始”****，再单击“管理工具”****，然后单击“DNS”****。
    
2. 在您的 SIP 域的控制台树中，展开 "**正向查找区域**"，展开安装了 Skype For business Server 2019 的 SIP 域，然后导航到 " **_tcp** " 设置。 
    
3. 在右侧窗格中，右键单击 " **_sipinternaltls** "，然后选择 "**属性**"。
    
4. 在**提供此服务的主机**中，将主机 FQDN 更新为指向 Skype For business Server 2019 池。
    
5. 单击“确定”。
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>验证是否可以解析前端池或 Standard Edition Server 的 FQDN

1. 登录到域中的客户端计算机。
    
2. 单击“开始”****，再单击“运行”****。
    
3. 在 "**打开**" 框中，键入 cmd，然后单击 **"确定"**。
    
4. 在命令提示符处，键入 nslookup _\<FQDN of the Front End pool\>_ 或 _\<FQDN of the Standard Edition server\>_ ，然后按 enter。
    
5. 验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。
    

