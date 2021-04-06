---
title: 停用本地 Skype for Business 环境
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 有关如何停用本地 Skype for Business 环境的说明。
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593875"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a><span data-ttu-id="9eb81-103">停用本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="9eb81-103">Decommission your on-premises Skype for Business environment</span></span>

<span data-ttu-id="9eb81-104">如果你的组织将 Teams 或 Skype for Business Online 与 Skype for Business Server 本地部署一同使用，你可以将这些环境完全迁移到云，然后停用 Skype for Business Server 本地部署。</span><span class="sxs-lookup"><span data-stu-id="9eb81-104">If your organization uses Teams or Skype for Business Online with an on-premises deployment of Skype for Business Server, you can migrate these environments fully to the cloud, and then retire your on-premises deployment of Skype for Business Server.</span></span> 

> [!NOTE]
> <span data-ttu-id="9eb81-105">在停用本地环境之前 [，必须在本地](configure-hybrid-connectivity.md) 部署和 Microsoft 365 之间配置混合连接。</span><span class="sxs-lookup"><span data-stu-id="9eb81-105">Before decommissioning your on-premises environment, you must [configure hybrid connectivity](configure-hybrid-connectivity.md) between your on-premises deployment and Microsoft 365.</span></span> <span data-ttu-id="9eb81-106">配置混合连接后，你可以将用户迁移到云，同时从本地迁移他们的会议，以及将任何联系人从 Skype for Business Server 迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="9eb81-106">After configuring hybrid connectivity, you can migrate users to the cloud, while migrating their meetings from on-premises, and migrating any contacts from Skype for Business Server to Teams.</span></span> <span data-ttu-id="9eb81-107">配置混合连接是将用户从本地迁移到云并确保 Teams 完整功能所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="9eb81-107">Configuring hybrid connectivity is a required step to migrate users from on-premises to the cloud and to ensure full Teams functionality.</span></span>

<span data-ttu-id="9eb81-108">若要完成从本地到云的迁移并停止使用本地 Skype for Business Server 环境，必须按以下顺序完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="9eb81-108">To complete your move from on-premises to the cloud and decommission your on-premises Skype for Business Server environment, you must complete the following steps in the following order:</span></span>

- <span data-ttu-id="9eb81-109">**步骤 1.**</span><span class="sxs-lookup"><span data-stu-id="9eb81-109">**Step 1.**</span></span> <span data-ttu-id="9eb81-110">[将所有必需的用户和应用程序终结点从本地移动到联机](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="9eb81-110">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="9eb81-111">**步骤 2.**</span><span class="sxs-lookup"><span data-stu-id="9eb81-111">**Step 2.**</span></span> <span data-ttu-id="9eb81-112">[禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="9eb81-112">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="9eb81-113">**步骤 3.**</span><span class="sxs-lookup"><span data-stu-id="9eb81-113">**Step 3.**</span></span> <span data-ttu-id="9eb81-114">[删除本地 Skype for Business 部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="9eb81-114">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

