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
localization_priority: Normal
description: 此附录包括更新 AAD Connect 以包括多个林的详细步骤，作为 Teams 和 Skype for Business 云整合的一部分。
ms.openlocfilehash: 19b761f3b64caf7afad7d37a51ae391e23d6b5ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120371"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="36882-103">将 AAD Connect 更新为包含多个林</span><span class="sxs-lookup"><span data-stu-id="36882-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="36882-104">Azure AD Connect [支持从多个林同步](/azure/active-directory/connect/active-directory-aadconnect-topologies)。</span><span class="sxs-lookup"><span data-stu-id="36882-104">Azure AD Connect supports [syncing from multiple forests](/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="36882-105">但是，它仅支持与 AAD 同步的 Azure AD Connect 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="36882-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="36882-106">因此，如果 Azure AD 已安装在一个林中，则必须更新 AAD Connect 的现有实例，以从其他林同步。</span><span class="sxs-lookup"><span data-stu-id="36882-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="36882-107">如果所有标识仅跨两个林 (表示一次，即，您尚未创建任何启用邮件的联系人) ，则只需重新运行 AAD Connect 向导，选择"自定义同步选项"，然后在"连接 **目录** "页上，输入其他林和林的名称。</span><span class="sxs-lookup"><span data-stu-id="36882-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="36882-108">!["连接目录"页](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="36882-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="36882-109">但是，如果用户可以存在于多个目录中，并且你将合并数据 (例如，如果与另一个林) 中的用户对应的林中存在联系对象，则需要卸载 Azure AD Connect 并重新安装它。</span><span class="sxs-lookup"><span data-stu-id="36882-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="36882-110">这是因为跨林加入规则条件只能在首次安装过程中配置。</span><span class="sxs-lookup"><span data-stu-id="36882-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="36882-111">此操作在下面的页面上完成：</span><span class="sxs-lookup"><span data-stu-id="36882-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="36882-112">![唯一标识用户页面](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="36882-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="36882-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36882-113">See also</span></span>

[<span data-ttu-id="36882-114">Teams 和 Skype for Business 云合并</span><span class="sxs-lookup"><span data-stu-id="36882-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)