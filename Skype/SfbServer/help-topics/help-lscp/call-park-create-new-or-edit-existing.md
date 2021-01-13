---
title: 呼叫管理新建或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: 呼叫等待号码范围定义临时号码，在有人取回或他们离开之前，将暂住已呼叫。
ms.openlocfilehash: 5ee0891ebaabc97b965aadc5f1ab1c4390669427
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819382"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="08e19-103">呼叫寄存：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="08e19-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="08e19-104">呼叫等待号码范围定义临时号码，在有人取回或他们离开之前，将暂住已呼叫。</span><span class="sxs-lookup"><span data-stu-id="08e19-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="08e19-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="08e19-105">UI Reference</span></span>

<span data-ttu-id="08e19-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="08e19-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="08e19-107">**名称** 键入标识号码范围的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="08e19-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="08e19-108">保存号码范围后，无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="08e19-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="08e19-109">**号码范围** 第一个字段中，键入号码范围的开始编号。</span><span class="sxs-lookup"><span data-stu-id="08e19-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="08e19-110">第二个字段中，键入号码范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="08e19-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="08e19-111">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="08e19-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="08e19-112">该范围的起始号码值的长度必须与该范围结束号码值的长度相同。</span><span class="sxs-lookup"><span data-stu-id="08e19-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="08e19-p103">号码范围必须是唯一的。该范围不能与其他任何范围重叠。</span><span class="sxs-lookup"><span data-stu-id="08e19-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="08e19-115">如果号码范围以字符或 #开头， \* 则范围必须大于 100。</span><span class="sxs-lookup"><span data-stu-id="08e19-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="08e19-116">有效值：必须与正则表达式字符串 ([ \\ \*|#]？[1-9]\d {0,7}) | ([1-9]\d {0,8}) 。</span><span class="sxs-lookup"><span data-stu-id="08e19-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="08e19-117">这意味着该值必须是以字符或 # 开头的字符串，或者是 1 到 9 的字符串 (第一个字符不能为 \* 零) 。</span><span class="sxs-lookup"><span data-stu-id="08e19-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="08e19-118">如果第一个字符是或 #，则下一个字符必须是 \* 1 到 9 (不能为零) 。</span><span class="sxs-lookup"><span data-stu-id="08e19-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="08e19-119">后续字符可以是 0 到 9 之间的任意数字，最多七个附加字符 (例如 \* ，"#6000"、"92000"、"95551212"和 \* "915551212") 。</span><span class="sxs-lookup"><span data-stu-id="08e19-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="08e19-120">如果第一个字符不是或 #，则第一个字符必须是 1 到 9 个数字 (不能为零) ，后跟最多八个字符，每个字符的编号从 0 到 \* 9 (例如：915551212;41212;300) 。</span><span class="sxs-lookup"><span data-stu-id="08e19-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="08e19-p105">每个池不应包含 50,000 个以上的号码。每个号码范围包含的号码数通常不超过 100，但是该数目可以更大，只要不超过 10,000。例如，不要将起始号码指定为“7000000”并将结束号码指定为“8000000”，而考虑将起始号码指定为“7000000”并将结束号码指定为“7000100”。</span><span class="sxs-lookup"><span data-stu-id="08e19-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="08e19-124">**目标服务器的 FQDN** 选择托管呼叫 (的应用程序) FQDN 或服务 ID 的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="08e19-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="08e19-125">所有位于号码范围的起始号码和结束号码所指定的范围内的号码的呼叫都将路由到此服务器或池。</span><span class="sxs-lookup"><span data-stu-id="08e19-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="08e19-126">有关呼叫等待特性和功能的详细信息，请参阅 Plan [for Call Park in Skype for Business 2015。](../../plan-your-deployment/enterprise-voice-solution/call-park.md)</span><span class="sxs-lookup"><span data-stu-id="08e19-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="08e19-127">有关使用呼叫等待号码范围的详细信息，请参阅配置用于"呼叫等待" [的电话号码分机号](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="08e19-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


