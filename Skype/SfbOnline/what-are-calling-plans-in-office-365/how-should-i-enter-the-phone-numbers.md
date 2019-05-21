---
title: 如何输入电话号码？
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: '了解如何在将电话号码移植到 Skype for Business 时设置电话号码。 '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280527"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="bd46c-103">如何输入电话号码？</span><span class="sxs-lookup"><span data-stu-id="bd46c-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="bd46c-104">当您移植电话号码时, 您必须以正确的格式输入它们。</span><span class="sxs-lookup"><span data-stu-id="bd46c-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bd46c-105">每个电话号码或电话号码的范围必须在每一行上单独输入。</span><span class="sxs-lookup"><span data-stu-id="bd46c-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="bd46c-106">输入单个电话号码时:</span><span class="sxs-lookup"><span data-stu-id="bd46c-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="bd46c-107">将忽略所有特殊字符 (包括短划线 "-")。</span><span class="sxs-lookup"><span data-stu-id="bd46c-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="bd46c-108">例如：</span><span class="sxs-lookup"><span data-stu-id="bd46c-108">For example:</span></span>
    
  - <span data-ttu-id="bd46c-109">对于10位号码: \*\* &amp; \*(\*425 (\*&amp;) (&amp;\*4 ()) (\*250649\*\*将更正为 **+ 14255550649**。</span><span class="sxs-lookup"><span data-stu-id="bd46c-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="bd46c-110">对于11位号码: **1\*() (\*&amp;&amp;\*42 () (\*&amp;55550649**将更正为 **+ 14255550649**)。</span><span class="sxs-lookup"><span data-stu-id="bd46c-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="bd46c-111">如果有10个或11个数字, 将忽略所有标记。</span><span class="sxs-lookup"><span data-stu-id="bd46c-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="bd46c-112">例如, \*\* \<div> 4255551234\</div>\*\* 将是 **+ 14255551234**。</span><span class="sxs-lookup"><span data-stu-id="bd46c-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="bd46c-113">将忽略 "-"、空格和括号。</span><span class="sxs-lookup"><span data-stu-id="bd46c-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="bd46c-114">例如：</span><span class="sxs-lookup"><span data-stu-id="bd46c-114">For example:</span></span>
    
  - <span data-ttu-id="bd46c-115">对于10位数字: **(425) 555-6776**将更正为 **+ 14255556776**。</span><span class="sxs-lookup"><span data-stu-id="bd46c-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="bd46c-116">对于11位号码: **1 (425) 555-6776**将更正为 **+ 14255556776**。</span><span class="sxs-lookup"><span data-stu-id="bd46c-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="bd46c-117">如果有10位或11位的电话号码, 则所有字母都将被视为特殊字符且被忽略。</span><span class="sxs-lookup"><span data-stu-id="bd46c-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="bd46c-118">例如：</span><span class="sxs-lookup"><span data-stu-id="bd46c-118">For example:</span></span>
    
  - <span data-ttu-id="bd46c-119">对于10位号码: **14jaosia2reoij05jof55506ajfoj49isdjf**将更正为 **+ 14255550649**。</span><span class="sxs-lookup"><span data-stu-id="bd46c-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="bd46c-120">对于11位号码: **1ade4jaoda2rfoij05ojof55506dsfoj49if**将更正为 **+ 14255550649**。</span><span class="sxs-lookup"><span data-stu-id="bd46c-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="bd46c-121">将更正特殊字符 (甚至其他语言) 的任意组合。</span><span class="sxs-lookup"><span data-stu-id="bd46c-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="bd46c-122">例如：</span><span class="sxs-lookup"><span data-stu-id="bd46c-122">For example:</span></span> 
    
  - <span data-ttu-id="bd46c-123">对于10位号码:**中文4中文2ajj5\*() (\*(5,) .。。551345**将更正为 **+ 14555551345**。</span><span class="sxs-lookup"><span data-stu-id="bd46c-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="bd46c-124">对于一个11位数字:**中文4中文 2\*$ a5 () (\*(5 () .。。55 (. 1345**将更正为 **+ 14555551345**。</span><span class="sxs-lookup"><span data-stu-id="bd46c-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="bd46c-125">如果任何数字中包含的数字少于10个或大于11个数字, 将突出显示这些数字以供用户更正:</span><span class="sxs-lookup"><span data-stu-id="bd46c-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="bd46c-126">\*\*5551245\* \*将突出显示并需要更正。</span><span class="sxs-lookup"><span data-stu-id="bd46c-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="bd46c-127">**1234567891011**将突出显示并需要更正。</span><span class="sxs-lookup"><span data-stu-id="bd46c-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="bd46c-128">任何小于10位或大于11位且包含任何特殊字符的数字都将突出显示, 而不会自动更正。</span><span class="sxs-lookup"><span data-stu-id="bd46c-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="bd46c-129">对于不带输入特殊字符的7位数字: 将突出显示**123456abcdefg7**并需要更正, 但不会忽略字母。</span><span class="sxs-lookup"><span data-stu-id="bd46c-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="bd46c-130">对于输入了特殊字符的7位数字: **&amp;\*12345! @ # $% ^ (), 将突出显示 @ # $%&amp;\*^ () 7** 。</span><span class="sxs-lookup"><span data-stu-id="bd46c-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="bd46c-131">特殊字符不会被忽略。</span><span class="sxs-lookup"><span data-stu-id="bd46c-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="bd46c-132">输入电话号码范围时。</span><span class="sxs-lookup"><span data-stu-id="bd46c-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="bd46c-133">仅允许两个电话号码。</span><span class="sxs-lookup"><span data-stu-id="bd46c-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="bd46c-134">较小的数字必须是区域中的第一个数字。</span><span class="sxs-lookup"><span data-stu-id="bd46c-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="bd46c-135">所有特殊字符 (短划线 "-" 除外) 的处理方式与单个数字相同。</span><span class="sxs-lookup"><span data-stu-id="bd46c-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="bd46c-136">例如, **(425) 555 0&amp;\*(123-(1425) 5557899nm**将更正为 **+ 14255550123-+ 13202040659**。</span><span class="sxs-lookup"><span data-stu-id="bd46c-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="bd46c-137">"-" 用于分隔两个数字。</span><span class="sxs-lookup"><span data-stu-id="bd46c-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="bd46c-138">不支持在数字范围中包含多个 "-"。</span><span class="sxs-lookup"><span data-stu-id="bd46c-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="bd46c-139">例如, **(425) 555-0649-(425) 555-1115**应输入为 **(425) 5550649-(425) 5551115**。</span><span class="sxs-lookup"><span data-stu-id="bd46c-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
  <span data-ttu-id="bd46c-140">**有关完整的分步说明, 请参阅[将电话号码转移到 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365)。**</span><span class="sxs-lookup"><span data-stu-id="bd46c-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

  > [!NOTE]
  > <span data-ttu-id="bd46c-141">如果需要获取更多电话号码，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="bd46c-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="bd46c-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="bd46c-142">Related topics</span></span>
[<span data-ttu-id="bd46c-143">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="bd46c-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="bd46c-144">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="bd46c-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="bd46c-145">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="bd46c-145">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="bd46c-146">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="bd46c-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="bd46c-147">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="bd46c-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 