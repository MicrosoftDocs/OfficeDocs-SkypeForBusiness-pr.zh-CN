---
title: Skype 会议室系统 Skype for business 软件许可证
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 阅读本主题，了解如何检查你是否拥有 Skype for Business 软件批量许可证。
ms.openlocfilehash: 15f768de96d65cd8584ceb2529b92892a7a94afe
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774813"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype 会议室系统：Skype for Business 软件许可证
 
阅读本主题，了解如何检查你是否拥有 Skype for Business 软件批量许可证。 
  
Skype 会议室系统使用已安装的 Skype for Business 客户端，该客户端需要软件批量许可证。 在部署第一个 Skype 会议室系统之前，请使用密钥管理服务器（KMS）或多个激活密钥（MAK）查看部署的批量许可证状态。
  
## <a name="key-management-servers-kms"></a>密钥管理服务器 (KMS)

如果 KMS 已到位并且将分配 Skype for business 批量许可证激活，则 Skype 会议室系统将自动激活 Skype for business 客户端。 要了解 KMS 是否准备就绪，请执行以下操作：
  
从命令提示符处，运行：`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
有关详细信息，请参阅[如何通过 DNS 发现 Office 和 WINDOWS KMS 主机并删除未经授权的实例](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。 
  
若要设置 KMS，请参阅适用于 KMS 的[office 2013](https://technet.microsoft.com/library/ee624357.aspx)和 GVLKs 的 kms 激活和[Office 2013 的 Active Directory 激活](https://technet.microsoft.com/library/dn385360.aspx)
  
适用于 Lync 的 Office 2013 常规批量许可证密钥： 2MG3G-3BNTT-3MFW9 （此键使 Skype 会议室系统在网络上查找 KMS。）
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>来自批量许可服务中心 (VLSC) 的多次激活密钥 (MAK)

如果客户使用任何其他批量许可证软件，则 IT 部门将使用 VLSC 管理软件激活和批量许可协议 (VLA)。 这还将使公司能够购买 Skype for business VL 激活，在此期间，公司可以在 Skype 会议室系统管理控制台中获取 MAK 进行输入。
  
具有 VLA 的客户必须知道其 VLSC 凭据，将使用这些凭据来管理协议和获取 MAK。 如果不确定，客户的财务部门应该能够确认客户是否已支付 VLA。
  
要获得 MAK，请访问批量许可服务中心以查看协议并下载产品密钥 (MAK)。 有关详细信息，请转到[批量许可服务中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>适用于 Office 365、不含 VLSC 访问的 MAK

如果客户没有批量许可协议，则 Skype for Business 激活的管理难度将大大增加。 但是，没有 VLSC 访问权限的 Office 365 客户可以通过向 OEM 销售 Skype 会议室系统提供以下信息来获取促销 MAK：
  
- 公司名称
    
- 部署联系人姓名、电子邮件和电话号码
    
- 部署的系统数
    
- 部署日期
    
- 如果客户有 Microsoft 技术客户经理，TAM 的姓名和联系人信息
    

