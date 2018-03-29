---
title: Skype 的空间系统 Skype 业务软件许可证
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 阅读本主题，了解如何检查你是否拥有 Skype for Business 软件批量许可证。
ms.openlocfilehash: e91a009c29647031d91e791ba5fd41ccc4578d1e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype 会议室系统：Skype for Business 软件许可证
 
阅读本主题，了解如何检查你是否拥有 Skype for Business 软件批量许可证。 
  
Skype 的空间系统对业务客户端，这需要软件批量许可证使用已安装的 Skype。 在部署之前第一个 Skype 的空间系统，查明卷许可证状态的部署-使用密钥管理服务器 (KMS) 或多次激活密钥 (MAK)。
  
## <a name="key-management-servers-kms"></a>密钥管理服务器 (KMS)

如果 KMS 均已到位，并将分发 Skype 业务批量许可证激活，Skype 的空间系统将自动激活业务客户端的 Skype。 要了解 KMS 是否准备就绪，请执行以下操作：
  
从命令提示符处，运行：`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
有关详细信息，请参阅[如何发现通过 DNS 的 Office 和 Windows KMS 主机并删除未经授权的实例](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。 
  
若要设置 KMS，看到[KMS 激活 Office 2013](https://technet.microsoft.com/en-us/library/ee624357.aspx)和[KMS 以及 Active Directory 激活 Office 2013 GVLKs](https://technet.microsoft.com/en-us/library/dn385360.aspx)
  
Lync 为 office 2013 一般批量许可证密钥： 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R （此项将使 Skype 空间系统来查找网络上 KMS）。
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>来自批量许可服务中心 (VLSC) 的多次激活密钥 (MAK)

如果客户使用任何其他批量许可证软件，则 IT 部门将使用 VLSC 管理软件激活和批量许可协议 (VLA)。 这还将使公司业务 VL 激活，其后该公司可以获得在 Skype 的空间系统管理控制台输入 MAK 购买 Skype。
  
具有 VLA 的客户必须知道其 VLSC 凭据，将使用这些凭据来管理协议和获取 MAK。 如果不确定的客户的财务部门应能够确认如果客户支付 VLA。
  
要获得 MAK，请访问批量许可服务中心以查看协议并下载产品密钥 (MAK)。 有关详细信息，请转到[卷授权服务中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>适用于 Office 365、不含 VLSC 访问的 MAK

如果客户没有批量许可协议，Skype 业务激活将更难以管理。 但是，Office 365 客户无需负责管理对于 VLSC 访问可以获得促销 MAK 通过为 OEM 提供以下信息销售 Skype 的空间系统：
  
- 公司名称
    
- 部署联系人姓名、电子邮件和电话号码
    
- 部署的系统的数量
    
- 部署日期
    
- 如果客户有 Microsoft 技术客户经理，TAM 的名称和联系信息
    

