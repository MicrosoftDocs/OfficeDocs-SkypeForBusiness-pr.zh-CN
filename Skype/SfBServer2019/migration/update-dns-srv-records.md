---
title: 更新 DNS SRV 记录
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要成功完成此过程，您应登录到服务器或域的 Domain Admins 组成员或 DnsAdmins 组的成员。
ms.openlocfilehash: f298db10f7030482b604734a1719756af4071ce2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027226"
---
# <a name="update-dns-srv-records"></a>更新 DNS SRV 记录

若要成功完成此过程，您应登录到服务器或域的 Domain Admins 组成员或 DnsAdmins 组的成员。
  
本主题介绍如何在迁移到 Skype for Business Server 2019 后更新的域名系统 (DNS) 记录。 所有用户都移动到 Skype 的业务服务器 2019年后，但在停用旧池或控制器之前，您必须在您的每个 SIP 域的内部 DNS 更新 DNS SRV 记录。 此过程假定您的内部 DNS 具有用于您的 SIP 用户域的区域。
  
## <a name="to-configure-a-dns-srv-record"></a>若要配置的 DNS SRV 记录

1. 在 DNS 服务器上，单击**开始**，单击**管理工具**，然后单击**DNS**。
    
2. 在您的 SIP 域的控制台树中，展开**正向查找区域**，展开 SIP 域中的 Skype 的业务服务器 2019年安装，并导航到 **_tcp**设置。 
    
3. 在右窗格中，右键单击 **_sipinternaltls**并选择**属性**。
    
4. 在**主机提供此服务**，更新主机 FQDN 以指向业务服务器 2019年池 Skype。
    
5. 单击“**确定**”。
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>若要验证可以解析前端池或 Standard Edition server 的 FQDN

1. 登录到域中的客户端计算机上。
    
2. 单击 **“开始”**，然后单击 **“运行”**。
    
3. 在**打开**框中，键入 cmd，，然后单击**确定**。
    
4. 在命令提示符处键入 nslookup_\<的前端池的 FQDN\>_ 或_\<Standard Edition server 的 FQDN\>_，然后按 ENTER。
    
5. 验证收到答复的 fqdn 解析为适当的 IP 地址。
    

