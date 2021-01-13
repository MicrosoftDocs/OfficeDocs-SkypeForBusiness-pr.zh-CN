---
title: 为 Skype for Business Server 配置与 Exchange 存储的集成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 中配置与 Exchange 存储的集成。
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825062"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>为 Skype for Business Server 配置与 Exchange 存储的集成
 
**摘要：** 阅读本主题，了解如何在 Skype for Business Server 中配置与 Exchange 存储的集成。
  
如果在部署中为所有用户使用 Microsoft Exchange 集成，则无需为用户配置 Skype for Business Server 存档策略。 相反，您可以配置 Exchange In-Place 保留策略以支持对 Exchange 上用户进行存档，其邮箱将置于In-Place保留状态。 配置与 Exchange 存储的集成之前，请阅读 [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md)。 有关 Exchange In-Place保留策略的详细信息，请参阅 Exchange 产品文档。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>配置与 Microsoft Exchange 存储的集成

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。
    
4. 单击存档配置列表中相应的全局、站点或池配置的名称，单击“编辑”，再单击“显示详细信息”，然后执行以下操作：
    
   - 若要启用与 Exchange 存储的集成，请选中 **Microsoft Exchange 集成** 复选框。
    
   - 若要禁用与 Exchange 存储的集成，请清除 **Microsoft Exchange 集成** 复选框。
    
5. 单击“提交”。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>当 Skype for Business Server 和 Microsoft Exchange 部署在不同的林中时

如果使用 Microsoft Exchange 集成，Microsoft Exchange Server未部署在 Skype for Business Server 的同一林中，则必须确保将以下 Exchange Active Directory 属性同步到部署 Skype for Business Server 的林：
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
这是一个多值属性。在同步此属性时，需要合并各个值（而不是将其替换）以确保现有值不会丢失。
  

