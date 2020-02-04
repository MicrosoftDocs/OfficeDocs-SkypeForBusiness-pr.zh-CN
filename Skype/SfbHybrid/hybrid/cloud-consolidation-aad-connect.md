---
title: 更新 AAD Connect 以包含多个林
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 此附录包括更新 AAD 连接的详细步骤，以包含多个林作为针对团队和 Skype for business 的云合并的一部分。
ms.openlocfilehash: 3d3d72c14957f0ed8932d95fcd2dbe9ec9c1e37e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696057"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>更新 AAD Connect 以包含多个林

Azure AD Connect 支持[来自多个林的同步](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies)。 但是，它仅支持 Azure AD Connect 同步到 AAD 的一个实例。 因此，在 Azure AD 已安装在一个林中的情况下，必须更新 AAD 连接的现有实例以从其他林同步。

 - 如果所有标识在两个林之间仅表示一次（即，您尚未创建任何启用邮件的联系人），则可以简单地重新运行 AAD 连接向导，选择 "自定义同步选项"，然后在 "**连接目录**" 页上，输入其他林和凭据的名称。<br><br>
 !["连接目录" 页](../media/cloud-consolidation-connect-your-directories.png)
 - 但是，如果用户可以存在于多个目录中，并且你将合并数据（例如，如果联系人对象存在于与另一个林中的用户相对应的林中），你将需要卸载 Azure AD Connect 并重新安装它。  这是因为跨林连接规则条件只能在第一次安装过程中进行配置。 这是在以下页面上完成的：<br><br>
 ![唯一标识用户页面](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>另请参阅

[针对团队和 Skype for Business 的云整合](cloud-consolidation.md)