---
title: 在 Skype for Business 中创建或修改规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: '摘要: 了解如何在 Skype for Business 服务器中定义、创建和修改规范化规则。'
ms.openlocfilehash: af0f09710d427dc97a919468b5decfa9ef3d93fa
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240258"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="a09b8-103">在 Skype for Business 中创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="a09b8-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="a09b8-104">**摘要:** 了解如何在 Skype for Business 服务器中定义、创建和修改规范化规则。</span><span class="sxs-lookup"><span data-stu-id="a09b8-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="a09b8-105">在 Skype for Business 服务器中定义、创建和修改规范化规则。</span><span class="sxs-lookup"><span data-stu-id="a09b8-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="a09b8-106">使用“建立规范化规则”定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="a09b8-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="a09b8-107">打开 "Skype for Business 服务器" 控制面板</span><span class="sxs-lookup"><span data-stu-id="a09b8-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="a09b8-108">可选按照在 " [Skype For Business 服务器" 中的步骤11创建或修改拨号计划](dial-plans.md)中的步骤操作, 或通过步骤 10[修改拨号计划](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a09b8-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="a09b8-109">在**新的规范化规则**或**编辑规范化规则**中, 键入用于描述在**名称**中正常化的数字模式的名称 (例如, 5DigitExtension)。</span><span class="sxs-lookup"><span data-stu-id="a09b8-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="a09b8-110">（可选）在“描述”\*\*\*\* 中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。</span><span class="sxs-lookup"><span data-stu-id="a09b8-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="a09b8-111">在“建立规范化规则”\*\*\*\* 的以下字段中输入值：</span><span class="sxs-lookup"><span data-stu-id="a09b8-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="a09b8-112">**开始数字**可选指定你希望模式匹配的已拨号码的前导数字。</span><span class="sxs-lookup"><span data-stu-id="a09b8-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="a09b8-113">例如, 如果你希望模式匹配以425开头的拨号码, type425。</span><span class="sxs-lookup"><span data-stu-id="a09b8-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="a09b8-114">**长度**在匹配模式中指定数字的位数, 并选择是希望模式完全匹配此长度、匹配至少具有此长度的电话号码, 还是匹配任何长度的已拨打号码。</span><span class="sxs-lookup"><span data-stu-id="a09b8-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="a09b8-115">**要删除的数字**可选指定要从所需模式匹配的已拨号码的起始位数。</span><span class="sxs-lookup"><span data-stu-id="a09b8-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="a09b8-116">**要添加的数字**可选指定要添加到要与模式匹配的已拨号码的数字。</span><span class="sxs-lookup"><span data-stu-id="a09b8-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="a09b8-117">这些字段中输入的值将反映在“要匹配的模式”\*\*\*\* 和“转换规则”\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="a09b8-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="a09b8-118">例如, 如果将开始的**数字**保留为空, type7 到 "**长度**" 字段中并选择 "**完全**", 并指定**要删除的数字**0, 则**要匹配的模式**中的结果正则表达式如下所示:</span><span class="sxs-lookup"><span data-stu-id="a09b8-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="a09b8-119">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="a09b8-119">^(\d{7})$</span></span>

6. <span data-ttu-id="a09b8-120">在“转换规则”\*\*\*\* 中，指定转换后的 E.164 电话号码格式的模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a09b8-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="a09b8-121">代表匹配模式中指定的号码位数的值。</span><span class="sxs-lookup"><span data-stu-id="a09b8-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="a09b8-122">例如, 如果匹配模式为 ^ (\d{7}) $, 则转换规则中的 $ 1 表示7位拨号码。</span><span class="sxs-lookup"><span data-stu-id="a09b8-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="a09b8-123">可选在 "**要添加的数字**" 中键入值以指定要在已翻译数字前预置的数字 (例如 + 1425)。</span><span class="sxs-lookup"><span data-stu-id="a09b8-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="a09b8-124">例如, 如果**要匹配的模式**包含 ^ (\d{7}) $ 作为拨号号码和**翻译规则**的模式, 则将 + 1425 $ 1 用作 E. 164 电话号码的模式, 规则将5550100标准化到 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="a09b8-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="a09b8-125">（可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a09b8-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="a09b8-p104">（可选）输入一个号码以测试规范化规则，然后单击“执行”\*\*\*\*。测试结果会显示在“输入要测试的号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="a09b8-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a09b8-p105">您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。有关详细信息，请参阅 [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a09b8-p105">You can save a normalization rule that does not yet pass the test and then reconfigure it later. For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="a09b8-130">单击“确定”\*\*\*\* 保存规范化规则。</span><span class="sxs-lookup"><span data-stu-id="a09b8-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="a09b8-131">单击“确定”\*\*\*\* 保存拨号计划。</span><span class="sxs-lookup"><span data-stu-id="a09b8-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="a09b8-132">在“拨号计划”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a09b8-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a09b8-133">无论何时创建或更改规范化规则，都必须运行“全部提交”\*\*\*\* 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="a09b8-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="a09b8-134">有关详细信息, 请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。</span><span class="sxs-lookup"><span data-stu-id="a09b8-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="a09b8-135">手动定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="a09b8-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="a09b8-136">打开 "Skype for Business 服务器" 控制面板</span><span class="sxs-lookup"><span data-stu-id="a09b8-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="a09b8-137">可选按照在[Skype For Business 服务器中创建或修改拨号计划](dial-plans.md)中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="a09b8-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="a09b8-138">在 "**新建规范化规则**" 或 "**编辑规范化规则**" 中, 键入描述要在**名称**中规范化的数字模式的名称 (例如, 将规范化 rule5DigitExtension 命名为 "名称")。</span><span class="sxs-lookup"><span data-stu-id="a09b8-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="a09b8-139">（可选）在“说明”\*\*\*\* 字段中，键入规范化规则的说明（例如，“Translates 5-digit extensions”）。</span><span class="sxs-lookup"><span data-stu-id="a09b8-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="a09b8-140">在“建立规范化规则”\*\*\*\* 中，单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a09b8-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="a09b8-141">在“键入正则表达式”\*\*\*\* 中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="a09b8-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="a09b8-142">在“匹配此模式”\*\*\*\* 中，指定要用于匹配拨打的电话号码的模式。</span><span class="sxs-lookup"><span data-stu-id="a09b8-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="a09b8-143">在“转换规则”\*\*\*\* 中，指定转换后的 E.164 电话号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="a09b8-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="a09b8-144">例如, 如果你在**翻译规则**中输入{7}"^ (\d) $" 与**此模式**+ 1425 $ 1, 则规则会将5550100规范化到 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="a09b8-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="a09b8-145">（可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a09b8-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="a09b8-p107">（可选）输入一个号码以测试规范化规则，然后单击“执行”\*\*\*\*。测试结果会显示在“输入要测试的号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="a09b8-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="a09b8-148">单击“确定”\*\*\*\* 保存规范化规则。</span><span class="sxs-lookup"><span data-stu-id="a09b8-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="a09b8-149">单击“确定”\*\*\*\* 保存拨号计划。</span><span class="sxs-lookup"><span data-stu-id="a09b8-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="a09b8-150">在“拨号计划”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a09b8-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a09b8-151">无论何时创建或更改规范化规则，都必须运行“全部提交”\*\*\*\* 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="a09b8-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="a09b8-152">有关详细信息, 请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。</span><span class="sxs-lookup"><span data-stu-id="a09b8-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


