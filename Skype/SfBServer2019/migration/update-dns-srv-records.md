---
title: 更新 DNS SRV 记录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要成功完成此过程, 你应作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。
ms.openlocfilehash: bf9f9c3f16ceb2ee35cda8e833d468e202d5653c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307054"
---
# <a name="update-dns-srv-records"></a>更新 DNS SRV 记录

若要成功完成此过程, 你应作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。
  
本主题介绍了迁移到 Skype for Business Server 2019 后如何更新域名系统 (DNS) 记录。 在所有用户都已移动到 Skype for Business Server 2019 之后, 在旧池或控制器停止使用之前, 必须在内部 DNS 中更新每个 SIP 域的 DNS SRV 记录。 此过程假定你的内部 DNS 具有适用于你的 SIP 用户域的区域。
  
## <a name="to-configure-a-dns-srv-record"></a>配置 DNS SRV 记录

1. 在 DNS 服务器上, 单击 "**开始**", 单击 "**管理工具**", 然后单击 " **DNS**"。
    
2. 在你的 SIP 域的控制台树中, 展开 "**正向查找区域**", 展开安装了 Skype For business Server 2019 的 SIP 域, 然后导航到 **_tcp**设置。 
    
3. 在右窗格中, 右键单击 " **_sipinternaltls** ", 然后选择 "**属性**"。
    
4. 在**提供此服务的主机**中, 更新主机 FQDN 以指向 Skype For business Server 2019 池。
    
5. 单击“**确定**”。
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>验证是否可以解析前端池或标准版服务器的 FQDN

1. 登录到域中的客户端计算机。
    
2. 单击 **“开始”**，然后单击 **“运行”**。
    
3. 在 "**打开**" 框中, 键入 cmd, 然后单击 **"确定"**。
    
4. 在命令提示符处, 键入_ \<"nslookup FQDN"\> _ ( _ \<标准版服务器\>_ 的前端池或 fqdn), 然后按 ENTER。
    
5. 验证您是否收到了解析为 FQDN 的相应 IP 地址的答复。
    

