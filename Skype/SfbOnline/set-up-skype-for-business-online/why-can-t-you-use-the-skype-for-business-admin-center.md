---
title: 为什么我当前无法使用 Skype for Business Online 管理中心？
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- Setup
- ms.lync.lac.TenantInMigration
description: '了解在将服务迁移到其他 Microsoft 数据中心时，Skype for Business管理中心中可以使用的功能和其他功能。 '
ms.openlocfilehash: 725a60be96a2d61bcec6367e1a0a33f2bc5dcee6
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238913"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="0a94b-103">为什么我当前无法使用 Skype for Business Online 管理中心？</span><span class="sxs-lookup"><span data-stu-id="0a94b-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="0a94b-104">[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]?</span><span class="sxs-lookup"><span data-stu-id="0a94b-104">[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]?</span></span>

<span data-ttu-id="0a94b-105">我们知道当你无法完成工作时，这非常令人沮丧，因此我们将解释此处发生的情况以及为什么值得等待。</span><span class="sxs-lookup"><span data-stu-id="0a94b-105">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="0a94b-106">首先，下面是技术说明：</span><span class="sxs-lookup"><span data-stu-id="0a94b-106">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="0a94b-107">我们正在将你的 Skype for Business Online 服务 (这意味着你的用户和组织) 迁移到离你更近的另一个 Microsoft 数据中心。</span><span class="sxs-lookup"><span data-stu-id="0a94b-107">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="0a94b-108">这将改进服务并减少延迟。</span><span class="sxs-lookup"><span data-stu-id="0a94b-108">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="0a94b-109">有关更多技术详细信息，请参阅 [移动数据期间和之后]( https://go.microsoft.com/fwlink/?LinkId=526418)。</span><span class="sxs-lookup"><span data-stu-id="0a94b-109">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="0a94b-110">好的，这意味着什么？</span><span class="sxs-lookup"><span data-stu-id="0a94b-110">OK, so what does that mean?</span></span>

<span data-ttu-id="0a94b-111">首先，让我们分解几个术语。</span><span class="sxs-lookup"><span data-stu-id="0a94b-111">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="0a94b-112">**数据中心** 这是存储来自用户或Microsoft 365 Office 365（如文件和电子邮件）的物理位置。</span><span class="sxs-lookup"><span data-stu-id="0a94b-112">**Data center** This is the physical location where the information from your Microsoft 365 or Office 365 is stored, such as your files and email messages.</span></span> <span data-ttu-id="0a94b-113">如果确实想要深入了解数据中心Microsoft 365 Office 365，请查看[此文](https://www.microsoft.com/online/legal/v2/?docid=25)。</span><span class="sxs-lookup"><span data-stu-id="0a94b-113">If you really want to dig in to what Microsoft 365 and Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="0a94b-114">**迁移** 这几乎与"移动"相同。</span><span class="sxs-lookup"><span data-stu-id="0a94b-114">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="0a94b-115">在这种情况下，这意味着我们将你的 Skype for Business Online 用户和设置从一个数据中心移动到离你更近的另一个数据中心，以改进你的服务。</span><span class="sxs-lookup"><span data-stu-id="0a94b-115">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="0a94b-116">**延迟** 这是访问管理中心、更改设置Microsoft 365保存这些更改所花的时间。</span><span class="sxs-lookup"><span data-stu-id="0a94b-116">**Latency** This is amount of time it takes you to access the Microsoft 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="0a94b-117">**关联 ID** 你可能在刚刚收到的邮件中看到了此内容。</span><span class="sxs-lookup"><span data-stu-id="0a94b-117">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="0a94b-118">Microsoft 支持工程师使用此信息来帮助你排查错误。</span><span class="sxs-lookup"><span data-stu-id="0a94b-118">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="0a94b-119">如果联系 Microsoft 支持部门，系统可能会要求你提供相关 ID。</span><span class="sxs-lookup"><span data-stu-id="0a94b-119">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="0a94b-120">因此，这意味着我们正在将你的所有联机Skype for Business和服务设置移动到离你更近的另一个位置。</span><span class="sxs-lookup"><span data-stu-id="0a94b-120">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="0a94b-121">越接近越好。</span><span class="sxs-lookup"><span data-stu-id="0a94b-121">The closer the better.</span></span> <span data-ttu-id="0a94b-122">好消息是，经过这一短暂的一段时间后，Skype for Business联机服务将会改善。</span><span class="sxs-lookup"><span data-stu-id="0a94b-122">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![服务迁移Microsoft 365或Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="0a94b-124">哪些 Skype for Business Online 功能仍可使用？</span><span class="sxs-lookup"><span data-stu-id="0a94b-124">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="0a94b-125">虽然无法访问 Skype for Business Online 管理中心，但以下 Skype for Business Online 功能在迁移期间仍正常工作：</span><span class="sxs-lookup"><span data-stu-id="0a94b-125">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="0a94b-126">联机会议</span><span class="sxs-lookup"><span data-stu-id="0a94b-126">Online meetings</span></span>
    
- <span data-ttu-id="0a94b-127">状态信息</span><span class="sxs-lookup"><span data-stu-id="0a94b-127">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="0a94b-128">我能否完成其他工作？</span><span class="sxs-lookup"><span data-stu-id="0a94b-128">Can I get other work done?</span></span>

<span data-ttu-id="0a94b-129">当然可以。</span><span class="sxs-lookup"><span data-stu-id="0a94b-129">Sure.</span></span> <span data-ttu-id="0a94b-130">在迁移 Skype for Business Online 服务时，仍可以使用 Microsoft 365 (中的其他管理中心，例如 Microsoft 365 Exchange 管理) 。</span><span class="sxs-lookup"><span data-stu-id="0a94b-130">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Microsoft 365 (for example, the Microsoft 365 and Exchange admin centers).</span></span> <span data-ttu-id="0a94b-131">但是，除了 Skype for Business Online 管理中心外，在迁移期间Skype for Business远程 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0a94b-131">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="0a94b-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="0a94b-132">Related topics</span></span>
[<span data-ttu-id="0a94b-133">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0a94b-133">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="0a94b-134">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="0a94b-134">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
