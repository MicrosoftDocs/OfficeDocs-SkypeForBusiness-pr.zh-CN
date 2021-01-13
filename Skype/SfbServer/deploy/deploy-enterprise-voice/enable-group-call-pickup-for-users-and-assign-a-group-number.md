---
title: 为用户启用组内呼叫接听，在 Skype for Business 中分配组号码
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
description: 在 Skype for Business Server 企业语音为用户启用组内呼叫企业语音分配组号码。
ms.openlocfilehash: 3467aea1b9671a93cca2f66a2ac73c39f15dc26e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830962"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="c2473-103">为用户启用组内呼叫接听，在 Skype for Business 中分配组号码</span><span class="sxs-lookup"><span data-stu-id="c2473-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="c2473-104">在 Skype for Business Server 企业语音为用户启用组内呼叫企业语音分配组号码。</span><span class="sxs-lookup"><span data-stu-id="c2473-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="c2473-105">将呼叫接听组号码添加到呼叫等待通道表后，使用 SEFAUtil 工具将组号码分配给用户，并为其启用组内呼叫分拣。</span><span class="sxs-lookup"><span data-stu-id="c2473-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="c2473-106">在混合部署中，不要将组内呼叫接听组分配给在线用户。</span><span class="sxs-lookup"><span data-stu-id="c2473-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="c2473-107">联机用户不能参与组内呼叫接听。</span><span class="sxs-lookup"><span data-stu-id="c2473-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="c2473-108">也就是说，其他用户无法应答其呼叫，并且无法应答其他用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c2473-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="c2473-109">为用户分配组号码并启用组内呼叫接听</span><span class="sxs-lookup"><span data-stu-id="c2473-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="c2473-110">使用管理员权限登录到安装 SEFAUtil 工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="c2473-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="c2473-111">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="c2473-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="c2473-112">例如，若要将组号 199 分配给用户：</span><span class="sxs-lookup"><span data-stu-id="c2473-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="c2473-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2473-113">See also</span></span>

[<span data-ttu-id="c2473-114">禁用用户的组分拣</span><span class="sxs-lookup"><span data-stu-id="c2473-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

