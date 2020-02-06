---
title: 为试点池部署配置 DNS 记录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在部署试验池之前，必须为试验池更新 DNS 主机的条目。 若要成功完成此过程，你应作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。
ms.openlocfilehash: 94e5047dc82b0ddb55b03ad5c466011878c05ae7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813850"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>为试点池部署配置 DNS 记录

在部署试验池之前，必须为试验池更新 DNS 主机的条目。 若要成功完成此过程，你应作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。
  
### <a name="to-configure-dns-host-a-records"></a>配置 DNS 主机 A 记录

1. 在 "域名系统（DNS）" 服务器上，单击 "**开始**"，单击 "**管理工具**"，然后单击 " **DNS**"。
    
2. 在您的域的控制台树中，展开 "**正向查找区域**"，然后右键单击将在其中安装 Skype For business Server 2019 的域。
    
3. 单击 "**新建主机（A 或 AAAA）**"。
    
4. 单击 "**名称**"，键入 Skype For business Server 2019 池的主机名（从在其中定义记录的区域中假定为域名，并且不需要将其输入为 A 记录的一部分）。
    
5. 单击 " **IP 地址**"，然后键入前端池的 ip 地址。
    
6. 单击 "**添加主机**"，然后单击 **"确定"**。 
    
7. 完成后，单击 "**完成**"。
    

