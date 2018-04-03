---
title: 应输入电话号码的方式
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: '了解如何设置电话号码，当您将它们到 Skype 的业务。 '
ms.openlocfilehash: 68fe698612c095e657dab56723df7de6eb13b858
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="5b8dd-103">应输入电话号码的方式</span><span class="sxs-lookup"><span data-stu-id="5b8dd-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="5b8dd-104">当移植电话号码时，您必须以正确的格式输入它们。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5b8dd-105">每个电话号码或电话号码的范围必须分别输入每个行上。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="5b8dd-106">当您正在输入一个电话号码：</span><span class="sxs-lookup"><span data-stu-id="5b8dd-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="5b8dd-107">将忽略所有特殊字符 (包括破折号"-")。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="5b8dd-108">例如：</span><span class="sxs-lookup"><span data-stu-id="5b8dd-108">For example:</span></span>
    
  - <span data-ttu-id="5b8dd-109">10 位号码： \*\* &amp; \*(425\*（) (\*&amp;4&amp;\*（)） (\*250649**将修正为**+14255550649\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="5b8dd-110">11 位号码： **1\*（) (\*&amp;42&amp;\*（) (\*&amp;55550649**将修正为**+14255550649**。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="5b8dd-111">如果有 10 或 11 位，所有的标记将被忽略。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="5b8dd-112">例如， ** \<div > 4255551234\</div >**将是**+14255551234**。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="5b8dd-113">"-"，空间和括号将被忽略。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="5b8dd-114">例如：</span><span class="sxs-lookup"><span data-stu-id="5b8dd-114">For example:</span></span>
    
  - <span data-ttu-id="5b8dd-115">为一个 10 位数字： **(425) 555-6776**将修正为**+14255556776**。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="5b8dd-116">11 位号码： **1(425) 555 6776**将修正为**+14255556776**。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="5b8dd-117">将视为特殊字符，如果 10 位或 11 位数字的电话号码，则忽略所有字母。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="5b8dd-118">例如：</span><span class="sxs-lookup"><span data-stu-id="5b8dd-118">For example:</span></span>
    
  - <span data-ttu-id="5b8dd-119">为一个 10 位数字： **14jaosia2reoij05jof55506ajfoj49isdjf**将修正为**+14255550649**。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="5b8dd-120">11 位号码： **1ade4jaoda2rfoij05ojof55506dsfoj49if**将修正为**+14255550649**。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="5b8dd-121">即使在其他语言中的特殊字符的任意组合将得到纠正。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="5b8dd-122">例如：</span><span class="sxs-lookup"><span data-stu-id="5b8dd-122">For example:</span></span> 
    
  - <span data-ttu-id="5b8dd-123">10 位号码：**中文4中文2ajj5\*（) (\*(5()...551345**将修正为**+14555551345**。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="5b8dd-124">11 位号码：**中文4中文2 美元 a5\*（) (\*(5()...55 (.1345**将修正为**+14555551345**。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="5b8dd-125">如果任何数字包含少于 10 位或多于 11 位，他们将会突出显示为用户纠正：</span><span class="sxs-lookup"><span data-stu-id="5b8dd-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="5b8dd-126">\*\*5551245\* \*将突出显示，需要进行更正。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="5b8dd-127">**1234567891011**将突出显示，需要进行更正。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="5b8dd-128">将突出显示任何数字的位数少于 10 个或多于 11 位，与任何特殊的字符，而不被自动更正。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="5b8dd-129">不含特殊字符输入的 7 位数编号为： **123456abcdefg7**将突出显示，需要进行更正，但不会忽略字母。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="5b8dd-130">特殊字符与输入的 7 位数编号为： **12345!@#$%^&amp;\*（)-@# $%^&amp;\*（7)**将突出以修正。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="5b8dd-131">特殊字符不会被忽略。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="5b8dd-132">当您输入电话号码的范围。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="5b8dd-133">允许仅有两个电话号码。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="5b8dd-134">较小的数字必须是该区域的第一个数字。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="5b8dd-135">所有特殊字符 (除连字符"-") 是一个数字被同等对待。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="5b8dd-136">例如， **(425) 555 0&amp;\*(123-（1425年) 5557899nm**将修正为**+14255550123-+13202040659**。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="5b8dd-137">"-"用于只分隔两个数字。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="5b8dd-138">它不支持包含多个"-"号范围内。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="5b8dd-139">例如，应作为输入**(425) 555-0649-(425) 555-1115** **(425) 5550649-（425) 5551115**。</span><span class="sxs-lookup"><span data-stu-id="5b8dd-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="5b8dd-140">**完整的逐步说明，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。**</span><span class="sxs-lookup"><span data-stu-id="5b8dd-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).**</span></span>

 > [!NOTE]
> <span data-ttu-id="5b8dd-141">如果需要获取更多电话号码，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="5b8dd-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="5b8dd-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="5b8dd-142">Related topics</span></span>
[<span data-ttu-id="5b8dd-143">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="5b8dd-143">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="5b8dd-144">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="5b8dd-144">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="5b8dd-145">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="5b8dd-145">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="5b8dd-146">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="5b8dd-146">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="5b8dd-147">Skype for Business Online：紧急呼叫免责声明标签</span><span class="sxs-lookup"><span data-stu-id="5b8dd-147">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 