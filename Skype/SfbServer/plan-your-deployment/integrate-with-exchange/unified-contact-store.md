---
title: 在 Skype for Business Server 中规划统一联系人存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 6/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: 摘要：在计划将 Skype for Business Server 与 Exchange 2013 集成时，请查看本主题。
ms.openlocfilehash: 3ce06118f8225e78c5c84a8f9124e4815f79d593
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816252"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中规划统一联系人存储
 
**摘要：** 在计划将 Skype for Business Server 与 Exchange 2013 或 Exchange 2016 集成时，请查看本主题。
  
统一联系人存储跨 Microsoft Office 产品提供一致的联系人体验，并使用户能够在 Exchange 2013 中存储所有联系人信息，但允许信息跨 Skype for Business、Exchange、Outlook 和 Outlook Web Access 全局提供。
  
## <a name="requirements-for-unified-contact-store"></a>统一联系人存储的要求

若要在 Skype for Business Server 中实现统一的联系人存储，
  
- 必须运行 Skype for Business Server 和 Exchange 2013 或 2016。
    
- 用户必须使用 Skype for Business 将其联系人从 Skype for Business Server 迁移到 Exchange 2013 或 2016。
    
- 用户邮箱必须迁移到 Exchange 2013。
    
- 必须在 Skype for Business Server 和 Exchange 2013 或 Exchange 2016 之间配置服务器到服务器身份验证。
    
    > [!NOTE]
    > 有关在 Skype for Business Server 和 Exchange 2013 或 Exchange 2016 之间设置身份验证的详细要求，请参阅操作文档中的"管理服务器到服务器身份验证 [ (OAuth) ](../../manage/authentication/server-to-server-and-partner-applications.md) 和 Skype for Business Server 中的合作伙伴应用程序"。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中部署统一的联系人存储](../../deploy/deploy-unified-contact-store.md)
