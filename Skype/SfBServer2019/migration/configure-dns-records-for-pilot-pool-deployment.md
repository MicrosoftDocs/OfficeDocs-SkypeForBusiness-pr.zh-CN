---
title: 为试点池部署配置 DNS 记录
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 部署试点池之前, 必须更新试点池的 DNS 主机 A 条目。 若要成功完成此过程，您应登录到服务器或域的 Domain Admins 组成员或 DnsAdmins 组的成员。
ms.openlocfilehash: 13492f7972e127de7a8200a0dbe933c72aba2da7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029893"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>为试点池部署配置 DNS 记录

部署试点池之前, 必须更新试点池的 DNS 主机 A 条目。 若要成功完成此过程，您应登录到服务器或域的 Domain Admins 组成员或 DnsAdmins 组的成员。
  
### <a name="to-configure-dns-host-a-records"></a>配置 DNS 主机 A 记录

1. 在域名系统 (DNS) 服务器上，单击**开始**，单击**管理工具**，然后单击**DNS**。
    
2. 在您的域的控制台树中，展开**正向查找区域**，，然后右键单击在其中安装业务服务器 2019年的 Skype 的域。
    
3. 单击**新建主机 （A 或 AAAA）**。
    
4. 单击**名称**中，键入 （从记录中定义的且不需要输入的 A 记录的一部分的区域假定域名称） 的业务服务器 2019年池 Skype 的主机名。
    
5. 单击**IP 地址**，然后键入前端池的 IP 地址。
    
6. 单击**添加主机**，，然后单击**确定**。 
    
7. 完成后，单击**完成**。
    

