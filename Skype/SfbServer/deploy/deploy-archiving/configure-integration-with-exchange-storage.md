---
title: 配置集成与 Exchange 存储的 Skype 业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 摘要： 阅读本主题可了解如何为业务 Server 与 Exchange 存储中 Skype 配置集成。
ms.openlocfilehash: b60924d351114a088910795ec0eb43aa1ed7972f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891872"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>配置集成与 Exchange 存储的 Skype 业务服务器
 
**摘要：** 阅读本主题可了解如何为业务 Server 与 Exchange 存储中 Skype 配置集成。
  
如果部署中的所有用户使用 Microsoft Exchange 集成，您无需配置 Skype 的业务服务器存档策略的用户。 而是您配置 Exchange 就地保留策略以支持存档的用户驻留在 Exchange，使用他们的邮箱置于就地保留。 与 Exchange 存储配置集成之前，请阅读[Plan for Business Server 的 Skype 的存档](../../plan-your-deployment/archiving/archiving.md)。 有关 Exchange 就地保留策略的详细信息，请参阅 Exchange 产品文档。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>配置与 Microsoft Exchange 存储的集成

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。
    
4. 单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，再单击“**显示详细信息**”，然后执行以下操作：
    
   - 若要启用与 Exchange 存储的集成，请选择**Microsoft Exchange 集成**复选框。
    
   - 若要禁用与 Exchange 存储的集成，请清除**Microsoft Exchange 集成**复选框。
    
5. 单击“**提交**”。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Skype Business Server 和 Microsoft Exchange 部署在不同的林中的时

如果您使用 Microsoft Exchange 集成和业务服务器中，将 Microsoft Exchange Server 不部署在同一个林中 Skype，您必须确保以下 Exchange Active Directory 属性同步到林其中的 Skype部署企业服务器：
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
这是一个多值属性。在同步此属性时，需要合并各个值（而不是将其替换）以确保现有值不会丢失。
  

