---
title: 为用户启用组呼叫分拣和分配 Skype for Business 中的一组数
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 为用户启用组中 Skype 调用的分拣业务 Server 企业语音，并分配组数。
ms.openlocfilehash: 94498732ef9bdc66130a6c15cbf342681c48f036
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881845"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="524f0-103">为用户启用组呼叫分拣和分配 Skype for Business 中的一组数</span><span class="sxs-lookup"><span data-stu-id="524f0-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="524f0-104">为用户启用组中 Skype 调用的分拣业务 Server 企业语音，并分配组数。</span><span class="sxs-lookup"><span data-stu-id="524f0-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="524f0-105">将呼叫分拣组号码添加到呼叫寄存通道表后，您使用 SEFAUtil 工具将组号码分配给用户和组呼叫分拣启用。</span><span class="sxs-lookup"><span data-stu-id="524f0-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="524f0-106">在混合部署中，现在将一组呼叫分拣组分配给驻留联机用户。</span><span class="sxs-lookup"><span data-stu-id="524f0-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="524f0-107">联机驻留的用户不能参与组呼叫分拣。</span><span class="sxs-lookup"><span data-stu-id="524f0-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="524f0-108">也就是说，他们的呼叫无法由其他用户应答，他们也无法应答对其他用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="524f0-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="524f0-109">指定一组数并为用户启用组呼叫分拣</span><span class="sxs-lookup"><span data-stu-id="524f0-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="524f0-110">使用管理员权限登录安装了 SEFAUtil 工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="524f0-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="524f0-111">在该命令行处，运行：</span><span class="sxs-lookup"><span data-stu-id="524f0-111">At the command line, run:</span></span>

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="524f0-112">例如，将组号码 199 分配给用户：</span><span class="sxs-lookup"><span data-stu-id="524f0-112">For example, to assign group number 199 to a user:</span></span>

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="524f0-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="524f0-113">See also</span></span>

[<span data-ttu-id="524f0-114">用户的禁用组分拣</span><span class="sxs-lookup"><span data-stu-id="524f0-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

