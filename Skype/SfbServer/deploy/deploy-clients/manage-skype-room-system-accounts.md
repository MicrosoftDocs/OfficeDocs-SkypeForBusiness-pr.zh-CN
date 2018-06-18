---
title: 管理 Skype 会议室系统帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: 阅读本主题，了解如何管理 Skype 会议室系统帐户。
ms.openlocfilehash: 4d3535c9583481273f7a511143244b511cdb5819
ms.sourcegitcommit: 0f089f0c1bc641793c61928fb1c8fa62b2dfabee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2018
ms.locfileid: "19927786"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="552d2-103">管理 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="552d2-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="552d2-104">阅读本主题，了解如何管理 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="552d2-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="552d2-105">Skype 会议室系统 v2 是具有不同的依赖关系和部署过程的不同产品。</span><span class="sxs-lookup"><span data-stu-id="552d2-105">Skype Room Systems v2 is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="552d2-106">Skype 会议室系统 v2 的信息，请参阅 Skype 会议室系统 v2[管理概述](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="552d2-106">For information on Skype Room Systems v2, see the Skype Room Systems v2 [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="552d2-107">池之间移动 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="552d2-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="552d2-108">如果您需要 Skype 会议室系统帐户在一个 Skype 业务服务器池之间移动 （例如，在升级过程），请使用以下命令将 Skype 会议室系统帐户池：</span><span class="sxs-lookup"><span data-stu-id="552d2-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="552d2-109">Skype 业务服务禁用的 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="552d2-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="552d2-110">如果您需要禁用现有 Skype 会议室系统上的帐户从 Skype Business services Skype 业务服务器池，请使用以下命令禁用帐户：</span><span class="sxs-lookup"><span data-stu-id="552d2-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="552d2-111">可选： Active Directory 中创建的 Skype 会议室系统管理员组</span><span class="sxs-lookup"><span data-stu-id="552d2-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="552d2-112">通过使用 Skype 会议室系统装置 PC 上的本地管理员权限的域用户能完全管理加入到域每个 Skype 会议室系统客户端。</span><span class="sxs-lookup"><span data-stu-id="552d2-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="552d2-113">因此，您可以在 Active Directory 中创建专用的管理员组并放弃此组的管理权限期间设置新的 Skype 会议室系统计算机。</span><span class="sxs-lookup"><span data-stu-id="552d2-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

