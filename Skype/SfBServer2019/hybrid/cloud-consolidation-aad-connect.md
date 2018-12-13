---
title: 更新 AAD 连接到包含多个林
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本附录中包括用于更新 AAD 连接到云整合个团队和 Skype for Business 的一部分包括多个林的详细的步骤。
ms.openlocfilehash: d7229d54c159f7e07a233636f1576830e667dce5
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247625"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>更新 AAD 连接到包含多个林

Azure AD 连接支持[从多个林同步](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies)。 但是，它支持 Azure AD 连接同步到 AAD 只有一个的实例。 因此，在 Azure AD 其中已安装在一个林中的情况下，AAD 连接的现有实例必须更新到其他林中的同步。

 - 如果所有标识仅执行一次都表示跨两个林 （即您没有指定任何启用邮件的联系人），那么您可以只需重新运行 AAD 连接向导中，选择"自定义同步选项，"然后连接**中的您的目录**页上，输入的其他林和凭据设置的名称。<br><br>
 ![连接目录页](../media/cloud-consolidation-connect-your-directories.png)
 - 但是，如果用户可位于超过一个目录，并将合并数据 （例如，如果联系人对象存在对应于另一个林中的用户林中），您将需要卸载 Azure AD 连接并重新安装它。  这是因为只能在第一台安装过程中配置跨林联接规则条件。 这是在以下页面：<br><br>
 ![用于唯一地标识用户页面](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>另请参阅

[云整合个团队和 Skype for Business](cloud-consolidation.md)