---
title: Skype 会议室系统 Skype for Business 软件许可证
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 阅读本主题，了解如何检查你是否拥有 Skype for Business 软件批量许可证。
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220922"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype 会议室系统： Skype for Business 软件许可证
 
阅读本主题，了解如何检查你是否拥有 Skype for Business 软件批量许可证。 
  
Skype 会议室系统使用已安装的 Skype for Business 客户端，这需要软件批量许可证。 在部署第一个 Skype 会议室系统之前，请使用密钥管理服务器（KMS）或多次激活密钥（MAK）查找部署的批量许可证状态。
  
## <a name="key-management-servers-kms"></a>密钥管理服务器（KMS）

如果 KMS 已就绪，并将分发 Skype for Business 批量许可证激活，Skype 会议室系统将自动激活 Skype for Business 客户端。 若要查明 KMS 是否就绪，请执行以下操作：
  
在命令提示符处，运行：`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
有关详细信息，请参阅[如何通过 DNS 发现 Office 和 WINDOWS KMS 主机并删除未授权的实例](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。 
  
若要设置 KMS，请参阅[kms activation Of office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [gvlk For Kms 和 Active Directory activation of office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
适用于 Lync 的 Office 2013 通用批量许可证密钥： 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R （此项会导致 Skype 会议室系统在网络上查找 KMS）。
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>批量许可证服务中心（VLSC）的多个激活密钥（MAK）

如果客户使用任何其他批量许可证软件，IT 部门将使用 VLSC 管理软件激活和批量许可协议（VLA）。 这还将使公司能够购买 Skype for business VL 激活，之后公司可以在 Skype 会议室系统管理控制台中获取 MAK 以进行输入。
  
具有 VLA 的客户必须知道其 VLSC 凭据，这将用于管理协议和获取 MAK。 如果不确定，客户的财务部门应能够确认客户是否已支付 VLA。
  
若要获取 MAK，请访问批量许可服务中心以查看协议和下载产品密钥（MAK）。 有关详细信息，请转到[批量许可服务中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>不使用 VLSC 访问的适用于 Microsoft 365 或 Office 365 的 MAK

如果客户没有批量许可协议，Skype for Business 激活的管理难度将大大增加。 但是，没有 VLSC 访问权限的 Microsoft 365 和 Office 365 客户可以通过向 OEM 销售 Skype 会议室系统提供以下信息来获取促销 MAK：
  
- 公司名称
    
- 部署联系人姓名、电子邮件和电话号码
    
- 部署的系统数量
    
- 部署日期
    
- 如果客户有 Microsoft 技术客户经理，TAM 的姓名和联系人信息
    

