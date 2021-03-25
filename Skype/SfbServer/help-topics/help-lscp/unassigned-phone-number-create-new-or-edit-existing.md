---
title: 未分配的电话号码 创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: 未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。
ms.openlocfilehash: c757be0b49638c39a9f20f83baf680508a907b20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116180"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="c959e-104">未分配电话号码：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="c959e-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="c959e-p102">未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。</span><span class="sxs-lookup"><span data-stu-id="c959e-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c959e-p103">在创建完新的未分配号码范围或编辑完现有未分配号码范围后，单击“确定”可返回到列出所有号码范围的“未分配号码”页。在单击“未分配号码”页上的“全部提交”后，您在“新建未分配号码范围”页或“编辑未分配号码范围”页上所做的更改才会被提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="c959e-p103">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges. The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c959e-109">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="c959e-109">UI Reference</span></span>

<span data-ttu-id="c959e-110">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="c959e-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c959e-111">**名称** 键入标识未分配号码范围的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="c959e-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="c959e-112">保存区域后，此名称将无法更改。</span><span class="sxs-lookup"><span data-stu-id="c959e-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="c959e-113">**号码范围** 第一个字段中，键入未分配号码范围的开始号码。</span><span class="sxs-lookup"><span data-stu-id="c959e-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="c959e-114">第二个字段中，键入范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="c959e-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="c959e-115">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="c959e-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="c959e-116">如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。</span><span class="sxs-lookup"><span data-stu-id="c959e-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="c959e-117">该数字必须与正则表达式匹配 `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` 。</span><span class="sxs-lookup"><span data-stu-id="c959e-117">The number must match the regular expression `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?`.</span></span> <span data-ttu-id="c959e-118">这意味着该数字可能以字符串 (如果不指定该字符串，它将会自动添加为) 、加号 (+) 以及 1 到 9 之间的数字 `tel:` 。</span><span class="sxs-lookup"><span data-stu-id="c959e-118">This means the number may begin with the string `tel:` (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="c959e-119">电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。</span><span class="sxs-lookup"><span data-stu-id="c959e-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="c959e-120">**通知服务** 选择 **"** 通知"让通知应用程序处理传入呼叫，或 **选择 Exchange UM** 让 Exchange UM 自动助理处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="c959e-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="c959e-121">如果选择“通知”作为“通知服务”：</span><span class="sxs-lookup"><span data-stu-id="c959e-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="c959e-122">**目标服务器的 FQDN** 选择运行通知应用程序的应用程序服务的服务 ID，该服务将处理对此未分配号码范围的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="c959e-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="c959e-123">**公告** 选择要为此未分配号码范围播放的公告。</span><span class="sxs-lookup"><span data-stu-id="c959e-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="c959e-124">如果选择“Exchange UM”作为“通知服务”：</span><span class="sxs-lookup"><span data-stu-id="c959e-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="c959e-125">**自动助理电话号码** 选择 Exchange UM 服务的电话号码自动助理。</span><span class="sxs-lookup"><span data-stu-id="c959e-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="c959e-126">有关通知特性和功能的详细信息，请参阅规划文档中的 Plan [for the Announcement application in Skype for Business 2015。](../../plan-your-deployment/enterprise-voice-solution/announcement.md)</span><span class="sxs-lookup"><span data-stu-id="c959e-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="c959e-127">有关使用未分配号码范围的详细信息，请参阅操作文档中的[Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="c959e-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) in the Operations documentation.</span></span>