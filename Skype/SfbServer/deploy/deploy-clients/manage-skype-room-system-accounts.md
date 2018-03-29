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
ms.openlocfilehash: c47765b617e0856d1db25c7ed4902fe0af9924f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="9590f-103">管理 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="9590f-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="9590f-104">阅读本主题，了解如何管理 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="9590f-104">Read this topic to learn how to manage Skype Room System accounts.</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="9590f-105">池间移动的 Skype 的空间系统帐户</span><span class="sxs-lookup"><span data-stu-id="9590f-105">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="9590f-106">如果您需要在 Skype 的空间系统帐户在一个 Skype 业务服务器池之间移动 （例如，在升级期间），使用下面的命令将 Skype 的空间系统帐户池移动：</span><span class="sxs-lookup"><span data-stu-id="9590f-106">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="9590f-107">Skype 在 Skype 的空间系统帐户禁用业务服务</span><span class="sxs-lookup"><span data-stu-id="9590f-107">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="9590f-108">如果您需要禁用现有 Skype 的空间系统上的帐户从 Skype 业务服务 Skype 业务服务器池，请使用以下命令来禁用该帐户：</span><span class="sxs-lookup"><span data-stu-id="9590f-108">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="9590f-109">可选： 在活动目录中创建的 Skype 的空间系统管理员组</span><span class="sxs-lookup"><span data-stu-id="9590f-109">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="9590f-110">使用 Skype 的空间系统装置计算机上的本地管理员权限的域用户可以完全管理加入域每个 Skype 的空间系统客户端。</span><span class="sxs-lookup"><span data-stu-id="9590f-110">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="9590f-111">因此，可以在 Active Directory 中创建专用的管理员组，并且放弃此组的管理权限集中在新的 Skype 的空间系统计算机。</span><span class="sxs-lookup"><span data-stu-id="9590f-111">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

