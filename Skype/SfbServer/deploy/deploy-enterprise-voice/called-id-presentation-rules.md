---
title: 在 Skype for Business Server 2015 中创建或修改来电显示的转换规则
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 摘要： 了解如何通过使用生成的转换规则工具的 Skype 中的业务服务器 2015年定义转换规则。
ms.openlocfilehash: eeff210b409d9d53ae54a30041207cffaa618f32
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500870"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server-2015"></a><span data-ttu-id="bd142-103">在 Skype for Business Server 2015 中创建或修改来电显示的转换规则</span><span class="sxs-lookup"><span data-stu-id="bd142-103">Create or modify a translation rule for called ID presentation in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bd142-104">**摘要：** 了解如何通过使用生成的转换规则工具的 Skype 中的业务服务器 2015年定义转换规则。</span><span class="sxs-lookup"><span data-stu-id="bd142-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="bd142-105">如果您想要在**建立转换规则**工具中输入的一组值和启用业务 Server 控制面板为您生成的相应匹配模式和转换规则的 Skype 定义转换规则，请按照以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bd142-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="bd142-106">或者，可以手动编写正则表达式来定义匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="bd142-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="bd142-107">有关详细信息，请参阅[创建或修改转换规则手动](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bd142-107">For details, see [Create or Modify a Translation Rule Manually](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>
  
### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="bd142-108">使用“构建转换规则”工具定义规则</span><span class="sxs-lookup"><span data-stu-id="bd142-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="bd142-109">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="bd142-109">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="bd142-110">要开始定义转换规则，请按照中的步骤[配置与媒体中继绕过中的业务服务器 2015 Skype](configure-trunk-with-media-bypass.md)通过 10 个步骤或[配置无媒体中继绕过中的业务服务器 2015 Skype](configure-trunk-without-media-bypass.md)前 9 个步骤。</span><span class="sxs-lookup"><span data-stu-id="bd142-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server 2015](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server 2015](configure-trunk-without-media-bypass.md) through step 9.</span></span>
    
3. <span data-ttu-id="bd142-111">在“新建转换规则”**** 或“编辑转换规则”**** 页上的“名称”**** 下，键入描述要转换的号码模式的名称。</span><span class="sxs-lookup"><span data-stu-id="bd142-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>
    
4. <span data-ttu-id="bd142-112">（可选）在**说明**，键入转换规则，例如，美国国际长途拨号的说明。</span><span class="sxs-lookup"><span data-stu-id="bd142-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>
    
5. <span data-ttu-id="bd142-113">在对话框的“构建转换规则”**** 部分的以下字段中输入值：</span><span class="sxs-lookup"><span data-stu-id="bd142-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
   - <span data-ttu-id="bd142-114">**起始数字**：（可选）指定要使模式与之匹配的号码的前导数字。</span><span class="sxs-lookup"><span data-stu-id="bd142-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="bd142-115">例如，输入 + 在此字段匹配的 E.164 号码设置的格式 (其中开头 +)。</span><span class="sxs-lookup"><span data-stu-id="bd142-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>
    
   - <span data-ttu-id="bd142-116">**长度**：指定匹配模式中的数字位数，并选择希望模式匹配的号码是必须具有此准确长度、至少具有此长度还是可以具有任何长度。</span><span class="sxs-lookup"><span data-stu-id="bd142-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="bd142-117">例如，输入 11 和 selectAt 最匹配的长度至少 11 位数字的号码下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="bd142-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
   - <span data-ttu-id="bd142-118">**要删除的数字**：（可选）指定要删除的起始数字的位数。</span><span class="sxs-lookup"><span data-stu-id="bd142-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="bd142-119">例如，输入 1 去掉 + 从编号的开头。</span><span class="sxs-lookup"><span data-stu-id="bd142-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>
    
   - <span data-ttu-id="bd142-120">**要添加的数字**：（可选）指定要附加到转换号码前面的数字。</span><span class="sxs-lookup"><span data-stu-id="bd142-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="bd142-121">如果您希望 011 应用规则时要预置到转换后的号码，例如，输入 011。</span><span class="sxs-lookup"><span data-stu-id="bd142-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="bd142-p106">这些字段中输入的值将反映在“要匹配的模式”**** 和“转换规则”**** 字段中。例如，如果指定前面示例中的值，则“要匹配的模式”**** 字段中生成的正则表达式为：</span><span class="sxs-lookup"><span data-stu-id="bd142-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="bd142-124">^\+(\d{9}\d+)$</span><span class="sxs-lookup"><span data-stu-id="bd142-124">^\+(\d{9}\d+)$</span></span>
    
    <span data-ttu-id="bd142-p107">“转换规则”**** 字段指定转换号码格式的模式。该模式由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="bd142-p107">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
   - <span data-ttu-id="bd142-127">一个代表匹配模式中的位数的值 (例如，$1)</span><span class="sxs-lookup"><span data-stu-id="bd142-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>
    
   - <span data-ttu-id="bd142-128">（可选）可以通过在“要添加的数字”**** 字段中输入来附加的值</span><span class="sxs-lookup"><span data-stu-id="bd142-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="bd142-129">使用前面示例中的值，011$ 1 显示在**转换规则**字段。</span><span class="sxs-lookup"><span data-stu-id="bd142-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="bd142-130">应用此转换规则后，+441235551010 将变为 011441235551010。</span><span class="sxs-lookup"><span data-stu-id="bd142-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>
    
6. <span data-ttu-id="bd142-131">单击“确定”**** 保存转换规则。</span><span class="sxs-lookup"><span data-stu-id="bd142-131">Click **OK** to save the translation rule.</span></span>
    
7. <span data-ttu-id="bd142-132">单击“确定”**** 保存中继配置。</span><span class="sxs-lookup"><span data-stu-id="bd142-132">Click **OK** to save the trunk configuration.</span></span>
    
8. <span data-ttu-id="bd142-133">在“Trunk 配置”**** 页上，单击“提交”****，然后单击“全部提交”****。</span><span class="sxs-lookup"><span data-stu-id="bd142-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="bd142-134">每当创建或修改转换规则时，都必须运行“全部提交”**** 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="bd142-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="bd142-135">有关详细信息，请参阅操作文档中的[挂起更改语音路由配置中的业务 2015 Skype 的发布](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="bd142-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="bd142-136">手动定义转换规则</span><span class="sxs-lookup"><span data-stu-id="bd142-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="bd142-137">打开 Skype 业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="bd142-137">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="bd142-138">要开始定义转换规则，请按照中的步骤[配置与媒体中继绕过中的业务服务器 2015 Skype](configure-trunk-with-media-bypass.md)通过 10 个步骤或[配置无媒体中继绕过中的业务服务器 2015 Skype](configure-trunk-without-media-bypass.md)前 9 个步骤。</span><span class="sxs-lookup"><span data-stu-id="bd142-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server 2015](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server 2015](configure-trunk-without-media-bypass.md) through step 9.</span></span>
    
3. <span data-ttu-id="bd142-139">在“新建转换规则”**** 或“编辑转换规则”**** 页上的“名称”**** 字段中，键入描述要转换的号码模式的名称。</span><span class="sxs-lookup"><span data-stu-id="bd142-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>
    
4. <span data-ttu-id="bd142-140">（可选）在**说明**框中，键入说明的转换规则，例如，美国国际长途拨号。</span><span class="sxs-lookup"><span data-stu-id="bd142-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>
    
5. <span data-ttu-id="bd142-141">单击“构建转换规则”**** 部分底部的“编辑”****。</span><span class="sxs-lookup"><span data-stu-id="bd142-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>
    
6. <span data-ttu-id="bd142-142">在“键入正则表达式”**** 中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="bd142-142">Enter the following in **Type a Regular Expression**:</span></span>
    
   - <span data-ttu-id="bd142-143">在“匹配此模式”**** 中，指定将用于匹配要转换的号码的模式。</span><span class="sxs-lookup"><span data-stu-id="bd142-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
   - <span data-ttu-id="bd142-144">在“转换规则”**** 中，指定转换号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="bd142-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="bd142-145">例如，如果输入 ^\+(\d{9}中**匹配此模式**and011 \d+)$ $1，在**转换规则**，该规则会将 + 441235551010 转换为 011441235551010。</span><span class="sxs-lookup"><span data-stu-id="bd142-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>
    
7. <span data-ttu-id="bd142-146">单击“确定”**** 保存转换规则。</span><span class="sxs-lookup"><span data-stu-id="bd142-146">Click **OK** to save the translation rule.</span></span>
    
8. <span data-ttu-id="bd142-147">单击“确定”**** 保存中继配置。</span><span class="sxs-lookup"><span data-stu-id="bd142-147">Click **OK** to save the trunk configuration.</span></span>
    
9. <span data-ttu-id="bd142-148">在“Trunk 配置”**** 页上，单击“提交”****，然后单击“全部提交”****。</span><span class="sxs-lookup"><span data-stu-id="bd142-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bd142-149">每当创建或修改转换规则时，都必须运行“全部提交”**** 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="bd142-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="bd142-150">有关详细信息，请参阅操作文档中的[挂起更改语音路由配置中的业务 2015 Skype 的发布](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="bd142-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bd142-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd142-151">See also</span></span>

[<span data-ttu-id="bd142-152">为业务服务器 2015年使用 Skype 中的媒体旁路配置中继</span><span class="sxs-lookup"><span data-stu-id="bd142-152">Configure a trunk with media bypass in Skype for Business Server 2015</span></span>](configure-trunk-with-media-bypass.md)
  
[<span data-ttu-id="bd142-153">配置无媒体绕过 Skype 中的业务服务器 2015年的中继</span><span class="sxs-lookup"><span data-stu-id="bd142-153">Configure a trunk without media bypass in Skype for Business Server 2015</span></span>](configure-trunk-without-media-bypass.md)
  
[<span data-ttu-id="bd142-154">挂起更改语音路由配置中的业务 2015 Skype 的发布</span><span class="sxs-lookup"><span data-stu-id="bd142-154">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="bd142-155">部署业务服务器 2015 Skype 中的媒体绕过</span><span class="sxs-lookup"><span data-stu-id="bd142-155">Deploy media bypass in Skype for Business Server 2015</span></span>](deploy-media-bypass.md)