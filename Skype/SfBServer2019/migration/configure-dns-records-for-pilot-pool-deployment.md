---
title: 为试点池部署配置 DNS 记录
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
description: 在部署试点池之前，必须为引导池更新 DNS 主机的条目。 若要成功完成此过程，您应以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录到服务器或域。
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754052"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>为试点池部署配置 DNS 记录

在部署试点池之前，必须为引导池更新 DNS 主机的条目。 若要成功完成此过程，您应以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录到服务器或域。
  
### <a name="to-configure-dns-host-a-records"></a>配置 DNS 主机 A 记录

1. 在域名系统 (DNS) 服务器上，单击“开始”****，再单击“管理工具”****，然后单击“DNS”****。
    
2. 在您的域的控制台树中，展开 "**正向查找区域**"，然后右键单击将在其中安装 Skype For business Server 2019 的域。
    
3. 单击“新建主机(A 或 AAAA)”****。
    
4. 单击 "**名称**"，键入 Skype For business Server 2019 池的主机名（假定该域名来自定义该记录的区域，并且无需输入为 A 记录的一部分）。
    
5. 单击 " **IP 地址**"，然后键入前端池的 IP 地址。
    
6. 单击“添加主机”****，然后单击“确定”****。 
    
7. 完成后，单击“完成”****。
    

