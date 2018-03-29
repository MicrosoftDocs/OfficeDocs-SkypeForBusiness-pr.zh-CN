---
title: 在 Skype for Business 2015 中创建或修改规范化规则
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 摘要： 了解如何定义、 创建和修改业务服务器 2015年在 Skype 的规范化规则。
ms.openlocfilehash: 5b55e5e930680d3c51908b77d44a80e2e74ef89c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business-2015"></a><span data-ttu-id="db2ab-103">在 Skype for Business 2015 中创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="db2ab-103">Create or modify a normalization rule in Skype for Business 2015</span></span>
 
<span data-ttu-id="db2ab-104">**摘要：**了解如何定义、 创建和修改业务服务器 2015年在 Skype 的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="db2ab-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="db2ab-105">定义、 创建和修改业务服务器在 Skype 的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="db2ab-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>
  
### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="db2ab-106">使用“建立规范化规则”定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="db2ab-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="db2ab-107">打开 Skype 业务服务器的控制面板</span><span class="sxs-lookup"><span data-stu-id="db2ab-107">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="db2ab-108">（可选）按照中的步骤[创建或修改的业务服务器 2015年的 Skype 的拨号计划](dial-plans.md)通过第 11 步或[修改拨号计划](http://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx)到第 10 步。</span><span class="sxs-lookup"><span data-stu-id="db2ab-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md) through step 11 or [Modify a Dial Plan](http://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>
    
3. <span data-ttu-id="db2ab-109">在**新的规范化规则**或**编辑规范化规则**中，键入描述正在规范化**名称**(例如，5DigitExtension) 中的数字模式的名称。</span><span class="sxs-lookup"><span data-stu-id="db2ab-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>
    
4. <span data-ttu-id="db2ab-110">（可选）在“描述”****中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。</span><span class="sxs-lookup"><span data-stu-id="db2ab-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>
    
5. <span data-ttu-id="db2ab-111">在“建立规范化规则”****的以下字段中输入值：</span><span class="sxs-lookup"><span data-stu-id="db2ab-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
   - <span data-ttu-id="db2ab-112">**起始位**（可选）指定拨叫的号码，您想要匹配的模式的前导位数字。</span><span class="sxs-lookup"><span data-stu-id="db2ab-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="db2ab-113">例如，type425 要匹配的模式是否拨打 425 以数字开头。</span><span class="sxs-lookup"><span data-stu-id="db2ab-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
   - <span data-ttu-id="db2ab-114">**长度**匹配模式中指定的位数并选择所需的模式完全匹配该长度、 至少是这个长度，匹配号码或匹配的任意长度的号码。</span><span class="sxs-lookup"><span data-stu-id="db2ab-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
   - <span data-ttu-id="db2ab-115">**若要删除的数字**（可选）指定希望启动数字要拨叫的号码从中删除要匹配的模式。</span><span class="sxs-lookup"><span data-stu-id="db2ab-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
   - <span data-ttu-id="db2ab-116">**若要添加的数字**（可选）指定要添加到拨叫的号码想要匹配的模式的数字。</span><span class="sxs-lookup"><span data-stu-id="db2ab-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="db2ab-117">这些字段中输入的值将反映在“要匹配的模式”****和“转换规则”****中。</span><span class="sxs-lookup"><span data-stu-id="db2ab-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="db2ab-118">例如，如果**长度**字段留空，type7 的**起始数字**和**完全**，选择并指定在**要删除的数字**为 0，则是得到的正则表达式**模式匹配**中：</span><span class="sxs-lookup"><span data-stu-id="db2ab-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="db2ab-119">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="db2ab-119">^(\d{7})$</span></span>
    
6. <span data-ttu-id="db2ab-120">在“转换规则”****中，指定转换后的 E.164 电话号码格式的模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="db2ab-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
   - <span data-ttu-id="db2ab-121">代表匹配模式中指定的号码位数的值。</span><span class="sxs-lookup"><span data-stu-id="db2ab-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="db2ab-122">例如，如果匹配的模式是 ^ （\d{7})$ 然后 $1 的转换规则中代表 7 位拨叫的号码。</span><span class="sxs-lookup"><span data-stu-id="db2ab-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>
    
   - <span data-ttu-id="db2ab-123">（可选）在**数字添加**字段以指定数字要预置的翻译数量 （例如，+1425） 中键入一个值。</span><span class="sxs-lookup"><span data-stu-id="db2ab-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>
    
    <span data-ttu-id="db2ab-124">例如，如果包含拨叫的号码和**转换规则**的模式与**模式匹配**contains^(\d{7})$ + 1425 E.164 模式作为 $1 电话号码、 规则标准化为 +14255550100 5550100。</span><span class="sxs-lookup"><span data-stu-id="db2ab-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>
    
7. <span data-ttu-id="db2ab-125">（可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”****。</span><span class="sxs-lookup"><span data-stu-id="db2ab-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>
    
8. <span data-ttu-id="db2ab-p104">（可选）输入一个号码以测试规范化规则，然后单击“执行”****。测试结果会显示在“输入要测试的号码”****下。</span><span class="sxs-lookup"><span data-stu-id="db2ab-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="db2ab-128">您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。</span><span class="sxs-lookup"><span data-stu-id="db2ab-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="db2ab-129">有关详细信息，请参阅[测试语音路由](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="db2ab-129">For details, see [Test Voice Routing](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span> 
  
9. <span data-ttu-id="db2ab-130">单击“确定”****保存规范化规则。</span><span class="sxs-lookup"><span data-stu-id="db2ab-130">Click **OK** to save the normalization rule.</span></span>
    
10. <span data-ttu-id="db2ab-131">单击“确定”****保存拨号计划。</span><span class="sxs-lookup"><span data-stu-id="db2ab-131">Click **OK** to save the dial plan.</span></span>
    
11. <span data-ttu-id="db2ab-132">在“拨号计划”****页上，单击“提交”****，然后单击“全部提交”****。</span><span class="sxs-lookup"><span data-stu-id="db2ab-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="db2ab-133">无论何时创建或更改规范化规则，都必须运行“全部提交”****命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="db2ab-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="db2ab-134">有关详细信息，请参阅[挂起更改的业务 2015年的 Skype 语音路由配置发布](voice-route-config-changes.md)操作文档。</span><span class="sxs-lookup"><span data-stu-id="db2ab-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="db2ab-135">手动定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="db2ab-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="db2ab-136">打开 Skype 业务服务器的控制面板</span><span class="sxs-lookup"><span data-stu-id="db2ab-136">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="db2ab-137">（可选）按照中的步骤[创建或修改的业务服务器 2015年的 Skype 的拨号计划](dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="db2ab-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md).</span></span> 
    
3. <span data-ttu-id="db2ab-138">在**新的规范化规则**或**编辑规范化规则**中，键入描述正在进行正常化在**名称**（例如，名称标准化 rule5DigitExtension） 的数字模式的名称。</span><span class="sxs-lookup"><span data-stu-id="db2ab-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>
    
4. <span data-ttu-id="db2ab-139">（可选）在“说明”****字段中，键入规范化规则的说明（例如，“Translates 5-digit extensions”）。</span><span class="sxs-lookup"><span data-stu-id="db2ab-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>
    
5. <span data-ttu-id="db2ab-140">在“建立规范化规则”****中，单击“编辑”****。</span><span class="sxs-lookup"><span data-stu-id="db2ab-140">In **Build a Normalization Rule**, click **Edit**.</span></span>
    
6. <span data-ttu-id="db2ab-141">在“键入正则表达式”****中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="db2ab-141">Enter the following in **Type a Regular Expression**:</span></span>
    
   - <span data-ttu-id="db2ab-142">在“匹配此模式”****中，指定要用于匹配拨打的电话号码的模式。</span><span class="sxs-lookup"><span data-stu-id="db2ab-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
   - <span data-ttu-id="db2ab-143">在“转换规则”****中，指定转换后的 E.164 电话号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="db2ab-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="db2ab-144">例如，如果您输入 ^ (\d{7})$ 中**与此模式匹配**和 + 1425年**翻译规则**，该规则中的 $1 将标准化为 +14255550100 5550100。</span><span class="sxs-lookup"><span data-stu-id="db2ab-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>
    
7. <span data-ttu-id="db2ab-145">（可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”****。</span><span class="sxs-lookup"><span data-stu-id="db2ab-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>
    
8. <span data-ttu-id="db2ab-p107">（可选）输入一个号码以测试规范化规则，然后单击“执行”****。测试结果会显示在“输入要测试的号码”****下。</span><span class="sxs-lookup"><span data-stu-id="db2ab-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
9. <span data-ttu-id="db2ab-148">单击“确定”****保存规范化规则。</span><span class="sxs-lookup"><span data-stu-id="db2ab-148">Click **OK** to save the normalization rule.</span></span>
    
10. <span data-ttu-id="db2ab-149">单击“确定”****保存拨号计划。</span><span class="sxs-lookup"><span data-stu-id="db2ab-149">Click **OK** to save the dial plan.</span></span>
    
11. <span data-ttu-id="db2ab-150">在“拨号计划”****页上，单击“提交”****，然后单击“全部提交”****。</span><span class="sxs-lookup"><span data-stu-id="db2ab-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="db2ab-151">无论何时创建或更改规范化规则，都必须运行“全部提交”****命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="db2ab-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="db2ab-152">有关详细信息，请参阅[挂起更改的业务 2015年的 Skype 语音路由配置发布](voice-route-config-changes.md)操作文档。</span><span class="sxs-lookup"><span data-stu-id="db2ab-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

