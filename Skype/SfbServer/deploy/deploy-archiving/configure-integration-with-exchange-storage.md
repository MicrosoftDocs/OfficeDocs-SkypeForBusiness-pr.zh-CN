---
title: 配置与Exchange存储的Skype for Business Server
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
description: 摘要：阅读本主题，了解如何配置与 Exchange 存储的Skype for Business Server。
ms.openlocfilehash: e33c5fcfb4ff059a266abbd06f31674e753ba1efb16b094244cba4e1f333c098
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312090"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>配置与Exchange存储的Skype for Business Server
 
**摘要：** 阅读本主题，了解如何配置与 Exchange 存储的Skype for Business Server。
  
如果使用 Microsoft Exchange部署中所有用户集成，则无需为用户配置Skype for Business Server存档策略。 相反，您可以配置Exchange In-Place保留策略以支持对位于 Exchange 上的用户进行存档，其邮箱将置于In-Place保留状态。 配置与存储Exchange之前，请阅读规划[存档Skype for Business Server。](../../plan-your-deployment/archiving/archiving.md) 有关保留Exchange In-Place的详细信息，请参阅Exchange产品文档。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>配置与 Microsoft Exchange存储的集成

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。
    
4. 单击存档配置列表中相应的全局、站点或池配置的名称，单击“编辑”，再单击“显示详细信息”，然后执行以下操作：
    
   - 若要启用与存储Exchange集成，请选中 **"Microsoft Exchange集成"** 复选框。
    
   - 若要禁用与Exchange集成，请清除 **"Microsoft Exchange集成"** 复选框。
    
5. 单击“提交”。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>在不同Skype for Business Server部署 Exchange 和 Microsoft 服务器时

如果使用 Microsoft Exchange 集成，Microsoft Exchange Server 未部署在 Skype for Business Server 相同的林中，则必须确保将以下 Exchange Active Directory 属性同步到部署了 Skype for Business Server 的林：
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
这是一个多值属性。在同步此属性时，需要合并各个值（而不是将其替换）以确保现有值不会丢失。
  

