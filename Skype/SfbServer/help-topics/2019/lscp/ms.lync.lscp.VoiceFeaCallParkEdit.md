---
title: 呼叫寄存 "新建" 或 "编辑现有"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: 呼叫寄存号码范围定义了停用通话的临时号码, 直到有人检索它们或超时。
ms.openlocfilehash: 7257327081be46f343ef8aeb6076ad9a788f46bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290168"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="52589-103">呼叫寄存：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="52589-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="52589-104">呼叫寄存号码范围定义了停用通话的临时号码, 直到有人检索它们或超时。</span><span class="sxs-lookup"><span data-stu-id="52589-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="52589-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="52589-105">UI Reference</span></span>

<span data-ttu-id="52589-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="52589-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="52589-107">**名称**键入标识数字范围的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="52589-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="52589-108">保存号码范围后, 此名称不能更改。</span><span class="sxs-lookup"><span data-stu-id="52589-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="52589-109">**数字范围**在第一个字段中, 键入数字范围的起始编号。</span><span class="sxs-lookup"><span data-stu-id="52589-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="52589-110">在第二个字段中, 键入数字范围的结束编号。</span><span class="sxs-lookup"><span data-stu-id="52589-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="52589-111">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="52589-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="52589-112">该范围的起始号码值的长度必须与该范围结束号码值的长度相同。</span><span class="sxs-lookup"><span data-stu-id="52589-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="52589-p103">号码范围必须是唯一的。该范围不能与其他任何范围重叠。</span><span class="sxs-lookup"><span data-stu-id="52589-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="52589-115">如果数字范围以字符\*或 # 开头, 则范围必须大于100。</span><span class="sxs-lookup"><span data-stu-id="52589-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="52589-116">有效值: 必须匹配正则表达式字符串 ([\\* | #] ? [1-9] \d{0,7}) |([1-9] \d{0,8})。</span><span class="sxs-lookup"><span data-stu-id="52589-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="52589-117">这意味着该值必须是以字符\*或 # 或数字1到9开头的字符串 (第一个字符不能为零)。</span><span class="sxs-lookup"><span data-stu-id="52589-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="52589-118">如果第一个字符是\*或 #, 则以下字符必须是1到9的数字 (不能为零)。</span><span class="sxs-lookup"><span data-stu-id="52589-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="52589-119">后续字符可以是0到9的任何数字, 最多可有7个附加字符 (例如, "\*#6000"、"\*92000"、"95551212" 和 "915551212")。</span><span class="sxs-lookup"><span data-stu-id="52589-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="52589-120">如果第一个字符不\*是或 #, 则第一个字符必须是数字1到 9 (不能为零), 后跟八个字符 (数字0到 9) (例如: 915551212; 41212; 300)。</span><span class="sxs-lookup"><span data-stu-id="52589-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="52589-p105">每个池不应包含 50,000 个以上的号码。每个号码范围包含的号码数通常不超过 100，但是该数目可以更大，只要不超过 10,000。例如，不要将起始号码指定为“7000000”并将结束号码指定为“8000000”，而考虑将起始号码指定为“7000000”并将结束号码指定为“7000100”。</span><span class="sxs-lookup"><span data-stu-id="52589-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="52589-124">**目标服务器的 FQDN**选择托管呼叫寄存应用程序的应用程序服务的完全限定的域名 (FQDN) 或服务 ID。</span><span class="sxs-lookup"><span data-stu-id="52589-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="52589-125">所有拨出的范围内的号码都将路由到此服务器或池, 并且数字范围内由起始号码和结束号码指定的范围内的电话。</span><span class="sxs-lookup"><span data-stu-id="52589-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="52589-126">有关呼叫寄存功能和功能的详细信息, 请参阅[在 Skype For business 中计划通话寄存](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="52589-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="52589-127">有关使用呼叫寄存号码范围的详细信息, 请参阅[配置停车通话的电话号码扩展](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="52589-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


