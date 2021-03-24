---
title: Create or modify a translation rule for called ID presentation in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 摘要：了解如何使用 Skype for Business Server 中的"生成转换规则"工具定义转换规则。
ms.openlocfilehash: 3f4754184e69e7b574709d0272afc9989553cfe5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103638"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="95258-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="95258-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="95258-104">**摘要：** 了解如何使用 Skype for Business Server 中的"生成转换规则"工具定义转换规则。</span><span class="sxs-lookup"><span data-stu-id="95258-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="95258-105">如果要定义转换规则，请按照以下步骤操作：在"生成转换规则"工具中输入一组值，并启用 Skype for Business Server 控制面板来生成相应的匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="95258-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="95258-106">或者，可以手动编写正则表达式来定义匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="95258-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="95258-107">有关详细信息，请参阅[Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually)。</span><span class="sxs-lookup"><span data-stu-id="95258-107">For details, see [Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="95258-108">使用“构建转换规则”工具定义规则</span><span class="sxs-lookup"><span data-stu-id="95258-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="95258-109">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="95258-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="95258-110">要开始定义转换规则，请按照在 Skype [for Business Server](configure-trunk-with-media-bypass.md) 中配置带媒体旁路的中继的步骤执行步骤 10 或按照步骤 9 在 [Skype for Business Server](configure-trunk-without-media-bypass.md) 中配置没有媒体旁路的中继中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="95258-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="95258-111">在“新建转换规则”或“编辑转换规则”页上的“名称”下，键入描述要转换的号码模式的名称。</span><span class="sxs-lookup"><span data-stu-id="95258-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="95258-112"> (可选) 在"说明"下，键入转换规则的说明，例如美国国际长途拨号。</span><span class="sxs-lookup"><span data-stu-id="95258-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="95258-113">在对话框的“构建转换规则”部分的以下字段中输入值：</span><span class="sxs-lookup"><span data-stu-id="95258-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="95258-114">**起始数字**：（可选）指定要使模式与之匹配的号码的前导数字。</span><span class="sxs-lookup"><span data-stu-id="95258-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="95258-115">例如，在此字段输入 +，可与 E.164 格式（以 + 开头）的号码匹配。</span><span class="sxs-lookup"><span data-stu-id="95258-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="95258-116">**长度**：指定匹配模式中的数字位数，并选择希望模式匹配的号码是必须具有此准确长度、至少具有此长度还是可以具有任何长度。</span><span class="sxs-lookup"><span data-stu-id="95258-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="95258-117">例如，在下拉列表中至少输入 11 和 selectAt，以匹配长度至少为 11 位数的号码。</span><span class="sxs-lookup"><span data-stu-id="95258-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="95258-118">**要删除的数字**：（可选）指定要删除的起始数字的位数。</span><span class="sxs-lookup"><span data-stu-id="95258-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="95258-119">例如，输入 1 可去除号码开头的+ 。</span><span class="sxs-lookup"><span data-stu-id="95258-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="95258-120">**要添加的数字**：（可选）指定要附加到转换号码前面的数字。</span><span class="sxs-lookup"><span data-stu-id="95258-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="95258-121">例如，如果要在应用规则时将 011 附加到转换号码的前面，则输入 011。</span><span class="sxs-lookup"><span data-stu-id="95258-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="95258-p106">这些字段中输入的值将反映在“要匹配的模式”和“转换规则”字段中。例如，如果指定前面示例中的值，则“要匹配的模式”字段中生成的正则表达式为：</span><span class="sxs-lookup"><span data-stu-id="95258-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="95258-124">^\+ (\d {9} \d+) $</span><span class="sxs-lookup"><span data-stu-id="95258-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="95258-125">“转换规则”字段指定转换号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="95258-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="95258-126">该模式由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="95258-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="95258-127">代表匹配模式中数字位数的值（例如，$1）</span><span class="sxs-lookup"><span data-stu-id="95258-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="95258-128">（可选）可以通过在“要添加的数字”字段中输入来附加的值</span><span class="sxs-lookup"><span data-stu-id="95258-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="95258-129">使用上述示例值，"转换规则"字段中将显示 011$1。 </span><span class="sxs-lookup"><span data-stu-id="95258-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="95258-130">应用此转换规则后，+441235551010 将变为 011441235551010。</span><span class="sxs-lookup"><span data-stu-id="95258-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="95258-131">单击“确定”保存转换规则。</span><span class="sxs-lookup"><span data-stu-id="95258-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="95258-132">单击“确定”保存 Trunk 配置。</span><span class="sxs-lookup"><span data-stu-id="95258-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="95258-133">在“Trunk 配置”页上，单击“提交”，然后单击“全部提交”。</span><span class="sxs-lookup"><span data-stu-id="95258-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="95258-134">每当创建或修改转换规则时，都必须运行“全部提交”命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="95258-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="95258-135">有关详细信息，请参阅操作文档中的 Publish [pending changes to the voice routing configuration in Skype for Business。](voice-route-config-changes.md)</span><span class="sxs-lookup"><span data-stu-id="95258-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="95258-136">手动定义转换规则</span><span class="sxs-lookup"><span data-stu-id="95258-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="95258-137">打开 Skype for Business Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="95258-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="95258-138">要开始定义转换规则，请按照在 Skype [for Business Server](configure-trunk-with-media-bypass.md) 中配置带媒体旁路的中继的步骤执行步骤 10 或按照步骤 9 在 [Skype for Business Server](configure-trunk-without-media-bypass.md) 中配置没有媒体旁路的中继中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="95258-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="95258-139">在“新建转换规则”或“编辑转换规则”页上的“名称”字段中，键入描述要转换的号码模式的名称。</span><span class="sxs-lookup"><span data-stu-id="95258-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="95258-140"> (可选) 在"说明"中，键入转换规则的说明，例如美国国际长途拨号。</span><span class="sxs-lookup"><span data-stu-id="95258-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="95258-141">单击“构建转换规则”部分底部的“编辑”。</span><span class="sxs-lookup"><span data-stu-id="95258-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="95258-142">在“键入正则表达式”中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="95258-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="95258-143">在“匹配此模式”中，指定将用于匹配要转换的号码的模式。</span><span class="sxs-lookup"><span data-stu-id="95258-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="95258-144">在“转换规则”中，指定转换号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="95258-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="95258-145">例如，如果在"匹配此模式"中输入 ^ (\d \d+) $，在"转换规则"中输入 \+ {9} 011$1，则规则将 +441235551010 转换为 011441235551010。  </span><span class="sxs-lookup"><span data-stu-id="95258-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="95258-146">单击“确定”保存转换规则。</span><span class="sxs-lookup"><span data-stu-id="95258-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="95258-147">单击“确定”保存 Trunk 配置。</span><span class="sxs-lookup"><span data-stu-id="95258-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="95258-148">在“Trunk 配置”页上，单击“提交”，然后单击“全部提交”。</span><span class="sxs-lookup"><span data-stu-id="95258-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95258-149">每当创建或修改转换规则时，都必须运行“全部提交”命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="95258-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="95258-150">有关详细信息，请参阅操作文档中的 Publish [pending changes to the voice routing configuration in Skype for Business。](voice-route-config-changes.md)</span><span class="sxs-lookup"><span data-stu-id="95258-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="95258-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95258-151">See also</span></span>

[<span data-ttu-id="95258-152">在 Skype for Business Server 中配置带媒体旁路的中继</span><span class="sxs-lookup"><span data-stu-id="95258-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="95258-153">在 Skype for Business Server 中配置无媒体旁路的中继</span><span class="sxs-lookup"><span data-stu-id="95258-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="95258-154">在 Skype for Business 中发布对语音路由配置的挂起更改</span><span class="sxs-lookup"><span data-stu-id="95258-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="95258-155">在 Skype for Business Server 中部署媒体旁路</span><span class="sxs-lookup"><span data-stu-id="95258-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)