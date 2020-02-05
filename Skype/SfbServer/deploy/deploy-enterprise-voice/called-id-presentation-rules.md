---
title: 在 Skype for Business Server 中创建或修改呼叫 ID 演示文稿的翻译规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：了解如何使用 Skype for Business Server 中的 "构建翻译规则" 工具定义翻译规则。
ms.openlocfilehash: 1a1f363ad157775395f77ef3e3c2915e9226bfd5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768195"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="3a26c-103">在 Skype for Business Server 中创建或修改呼叫 ID 演示文稿的翻译规则</span><span class="sxs-lookup"><span data-stu-id="3a26c-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="3a26c-104">**摘要：** 了解如何使用 Skype for Business Server 中的 "生成翻译规则" 工具定义翻译规则。</span><span class="sxs-lookup"><span data-stu-id="3a26c-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="3a26c-105">如果要定义翻译规则，请执行以下步骤：在 "**生成翻译规则**" 工具中输入一组值，并启用 "Skype For Business 服务器" 控制面板为你生成相应的匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="3a26c-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="3a26c-106">或者，可以手动编写正则表达式来定义匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="3a26c-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="3a26c-107">有关详细信息，请参阅[Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3a26c-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="3a26c-108">使用“构建转换规则”工具定义规则</span><span class="sxs-lookup"><span data-stu-id="3a26c-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="3a26c-109">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="3a26c-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="3a26c-110">若要开始定义翻译规则，请按照在 Skype for business[服务器的 skype For Business 服务器中配置具有媒体旁路的主干](configure-trunk-with-media-bypass.md)中的步骤，在 skype For business 服务器中通过步骤 9[配置一个干线而不使用媒体旁路](configure-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="3a26c-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="3a26c-111">在“新建转换规则”\*\*\*\* 或“编辑转换规则”\*\*\*\* 页上的“名称”\*\*\*\* 下，键入描述要转换的号码模式的名称。</span><span class="sxs-lookup"><span data-stu-id="3a26c-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="3a26c-112">可选在 "**说明**" 下，键入翻译规则的描述，例如 "美国国际长途拨号"。</span><span class="sxs-lookup"><span data-stu-id="3a26c-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="3a26c-113">在对话框的“构建转换规则”\*\*\*\* 部分的以下字段中输入值：</span><span class="sxs-lookup"><span data-stu-id="3a26c-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="3a26c-114">**起始数字**：（可选）指定要使模式与之匹配的号码的前导数字。</span><span class="sxs-lookup"><span data-stu-id="3a26c-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="3a26c-115">例如，在此字段输入 +，可与 E.164 格式（以 + 开头）的号码匹配。</span><span class="sxs-lookup"><span data-stu-id="3a26c-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="3a26c-116">**长度**：指定匹配模式中的数字位数，并选择希望模式匹配的号码是必须具有此准确长度、至少具有此长度还是可以具有任何长度。</span><span class="sxs-lookup"><span data-stu-id="3a26c-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="3a26c-117">例如，在下拉列表中最少输入11和 selectAt，以匹配长度至少为11位的数字。</span><span class="sxs-lookup"><span data-stu-id="3a26c-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="3a26c-118">**要删除的数字**：（可选）指定要删除的起始数字的位数。</span><span class="sxs-lookup"><span data-stu-id="3a26c-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="3a26c-119">例如，输入 "1" 将从号码的开头去掉 +。</span><span class="sxs-lookup"><span data-stu-id="3a26c-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="3a26c-120">**要添加的数字**：（可选）指定要附加到转换号码前面的数字。</span><span class="sxs-lookup"><span data-stu-id="3a26c-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="3a26c-121">例如，如果要在应用规则时将 011 附加到转换号码的前面，则输入 011。</span><span class="sxs-lookup"><span data-stu-id="3a26c-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="3a26c-p106">这些字段中输入的值将反映在“要匹配的模式”\*\*\*\* 和“转换规则”\*\*\*\* 字段中。例如，如果指定前面示例中的值，则“要匹配的模式”\*\*\*\* 字段中生成的正则表达式为：</span><span class="sxs-lookup"><span data-stu-id="3a26c-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="3a26c-124">^\+（\d{9}\d +） $</span><span class="sxs-lookup"><span data-stu-id="3a26c-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="3a26c-125">“转换规则”\*\*\*\* 字段指定转换号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="3a26c-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="3a26c-126">该模式由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="3a26c-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="3a26c-127">代表匹配模式中数字位数的值（例如，$1）</span><span class="sxs-lookup"><span data-stu-id="3a26c-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="3a26c-128">（可选）可以通过在“要添加的数字”\*\*\*\* 字段中输入来附加的值</span><span class="sxs-lookup"><span data-stu-id="3a26c-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="3a26c-129">使用前面的示例值，011 $ 1 显示在 "**翻译规则**" 字段中。</span><span class="sxs-lookup"><span data-stu-id="3a26c-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="3a26c-130">应用此转换规则后，+441235551010 将变为 011441235551010。</span><span class="sxs-lookup"><span data-stu-id="3a26c-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="3a26c-131">单击“确定”\*\*\*\* 保存转换规则。</span><span class="sxs-lookup"><span data-stu-id="3a26c-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="3a26c-132">单击“确定”\*\*\*\* 保存中继配置。</span><span class="sxs-lookup"><span data-stu-id="3a26c-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="3a26c-133">在“Trunk 配置”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a26c-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3a26c-134">每当创建或修改转换规则时，都必须运行“全部提交”\*\*\*\* 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="3a26c-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="3a26c-135">有关详细信息，请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。</span><span class="sxs-lookup"><span data-stu-id="3a26c-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="3a26c-136">手动定义转换规则</span><span class="sxs-lookup"><span data-stu-id="3a26c-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="3a26c-137">打开 "Skype for Business 服务器" 控制面板</span><span class="sxs-lookup"><span data-stu-id="3a26c-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="3a26c-138">若要开始定义翻译规则，请按照在 Skype for business[服务器的 skype For Business 服务器中配置具有媒体旁路的主干](configure-trunk-with-media-bypass.md)中的步骤，在 skype For business 服务器中通过步骤 9[配置一个干线而不使用媒体旁路](configure-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="3a26c-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="3a26c-139">在“新建转换规则”\*\*\*\* 或“编辑转换规则”\*\*\*\* 页上的“名称”\*\*\*\* 字段中，键入描述要转换的号码模式的名称。</span><span class="sxs-lookup"><span data-stu-id="3a26c-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="3a26c-140">可选在 "**说明**" 中，键入翻译规则的描述，例如 "美国国际长途拨号"。</span><span class="sxs-lookup"><span data-stu-id="3a26c-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="3a26c-141">单击“构建转换规则”\*\*\*\* 部分底部的“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a26c-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="3a26c-142">在“键入正则表达式”\*\*\*\* 中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="3a26c-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="3a26c-143">在“匹配此模式”\*\*\*\* 中，指定将用于匹配要转换的号码的模式。</span><span class="sxs-lookup"><span data-stu-id="3a26c-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="3a26c-144">在“转换规则”\*\*\*\* 中，指定转换号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="3a26c-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="3a26c-145">例如，如果在 "**翻译规则**" 中{9}输入 "^\+" （\D \d +） $ 以**匹配此模式**and011 $ 1，则规则会将 + 441235551010 转换为011441235551010。</span><span class="sxs-lookup"><span data-stu-id="3a26c-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="3a26c-146">单击“确定”\*\*\*\* 保存转换规则。</span><span class="sxs-lookup"><span data-stu-id="3a26c-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="3a26c-147">单击“确定”\*\*\*\* 保存中继配置。</span><span class="sxs-lookup"><span data-stu-id="3a26c-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="3a26c-148">在“Trunk 配置”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a26c-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a26c-149">每当创建或修改转换规则时，都必须运行“全部提交”\*\*\*\* 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="3a26c-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="3a26c-150">有关详细信息，请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。</span><span class="sxs-lookup"><span data-stu-id="3a26c-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a26c-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a26c-151">See also</span></span>

[<span data-ttu-id="3a26c-152">在 Skype for Business 服务器中使用 "媒体绕过" 配置主干</span><span class="sxs-lookup"><span data-stu-id="3a26c-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="3a26c-153">在 Skype for Business 服务器中配置不使用媒体的主干</span><span class="sxs-lookup"><span data-stu-id="3a26c-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="3a26c-154">发布 Skype for Business 中的语音路由配置的待处理更改</span><span class="sxs-lookup"><span data-stu-id="3a26c-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="3a26c-155">在 Skype for Business 服务器中部署媒体旁路</span><span class="sxs-lookup"><span data-stu-id="3a26c-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

