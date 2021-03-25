---
title: 为用户启用组内呼叫接听，并分配 Skype for Business 中的组号码
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 在 Skype for Business Server 中为用户启用企业语音，并分配组号码。
ms.openlocfilehash: 5469e9634e16b855993518092114184a2dca7359
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111828"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="bc763-103">为用户启用组内呼叫接听，并分配 Skype for Business 中的组号码</span><span class="sxs-lookup"><span data-stu-id="bc763-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="bc763-104">在 Skype for Business Server 中为用户启用企业语音，并分配组号码。</span><span class="sxs-lookup"><span data-stu-id="bc763-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="bc763-105">将呼叫接听组号码添加到呼叫等待通道表后，使用 SEFAUtil 工具将组号码分配给用户，并为其启用组内呼叫接听。</span><span class="sxs-lookup"><span data-stu-id="bc763-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="bc763-106">在混合部署中，不要将组内呼叫接听组分配给在线用户。</span><span class="sxs-lookup"><span data-stu-id="bc763-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="bc763-107">联机用户不能参与组内呼叫接听。</span><span class="sxs-lookup"><span data-stu-id="bc763-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="bc763-108">也就是说，其他用户无法应答呼叫，也无法应答其他用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="bc763-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="bc763-109">为用户分配组号码并启用组内呼叫接听</span><span class="sxs-lookup"><span data-stu-id="bc763-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="bc763-110">使用管理员权限登录到安装了 SEFAUtil 工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="bc763-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="bc763-111">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="bc763-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="bc763-112">例如，若要将组号 199 分配给用户：</span><span class="sxs-lookup"><span data-stu-id="bc763-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="bc763-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc763-113">See also</span></span>

[<span data-ttu-id="bc763-114">禁用用户的组分拣</span><span class="sxs-lookup"><span data-stu-id="bc763-114">Disable Group Pickup for Users</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)