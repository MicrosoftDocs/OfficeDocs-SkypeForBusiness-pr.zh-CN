---
title: 管理 Skype 会议室系统账户
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: 阅读本主题，了解如何管理 Skype 会议室系统帐户。
ms.openlocfilehash: fe6438934fa8fffabbc73c96ac00fd7844b51e14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805552"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="28282-103">管理 Skype 会议室系统账户</span><span class="sxs-lookup"><span data-stu-id="28282-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="28282-104">阅读本主题，了解如何管理 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="28282-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="28282-105">Microsoft Teams 会议室是具有不同的依赖项和部署过程的不同产品。</span><span class="sxs-lookup"><span data-stu-id="28282-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="28282-106">有关 Microsoft Teams 会议室的信息，请参阅 Microsoft Teams 会议室 [管理概述](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)。</span><span class="sxs-lookup"><span data-stu-id="28282-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="28282-107">在池之间移动 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="28282-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="28282-108">如果需要将 Skype 会议室系统帐户从一个 Skype for Business Server 池移动到另一个 (例如，在升级) 期间，请使用以下命令移动 Skype 会议室系统帐户池：</span><span class="sxs-lookup"><span data-stu-id="28282-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="28282-109">禁用 Skype for Business 服务的 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="28282-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="28282-110">如果需要从 Skype for Business Server 池上的 Skype for Business 服务禁用现有 Skype 会议室系统帐户，请使用以下命令禁用该帐户：</span><span class="sxs-lookup"><span data-stu-id="28282-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="28282-111">可选：在 Active Directory 中创建 Skype 会议室系统管理员组</span><span class="sxs-lookup"><span data-stu-id="28282-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="28282-112">加入域的每个 Skype 会议室系统客户端都可以由在 Skype 会议室系统设备电脑上具有本地管理员权限的域用户完全管理。</span><span class="sxs-lookup"><span data-stu-id="28282-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="28282-113">因此，可以在 Active Directory 中创建专用管理员组，在设置新的 Skype 会议室系统计算机期间授予此组管理权限。</span><span class="sxs-lookup"><span data-stu-id="28282-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

