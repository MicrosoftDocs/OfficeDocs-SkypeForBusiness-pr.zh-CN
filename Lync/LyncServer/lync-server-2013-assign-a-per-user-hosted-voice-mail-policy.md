---
title: Lync Server 2013：分配每用户托管的语音邮件策略
description: Lync Server 2013：分配每用户托管的语音邮件策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559888"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="33652-103">在 Lync Server 2013 中分配每用户托管的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="33652-103">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="33652-p101">部署一个或多个每用户托管语音邮件策略是可选的。如果要部署每用户策略，则必须将其显式分配给用户、组或联系人对象。</span><span class="sxs-lookup"><span data-stu-id="33652-p101">Deploying one or more per-user hosted voice mail policies is optional. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="33652-106">有关分配或删除每用户托管语音邮件策略分配的详细信息，请参阅以下 cmdlet 的 Lync Server 命令行管理程序文档：</span><span class="sxs-lookup"><span data-stu-id="33652-106">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="33652-107">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="33652-107">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="33652-108">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="33652-108">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="33652-109">分配每用户托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="33652-109">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="33652-110">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="33652-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="33652-p102">运行 Grant-CsHostedVoicemailPolicy cmdlet 将每用户托管语音邮件策略分配给各个用户、组和联系人对象。例如，运行：</span><span class="sxs-lookup"><span data-stu-id="33652-p102">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects. For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="33652-113">此示例将 ExRedmond 托管语音邮件策略分配给用户 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="33652-113">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="33652-p103">**Identity** 指定要修改的用户帐户。可以使用以下任意格式指定 Identity 值：</span><span class="sxs-lookup"><span data-stu-id="33652-p103">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="33652-116">用户的 SIP 地址</span><span class="sxs-lookup"><span data-stu-id="33652-116">The user's SIP address</span></span>
    
      - <span data-ttu-id="33652-117">用户的 Active Directory 用户主体名称</span><span class="sxs-lookup"><span data-stu-id="33652-117">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="33652-118">用户的域 \\ 登录名 (例如，contoso \\ kenmyer) </span><span class="sxs-lookup"><span data-stu-id="33652-118">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="33652-119">用户的 Active Directory 域服务显示名称（例如，Ken Myer）。</span><span class="sxs-lookup"><span data-stu-id="33652-119">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="33652-120">如果使用 Display-Name 作为 Identity 值，则可以使用星号 (\*) 通配符。</span><span class="sxs-lookup"><span data-stu-id="33652-120">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="33652-121">例如，标识 " \* smith" 将返回其 Display-Name 以字符串值 "smith" 结尾的所有用户。</span><span class="sxs-lookup"><span data-stu-id="33652-121">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="33652-122">用户的 Active Directory SAM 帐户名不能用作 Identity 值，因为 SAM 帐户名在林中不一定是唯一的。</span><span class="sxs-lookup"><span data-stu-id="33652-122">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


