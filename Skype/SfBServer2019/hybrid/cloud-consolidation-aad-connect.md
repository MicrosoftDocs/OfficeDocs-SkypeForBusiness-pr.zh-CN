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
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="4c67d-103">更新 AAD 连接到包含多个林</span><span class="sxs-lookup"><span data-stu-id="4c67d-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="4c67d-104">Azure AD 连接支持[从多个林同步](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies)。</span><span class="sxs-lookup"><span data-stu-id="4c67d-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="4c67d-105">但是，它支持 Azure AD 连接同步到 AAD 只有一个的实例。</span><span class="sxs-lookup"><span data-stu-id="4c67d-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="4c67d-106">因此，在 Azure AD 其中已安装在一个林中的情况下，AAD 连接的现有实例必须更新到其他林中的同步。</span><span class="sxs-lookup"><span data-stu-id="4c67d-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="4c67d-107">如果所有标识仅执行一次都表示跨两个林 （即您没有指定任何启用邮件的联系人），那么您可以只需重新运行 AAD 连接向导中，选择"自定义同步选项，"然后连接**中的您的目录**页上，输入的其他林和凭据设置的名称。</span><span class="sxs-lookup"><span data-stu-id="4c67d-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="4c67d-108">![连接目录页](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="4c67d-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="4c67d-109">但是，如果用户可位于超过一个目录，并将合并数据 （例如，如果联系人对象存在对应于另一个林中的用户林中），您将需要卸载 Azure AD 连接并重新安装它。</span><span class="sxs-lookup"><span data-stu-id="4c67d-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="4c67d-110">这是因为只能在第一台安装过程中配置跨林联接规则条件。</span><span class="sxs-lookup"><span data-stu-id="4c67d-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="4c67d-111">这是在以下页面：</span><span class="sxs-lookup"><span data-stu-id="4c67d-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="4c67d-112">![用于唯一地标识用户页面](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="4c67d-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="4c67d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c67d-113">See also</span></span>

[<span data-ttu-id="4c67d-114">云整合个团队和 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4c67d-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)