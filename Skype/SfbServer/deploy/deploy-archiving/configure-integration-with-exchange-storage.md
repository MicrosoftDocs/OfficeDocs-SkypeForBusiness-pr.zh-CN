---
title: 配置与 Skype for Business Server 2015 的 Exchange 存储的集成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 摘要： 阅读本主题，以了解如何使用 Exchange 存储在 Skype 业务服务器 2015年配置集成。
ms.openlocfilehash: 2d814bb297999062aaf93160286031afec51c3a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server-2015"></a>配置与 Skype for Business Server 2015 的 Exchange 存储的集成
 
**摘要：**阅读本主题，以了解如何使用 Exchange 存储在 Skype 业务服务器 2015年配置集成。
  
如果部署中的所有用户使用 Microsoft Exchange 集成，您不需要为业务服务器归档策略，为您的用户配置 Skype。 相反，您可以配置支持归档的放在原位保存其邮箱上交换，驻留用户交换就地保存策略。 使用 Exchange 存储中配置集成之前，请阅读[存档业务服务器 2015年的 Skype 的计划](../../plan-your-deployment/archiving/archiving.md)。 有关 Exchange 就地保存策略的详细信息，请参阅 Exchange 产品文档。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>使用 Microsoft Exchange 存储配置集成

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档配置**”。
    
4. 单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，再单击“**显示详细信息**”，然后执行以下操作：
    
  - 要启用与 Exchange 存储集成，请选择**Microsoft Exchange 集成**复选框。
    
  - 要禁用与 Exchange 存储集成，请清除**Microsoft Exchange 集成**复选框。
    
5. 单击“**提交**”。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>当 Skype 业务服务器和 Microsoft Exchange 部署在不同的目录林

如果您使用 Microsoft Exchange 集成和 Microsoft Exchange Server 将不会部署在同一个林的 Skype 业务服务器，必须确保以下 Exchange Active Directory 属性将同步到林在 Skype 的部署企业服务器：
  
- msExchUserHoldPolicies
    
- 代理地址
    
这是一个多值属性。在同步此属性时，需要合并各个值（而不是将其替换）以确保现有值不会丢失。
  

