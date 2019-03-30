---
title: 管理 Skype 会议室系统帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: 阅读本主题，了解如何管理 Skype 会议室系统帐户。
ms.openlocfilehash: 4c276d4acf0cf15df7689fa5c11a0e6e2cde785b
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012522"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="0be53-103">管理 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="0be53-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="0be53-104">阅读本主题，了解如何管理 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="0be53-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="0be53-105">Microsoft 团队聊天室是一种不同的产品具有不同的依赖项以及部署过程。</span><span class="sxs-lookup"><span data-stu-id="0be53-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="0be53-106">有关 Microsoft 团队聊天室的信息，请参阅 Microsoft 团队聊天室[管理概述](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="0be53-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="0be53-107">池之间移动 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="0be53-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="0be53-108">如果您需要 Skype 会议室系统帐户在一个 Skype 业务服务器池之间移动 （例如，在升级过程），请使用以下命令将 Skype 会议室系统帐户池：</span><span class="sxs-lookup"><span data-stu-id="0be53-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="0be53-109">Skype 业务服务禁用的 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="0be53-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="0be53-110">如果您需要禁用现有 Skype 会议室系统上的帐户从 Skype Business services Skype 业务服务器池，请使用以下命令禁用帐户：</span><span class="sxs-lookup"><span data-stu-id="0be53-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="0be53-111">可选： Active Directory 中创建的 Skype 会议室系统管理员组</span><span class="sxs-lookup"><span data-stu-id="0be53-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="0be53-112">通过使用 Skype 会议室系统装置 PC 上的本地管理员权限的域用户能完全管理加入到域每个 Skype 会议室系统客户端。</span><span class="sxs-lookup"><span data-stu-id="0be53-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="0be53-113">因此，您可以在 Active Directory 中创建专用的管理员组并放弃此组的管理权限期间设置新的 Skype 会议室系统计算机。</span><span class="sxs-lookup"><span data-stu-id="0be53-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

