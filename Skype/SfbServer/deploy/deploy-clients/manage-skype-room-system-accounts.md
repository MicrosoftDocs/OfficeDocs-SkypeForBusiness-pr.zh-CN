---
title: 管理 Skype 会议室系统帐户
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: 阅读本主题，了解如何管理 Skype 会议室系统帐户。
ms.openlocfilehash: 2a45fc8507b9b09b777e6aa91c47fff2b3dfc3d2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234071"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="2a183-103">管理 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="2a183-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="2a183-104">阅读本主题，了解如何管理 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="2a183-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="2a183-105">Microsoft 团队聊天室是具有不同的依赖项和部署过程的其他产品。</span><span class="sxs-lookup"><span data-stu-id="2a183-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="2a183-106">有关 Microsoft 团队聊天室的信息, 请参阅 Microsoft 团队聊天室[管理概述](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="2a183-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="2a183-107">在池之间移动 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="2a183-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="2a183-108">如果需要将 Skype 会议室系统帐户从一个 Skype for business 服务器池移动到另一个 (例如, 在升级期间), 请使用以下命令移动 Skype 会议室系统帐户池:</span><span class="sxs-lookup"><span data-stu-id="2a183-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="2a183-109">禁用 Skype for business 服务的 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="2a183-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="2a183-110">如果您需要从 Skype for business 服务器池上的 Skype for Business 服务禁用现有 Skype 会议室系统帐户, 请使用以下命令禁用帐户:</span><span class="sxs-lookup"><span data-stu-id="2a183-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="2a183-111">可选: 在 Active Directory 中创建 Skype 会议室系统管理员组</span><span class="sxs-lookup"><span data-stu-id="2a183-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="2a183-112">加入域的每个 Skype 会议室系统客户都可以通过 Skype 会议室系统设备电脑上具有本地管理员权限的域用户进行完全管理。</span><span class="sxs-lookup"><span data-stu-id="2a183-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="2a183-113">因此, 你可以在 Active Directory 中创建一个专用管理员组, 并在设置新的 Skype 会议室系统计算机期间授予此组管理权限。</span><span class="sxs-lookup"><span data-stu-id="2a183-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

