---
title: 调用公园新建或编辑现有的
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: 调用公园数字范围定义人检索它们也下班时间之前排队的调用保存的临时数字。
ms.openlocfilehash: 840caf654e1264d7355f117303e8ded9efbca7d3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="3de55-103">呼叫寄存：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="3de55-103">Call Park: Create New or Edit Existing</span></span>
 
<span data-ttu-id="3de55-104">调用公园数字范围定义人检索它们也下班时间之前排队的调用保存的临时数字。</span><span class="sxs-lookup"><span data-stu-id="3de55-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="3de55-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="3de55-105">UI Reference</span></span>

<span data-ttu-id="3de55-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="3de55-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="3de55-107">**名称**键入一个描述性的名称，用于标识的范围。</span><span class="sxs-lookup"><span data-stu-id="3de55-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="3de55-108">保存的范围之后，无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="3de55-108">After you save the number range, this name cannot be changed.</span></span>
    
- <span data-ttu-id="3de55-109">**编号范围**在第一个字段中，键入起始数的范围。</span><span class="sxs-lookup"><span data-stu-id="3de55-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="3de55-110">在第二个字段中，键入结束的范围数。</span><span class="sxs-lookup"><span data-stu-id="3de55-110">In the second field, type the ending number of the number range.</span></span>
    
  - <span data-ttu-id="3de55-111">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="3de55-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
  - <span data-ttu-id="3de55-112">该范围的起始号码值的长度必须与该范围结束号码值的长度相同。</span><span class="sxs-lookup"><span data-stu-id="3de55-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>
    
  - <span data-ttu-id="3de55-p103">号码范围必须是唯一的。该范围不能与其他任何范围重叠。</span><span class="sxs-lookup"><span data-stu-id="3de55-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>
    
  - <span data-ttu-id="3de55-115">如果字符开头的数字范围\*或 #，范围必须是大于 100。</span><span class="sxs-lookup"><span data-stu-id="3de55-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>
    
  - <span data-ttu-id="3de55-116">有效值： 必须匹配的正则表达式字符串 ([\\* | #] ?[1-9]\d{0,7}) |([1-9] \d {0,8})。</span><span class="sxs-lookup"><span data-stu-id="3de55-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="3de55-117">这意味着该值必须是一个任意的字符开头的字符串\*# 或数字 1 到 9 （第一个字符不能为零）。</span><span class="sxs-lookup"><span data-stu-id="3de55-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="3de55-118">如果第一个字符是\*或 #，下面的字符必须是一个数字 1 到 9 （不能为零）。</span><span class="sxs-lookup"><span data-stu-id="3de55-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="3de55-119">后面的字符可以是任意数字 0 到 9，最多七个其他字符 (例如，"#6000"、"\*92000"、"\*95551212"，和"915551212")。</span><span class="sxs-lookup"><span data-stu-id="3de55-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="3de55-120">如果第一个字符不是\*#，第一个字符必须为最多八个字符后, 跟一个数字 1 到 9 （不能为零），或每个数字 0 到 9 (例如： 915551212; 41212; 300)。</span><span class="sxs-lookup"><span data-stu-id="3de55-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>
    
  - <span data-ttu-id="3de55-p105">每个池不应包含 50,000 个以上的号码。每个号码范围包含的号码数通常不超过 100，但是该数目可以更大，只要不超过 10,000。例如，不要将起始号码指定为“7000000”并将结束号码指定为“8000000”，而考虑将起始号码指定为“7000000”并将结束号码指定为“7000100”。</span><span class="sxs-lookup"><span data-stu-id="3de55-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>
    
- <span data-ttu-id="3de55-124">**目标服务器的 FQDN**选择完全合格的域名称 (FQDN) 或服务呼叫公园应用程序宿主的应用程序服务的 ID。</span><span class="sxs-lookup"><span data-stu-id="3de55-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="3de55-125">所有电话都停到指定起始数的范围之内的数字和数字范围内的最终数字将路由到此服务器或池。</span><span class="sxs-lookup"><span data-stu-id="3de55-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>
    
<span data-ttu-id="3de55-126">有关调用公园的特性和功能的详细信息，请参阅[规划中业务 2015年的 Skype 通话公园](../../plan-your-deployment/enterprise-voice-solution/call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="3de55-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="3de55-127">有关使用调用公园数字范围的详细信息，请参阅[配置电话号码停车调用扩展](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3de55-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>
  

