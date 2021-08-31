---
title: 将 AAD Connect 更新为包含多个林
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
ms.localizationpriority: medium
description: 此附录包括有关更新 AAD 连接以将多个林作为云合并的一部分以用于 Teams 和 Skype for Business。
ms.openlocfilehash: 261085c85b9b3114bce49216e7b63173cd37d55e
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731881"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>将 AAD Connect 更新为包含多个林

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Azure AD 连接[支持从多个林同步](/azure/active-directory/connect/active-directory-aadconnect-topologies)。 但是，它仅支持一个 Azure AD 连接同步到 AAD。 因此，如果 Azure AD 已安装在一个林中，则必须更新现有 AAD 连接，以从其他林同步。

 - 如果所有标识仅跨两个林 (表示一次，即，您尚未创建任何启用邮件的联系人) ，则只需重新运行 AAD 连接 向导，选择"自定义同步选项"，然后在 **"连接** 您的目录"页上，输入其他林的名称和 creds。<br><br>
 ![the 连接 your directories page.](../media/cloud-consolidation-connect-your-directories.png)
 - 但是，如果用户可以存在于多个目录中，并且你要合并数据 (例如，如果与另一个林) 中的用户对应的林中存在联系对象，则需要卸载 Azure AD 连接 并重新安装它。  这是因为跨林加入规则条件只能在首次安装过程中配置。 此操作在下面的页面上完成：<br><br>
 ![唯一标识用户页面。](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>另请参阅

[云合并Teams和Skype for Business](cloud-consolidation.md)