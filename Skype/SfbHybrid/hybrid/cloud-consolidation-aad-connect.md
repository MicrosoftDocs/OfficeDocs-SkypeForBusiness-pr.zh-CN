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
ms.openlocfilehash: a61a45c8a492afd761f8cc6b1020b591851645b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049094"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="c9b73-103">更新 AAD Connect 以包含多个林</span><span class="sxs-lookup"><span data-stu-id="c9b73-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="c9b73-104">Azure AD Connect 支持[来自多个林的同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies)。</span><span class="sxs-lookup"><span data-stu-id="c9b73-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="c9b73-105">但是，它仅支持 Azure AD Connect 同步到 AAD 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="c9b73-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="c9b73-106">因此，在 Azure AD 已安装在一个林中的情况下，必须更新 AAD 连接的现有实例以从其他林同步。</span><span class="sxs-lookup"><span data-stu-id="c9b73-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="c9b73-107">如果所有标识在两个林之间仅表示一次（即，您尚未创建任何启用邮件的联系人），则可以简单地重新运行 AAD 连接向导，选择 "自定义同步选项"，然后在 "**连接目录**" 页上，输入其他林和凭据的名称。</span><span class="sxs-lookup"><span data-stu-id="c9b73-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="c9b73-108">!["连接目录" 页](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="c9b73-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="c9b73-109">但是，如果用户可以存在于多个目录中，并且你将合并数据（例如，如果联系人对象存在于与另一个林中的用户相对应的林中），你将需要卸载 Azure AD Connect 并重新安装它。</span><span class="sxs-lookup"><span data-stu-id="c9b73-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="c9b73-110">这是因为跨林连接规则条件只能在第一次安装过程中进行配置。</span><span class="sxs-lookup"><span data-stu-id="c9b73-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="c9b73-111">这是在以下页面上完成的：</span><span class="sxs-lookup"><span data-stu-id="c9b73-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="c9b73-112">![唯一标识用户页面](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="c9b73-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="c9b73-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9b73-113">See also</span></span>

[<span data-ttu-id="c9b73-114">针对团队和 Skype for Business 的云整合</span><span class="sxs-lookup"><span data-stu-id="c9b73-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)