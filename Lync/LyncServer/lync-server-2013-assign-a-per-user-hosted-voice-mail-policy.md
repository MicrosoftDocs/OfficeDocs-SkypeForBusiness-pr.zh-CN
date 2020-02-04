---
title: Lync Server 2013：分配每用户托管的语音邮件策略
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
ms.openlocfilehash: 95413733a9b23ce1f749ebb16521a3349b00165d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722952"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="80343-102">在 Lync Server 2013 中分配每用户托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="80343-102">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="80343-103">部署一个或多个每用户托管的语音邮件策略是可选的。</span><span class="sxs-lookup"><span data-stu-id="80343-103">Deploying one or more per-user hosted voice mail policies is optional.</span></span> <span data-ttu-id="80343-104">如果你确实要部署每用户策略，则必须将它们显式分配给用户、组或联系人对象。</span><span class="sxs-lookup"><span data-stu-id="80343-104">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="80343-105">有关分配或删除每用户托管语音邮件策略分配的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：</span><span class="sxs-lookup"><span data-stu-id="80343-105">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="80343-106">授权-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="80343-106">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="80343-107">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="80343-107">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="80343-108">分配每用户托管的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="80343-108">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="80343-109">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="80343-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="80343-110">运行 CsHostedVoicemailPolicy cmdlet，将每用户托管语音邮件策略分配给单个用户、组和联系人对象。</span><span class="sxs-lookup"><span data-stu-id="80343-110">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects.</span></span> <span data-ttu-id="80343-111">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="80343-111">For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="80343-112">此示例将 ExRedmond 托管语音邮件策略分配给用户 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="80343-112">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="80343-113">**标识**指定要修改的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="80343-113">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="80343-114">可以使用以下任意格式指定标识值：</span><span class="sxs-lookup"><span data-stu-id="80343-114">The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="80343-115">用户的 SIP 地址</span><span class="sxs-lookup"><span data-stu-id="80343-115">The user's SIP address</span></span>
    
      - <span data-ttu-id="80343-116">用户的 Active Directory 用户主体-名称</span><span class="sxs-lookup"><span data-stu-id="80343-116">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="80343-117">用户的域\\登录名（例如，contoso\\kenmyer）</span><span class="sxs-lookup"><span data-stu-id="80343-117">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="80343-118">用户的 Active Directory 域服务显示名称（如 Ken Myer）。</span><span class="sxs-lookup"><span data-stu-id="80343-118">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="80343-119">如果使用显示名称作为标识值，则可以使用星号（\*）通配符。</span><span class="sxs-lookup"><span data-stu-id="80343-119">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="80343-120">例如，标识 "\* smith" 将返回具有以字符串值 "smith" 结尾的显示名称的所有用户。</span><span class="sxs-lookup"><span data-stu-id="80343-120">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="80343-121">用户的 Active Directory SAM-帐户名称不能用作标识值，因为 SAM 帐户名称不一定在林中唯一。</span><span class="sxs-lookup"><span data-stu-id="80343-121">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


