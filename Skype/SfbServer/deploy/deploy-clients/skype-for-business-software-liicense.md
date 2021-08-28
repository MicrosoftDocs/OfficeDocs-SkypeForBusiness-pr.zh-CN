---
title: Skype会议室系统Skype for Business软件许可证
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 阅读本主题，了解如何检查你是否拥有Skype for Business批量许可证。
ms.openlocfilehash: 23ea556a8afd7160e20a1ddd0b4e1d044761d4d1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583326"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype会议室系统：Skype for Business软件许可证
 
阅读本主题，了解如何检查你是否拥有Skype for Business批量许可证。 
  
Skype会议室系统使用已安装Skype for Business客户端，这需要软件批量许可证。 部署第一个 Skype 会议室系统之前，请了解部署的批量许可证状态 - 使用密钥管理服务器 (KMS) 或 MAK (多次激活) 。
  
## <a name="key-management-servers-kms"></a>密钥管理服务器 (KMS) 

如果KMS已就位并将Skype for Business批量许可证激活，Skype系统将自动激活 Skype for Business 客户端。 若要了解KMS是否就位：
  
在命令提示符下，运行：  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
有关详细信息，请参阅如何通过[DNS Office Windows KMS和删除未经授权的实例](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。 
  
若要设置 KMS，请参阅[KMS 2013 Office 2013 和 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) KMS Active Directory Office [2013](/DeployOffice/vlactivation/gvlks)
  
Office Lync 的 2013 通用批量许可证密钥：2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (此密钥会导致 Skype 会议室系统查找网络上 KMS。) 
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>从批量 () VLSC) 中的多个激活密钥 (MAK) 

如果客户使用任何其他批量许可软件，IT 部门将使用 VLSC 管理软件激活和批量许可协议 (VLA) 许可证。 这还将使公司能够购买 Skype for Business VL 激活，之后公司可以获取 MAK 以在 Skype Room System Admin Console 中输入。
  
具有 VLA 的客户必须知道其 VLSC 凭据，这些凭据将用于管理协议和获取 MAK。 如果不确定，客户的财务部门应能够确认客户是否支付 VLA 费用。
  
若要获取 MAK，访问批量许可服务中心以查看协议，并下载 MAK (产品) 。 有关详细信息，请转到批量 [许可服务中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>没有 VLSC Microsoft 365或Office 365的 MAK

如果客户没有批量许可协议，Skype for Business激活将更加难以管理。 但是，Microsoft 365 VLSC Office 365的客户可以通过向销售该会议室系统的 OEM 提供以下信息来获取Skype MAK：
  
- 公司名称
    
- 部署联系人姓名、电子邮件和电话号码
    
- 已部署的系统数
    
- 部署日期
    
- 如果客户有 Microsoft 技术客户经理，则 TAM 的姓名和联系信息
