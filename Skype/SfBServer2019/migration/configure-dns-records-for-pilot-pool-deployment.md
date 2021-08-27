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
ms.localizationpriority: medium
description: 在部署试点池之前，必须更新试点池的 DNS 主机 A 条目。 要成功完成此过程，您应该以 Domain Admins 组或 DnsAdmins 组的成员身份登录到服务器或域。
ms.openlocfilehash: e77a85d84debadc19e52cb2d195ac86f5b3e6055
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588054"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>为试点池部署配置 DNS 记录

部署试点池之前，必须更新试点池的 DNS 主机 A 条目。 要成功完成此过程，您应该以 Domain Admins 组或 DnsAdmins 组的成员身份登录到服务器或域。
  
### <a name="to-configure-dns-host-a-records"></a>配置 DNS 主机 A 记录

1. 在域名系统 (DNS) 服务器上，单击“开始”，再单击“管理工具”，然后单击“DNS”。
    
2. 在域的控制台树中，展开"前向查找区域"，然后右键单击将安装 Skype for Business Server 2019 的域。
    
3. 单击“新建主机(A 或 AAAA)”。
    
4. 单击 **"** 名称"，键入 Skype for Business Server 2019 池的主机名 (假定域名来自记录定义的区域，并且不需要作为 A 记录的一) 。
    
5. 单击 **"IP 地址**"，然后键入前端池的 IP 地址。
    
6. 单击“添加主机”，然后单击“确定”。 
    
7. 完成后，单击“完成”。
    

