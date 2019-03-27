---
title: 创建或修改规范化规则中的业务的 Skype
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 摘要： 了解如何定义、 创建和修改企业服务器中 Skype 的规范化规则。
ms.openlocfilehash: 52f56280c747db702935405ea4c60383c58a6d78
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874596"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="4f7c1-103">创建或修改规范化规则中的业务的 Skype</span><span class="sxs-lookup"><span data-stu-id="4f7c1-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="4f7c1-104">**摘要：** 了解如何定义、 创建和修改企业服务器中 Skype 的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="4f7c1-105">定义、 创建和修改企业服务器中 Skype 的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="4f7c1-106">使用“建立规范化规则”定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="4f7c1-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="4f7c1-107">打开 Skype 业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="4f7c1-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="4f7c1-108">（可选）请按照本文[创建或修改拨号计划中 Skype Business Server](dial-plans.md)通过步骤 11 或[修改拨号计划](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx)前 10 个步骤。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="4f7c1-109">在**新的规范化规则**或**编辑规范化规则**中，键入描述要进行规范化**名称**(例如，5DigitExtension) 中的号码模式的名称。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="4f7c1-110">（可选）在“描述”\*\*\*\* 中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="4f7c1-111">在“建立规范化规则”\*\*\*\* 的以下字段中输入值：</span><span class="sxs-lookup"><span data-stu-id="4f7c1-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="4f7c1-112">**起始数字**（可选）指定您希望模式与之匹配已拨号码的前导位数字。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="4f7c1-113">例如，type425 如果您想要匹配的模式拨打号码 425 开头的字符串。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="4f7c1-114">**长度**匹配模式中指定的位数，选择您想要完全匹配此长度的模式、 匹配的拨打号码的至少此长度，或匹配的拨打号码的任何长度。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="4f7c1-115">**要删除的数字**（可选）指定数量的起始数字要从已拨号码中删除您想要匹配的模式。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="4f7c1-116">**要添加的数字**（可选）指定要添加到已拨号码您想要匹配的模式的数字。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="4f7c1-117">这些字段中输入的值将反映在“要匹配的模式”\*\*\*\* 和“转换规则”\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="4f7c1-118">例如，如果**长度**字段保留为空，type7**起始数字**和选择**完全**，并指定**要删除的数字**0，在**要匹配模式**中生成的正则表达式是：</span><span class="sxs-lookup"><span data-stu-id="4f7c1-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="4f7c1-119">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="4f7c1-119">^(\d{7})$</span></span>

6. <span data-ttu-id="4f7c1-120">在“转换规则”\*\*\*\* 中，指定转换后的 E.164 电话号码格式的模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4f7c1-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="4f7c1-121">代表匹配模式中指定的号码位数的值。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="4f7c1-122">例如，如果匹配模式 ^(\d{7})$ 然后 $1 转换规则代表 7 位数字表示已拨的号码。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="4f7c1-123">（可选）键入**要添加的数字**字段来指定要附加到转换后的号码 （例如 + 1425年） 前面的数字值。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="4f7c1-124">例如，如果**模式与之匹配**包含 ^(\d{7}) 拨打号码中为的模式 $ 和**转换规则**包含 + 1425年$ 1 为模式的 E.164 电话号码，该规则会规范化为 + 14255550100 将 5550100。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="4f7c1-125">（可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="4f7c1-p104">（可选）输入一个号码以测试规范化规则，然后单击“执行”\*\*\*\*。测试结果会显示在“输入要测试的号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4f7c1-p105">您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。有关详细信息，请参阅 [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-p105">You can save a normalization rule that does not yet pass the test and then reconfigure it later. For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="4f7c1-130">单击“确定”\*\*\*\* 保存规范化规则。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="4f7c1-131">单击“确定”\*\*\*\* 保存拨号计划。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="4f7c1-132">在“拨号计划”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4f7c1-133">无论何时创建或更改规范化规则，都必须运行“全部提交”\*\*\*\* 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="4f7c1-134">有关详细信息，请参阅操作文档中的[Publish 挂起的 Skype for Business 中的语音路由配置更改](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="4f7c1-135">手动定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="4f7c1-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="4f7c1-136">打开 Skype 业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="4f7c1-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="4f7c1-137">（可选）请按照本文[创建或修改拨号计划中 Skype Business Server](dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="4f7c1-138">在**新的规范化规则**或**编辑规范化规则**中，键入描述要进行规范化在**名称**（例如，名称规范化 rule5DigitExtension） 的号码模式的名称。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="4f7c1-139">（可选）在“说明”\*\*\*\* 字段中，键入规范化规则的说明（例如，“Translates 5-digit extensions”）。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="4f7c1-140">在“建立规范化规则”\*\*\*\* 中，单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="4f7c1-141">在“键入正则表达式”\*\*\*\* 中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="4f7c1-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="4f7c1-142">在“匹配此模式”\*\*\*\* 中，指定要用于匹配拨打的电话号码的模式。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="4f7c1-143">在“转换规则”\*\*\*\* 中，指定转换后的 E.164 电话号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="4f7c1-144">例如，如果输入 ^(\d{7})$，在**匹配此模式**和 + 1425年$ 1，在**转换规则**，该规则会为 + 14255550100 将 5550100 规范化。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="4f7c1-145">（可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="4f7c1-p107">（可选）输入一个号码以测试规范化规则，然后单击“执行”\*\*\*\*。测试结果会显示在“输入要测试的号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="4f7c1-148">单击“确定”\*\*\*\* 保存规范化规则。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="4f7c1-149">单击“确定”\*\*\*\* 保存拨号计划。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="4f7c1-150">在“拨号计划”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4f7c1-151">无论何时创建或更改规范化规则，都必须运行“全部提交”\*\*\*\* 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="4f7c1-152">有关详细信息，请参阅操作文档中的[Publish 挂起的 Skype for Business 中的语音路由配置更改](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="4f7c1-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


