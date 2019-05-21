---
title: 配置与 Skype for business Server 的 Exchange 存储的集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '摘要: 阅读本主题, 了解如何在 Skype for Business Server 中配置与 Exchange 存储的集成。'
ms.openlocfilehash: b58aa090e4e6c51beb1f99ba5dc9020e029c8c39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286423"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>配置与 Skype for business Server 的 Exchange 存储的集成
 
**摘要:** 阅读本主题, 了解如何在 Skype for Business Server 中配置与 Exchange 存储的集成。
  
如果你对部署中的所有用户使用 Microsoft Exchange 集成, 则无需为你的用户配置 Skype for Business 服务器存档策略。 而是配置 Exchange 就地保留策略以支持驻留在 Exchange 上的用户的存档, 并将其邮箱置于就地保留。 在配置与 Exchange 存储的集成之前, 请阅读[Skype For Business Server 中的存档计划](../../plan-your-deployment/archiving/archiving.md)。 有关 Exchange 现场保留策略的详细信息, 请参阅 Exchange 产品文档。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>配置与 Microsoft Exchange 存储的集成

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。
    
4. 单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，再单击“**显示详细信息**”，然后执行以下操作：
    
   - 若要启用与 Exchange 存储的集成, 请选中 " **Microsoft Exchange 集成**" 复选框。
    
   - 若要禁用与 Exchange 存储的集成, 请清除 " **Microsoft Exchange 集成**" 复选框。
    
5. 单击“**提交**”。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>当 Skype for Business 服务器和 Microsoft Exchange 部署在不同的林中时

如果你使用的是 Microsoft Exchange 集成, 并且 Microsoft Exchange Server 不是与 Skype for Business Server 在同一林中部署的, 则必须确保以下 Exchange Active Directory 属性已同步到 Skype for business 的林已部署企业服务器:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
这是一个多值属性。在同步此属性时，需要合并各个值（而不是将其替换）以确保现有值不会丢失。
  

