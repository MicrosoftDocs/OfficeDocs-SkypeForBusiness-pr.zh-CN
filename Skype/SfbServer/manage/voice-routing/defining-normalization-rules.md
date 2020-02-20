---
title: 在 Skype for Business Server 中定义规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 规范化规则使用 .NET Framework 正则表达式将拨打的电话号码转换为. 164 格式;换言之，规范化规则采用用户拨打的电话号码，并将该号码转换为 Skype for Business Server 在内部使用的格式。 必须将每个拨号计划分配给一个或多个规范化规则。
ms.openlocfilehash: 2fd7f59bcebcfe676a03ce5a6a897336551ddbad
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151212"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a><span data-ttu-id="43cc6-104">在 Skype for Business Server 中定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="43cc6-104">Defining normalization rules in Skype for Business Server</span></span>

<span data-ttu-id="43cc6-105">Skype for Business Server 规范化规则使用 .NET Framework 正则表达式将拨打的电话号码转换为. 164 格式;换言之，规范化规则采用用户拨打的电话号码，并将该号码转换为 Skype for Business Server 在内部使用的格式。</span><span class="sxs-lookup"><span data-stu-id="43cc6-105">Skype for Business Server normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Skype for Business Server.</span></span> <span data-ttu-id="43cc6-106">必须将每个拨号计划分配给一个或多个规范化规则。</span><span class="sxs-lookup"><span data-stu-id="43cc6-106">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="43cc6-107">有关规范化规则的详细信息，请参阅[拨号计划和规范化规则](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="43cc6-107">For details about normalization rules, see [Dial plans and normalization rules](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx).</span></span>

<span data-ttu-id="43cc6-108">有关如何编写正则表达式的详细信息，请参阅[.Net Framework 正则表达式](https://go.microsoft.com/fwlink/p/?linkId=140927)。</span><span class="sxs-lookup"><span data-stu-id="43cc6-108">For details about how to write regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span>

<span data-ttu-id="43cc6-109">可以使用以下任一方法定义或编辑规范化规则：</span><span class="sxs-lookup"><span data-stu-id="43cc6-109">You can use either of the following methods to define or edit a normalization rule:</span></span>
- <span data-ttu-id="43cc6-110">[使用 "**生成规范化规则**" 工具](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule)来指定起始数字、长度、要删除的数字和要添加的数字的值，然后让 Skype for business Server 控制面板为您生成相应的匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="43cc6-110">[Use the **Build a Normalization Rule** tool](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) to specify values for the starting digits, length, digits to remove and digits to add, and then let Skype for Business Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>
- <span data-ttu-id="43cc6-111">[手动写入正则表达式](#create-or-modify-a-normalization-rule-manually)，以定义匹配的模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="43cc6-111">[Write regular expressions manually](#create-or-modify-a-normalization-rule-manually) to define the matching pattern and translation rule.</span></span> 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="43cc6-112">使用生成规范化规则创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="43cc6-112">Create or modify a normalization rule by using Build a Normalization Rule</span></span>

<span data-ttu-id="43cc6-113">如果要在 Skype for Business Server 控制面板中创建或修改规范化规则，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="43cc6-113">Complete the following steps if you want to create or modify a normalization rule in Skype for Business Server Control Panel.</span></span> 

<span data-ttu-id="43cc6-114">**使用“建立规范化规则”定义规则**</span><span class="sxs-lookup"><span data-stu-id="43cc6-114">**To define a rule by using Build a Normalization Rule**</span></span>

1. <span data-ttu-id="43cc6-115">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="43cc6-115">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="43cc6-116">有关详细信息，请参阅[委派安装权限](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="43cc6-116">For details, see [Delegate setup permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).</span></span>
2. <span data-ttu-id="43cc6-117">打开浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="43cc6-117">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="43cc6-118">有关可用于启动 Skype for Business 控制面板的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="43cc6-118">For details about the different methods you can use to start the Skype for Business Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="43cc6-119">Optional按照在步骤11中[创建拨号计划](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan)中的步骤或通过步骤 10[修改拨号计划](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan)。</span><span class="sxs-lookup"><span data-stu-id="43cc6-119">(Optional) Follow the steps in [Create a dial plan](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) through step 11 or [Modify a dial plan](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) through step 10.</span></span> 
4. <span data-ttu-id="43cc6-120">在“新建规范化规则”\*\*\*\* 或“编辑规范化规则”\*\*\*\* 的“名称”\*\*\*\* 中，键入描述要进行规范化的号码模式的名称（例如，**5DigitExtension**）。</span><span class="sxs-lookup"><span data-stu-id="43cc6-120">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>
5. <span data-ttu-id="43cc6-121">（可选）在“描述”\*\*\*\* 中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。</span><span class="sxs-lookup"><span data-stu-id="43cc6-121">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>
6. <span data-ttu-id="43cc6-122">在“建立规范化规则”\*\*\*\* 的以下字段中输入值：</span><span class="sxs-lookup"><span data-stu-id="43cc6-122">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    - <span data-ttu-id="43cc6-123">**起始数字**：（可选）指定您希望模式匹配的拨打号码的前导数字。</span><span class="sxs-lookup"><span data-stu-id="43cc6-123">**Starting digits**:   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="43cc6-124">例如，如果要使模式与以 425 开头的拨打号码匹配，则键入 **425**。</span><span class="sxs-lookup"><span data-stu-id="43cc6-124">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    - <span data-ttu-id="43cc6-125">**Length**：指定匹配模式中的位数，并选择您是否希望模式与此长度完全匹配，匹配至少为此长度的拨叫号码，或匹配任意长度的拨出号码。</span><span class="sxs-lookup"><span data-stu-id="43cc6-125">**Length**:   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    - <span data-ttu-id="43cc6-126">**要删除的数字**：（可选）指定要从所需模式匹配的拨叫号码中删除的起始数字的数量。</span><span class="sxs-lookup"><span data-stu-id="43cc6-126">**Digits to remove**:   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    - <span data-ttu-id="43cc6-127">**要添加的数字**：（可选）指定要添加到要模式匹配的拨打号码的数字。</span><span class="sxs-lookup"><span data-stu-id="43cc6-127">**Digits to add**:   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="43cc6-128">这些字段中输入的值将反映在“要匹配的模式”\*\*\*\* 和“转换规则”\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="43cc6-128">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="43cc6-129">例如，如果将**起始数字**保留为空，请在**长度**字段中键入**7**选择 "**完全**"，并指定**要删除的数字**为**0** ，要**匹配的模式**中的结果正则表达式为：</span><span class="sxs-lookup"><span data-stu-id="43cc6-129">For example, if you leave **Starting digits** empty, type **7** into the **Length** field select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

    <span data-ttu-id="43cc6-130">**^ （\d{7}） $**</span><span class="sxs-lookup"><span data-stu-id="43cc6-130">**^(\d{7})$**</span></span>

7. <span data-ttu-id="43cc6-131">在“转换规则”\*\*\*\* 中，指定转换后的 E.164 电话号码格式的模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="43cc6-131">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    - <span data-ttu-id="43cc6-132">代表匹配模式中指定的号码位数的值。</span><span class="sxs-lookup"><span data-stu-id="43cc6-132">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="43cc6-133">例如，如果匹配模式是 **^ （\d{7}） $**，则转换规则中的 $1 代表7位拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="43cc6-133">For example, if the matching pattern is **^(\d{7})$**, then $1 in the translation rule represents 7-digit dialed numbers.</span></span>
    - <span data-ttu-id="43cc6-134">（可选）在“要添加的数字”\*\*\*\* 字段中键入值，指定要附加到转换后的号码前面的数字（例如 **+1425**）。</span><span class="sxs-lookup"><span data-stu-id="43cc6-134">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="43cc6-135">例如，如果**要匹配的模式**包含 **^ （\d{7}） $** 作为拨打的号码和**转换规则**的模式，则包含 **+ 1425 $ 1**作为 e.164 电话号码的模式，该规则会将5550100规范化为 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="43cc6-135">For example, if **Pattern to match** contains **^(\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8. <span data-ttu-id="43cc6-136">（可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="43cc6-136">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>
9. <span data-ttu-id="43cc6-p108">（可选）输入一个号码以测试规范化规则，然后单击“执行”\*\*\*\*。测试结果会显示在“输入要测试的号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="43cc6-p108">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    > [!Note] 
    > <span data-ttu-id="43cc6-139">您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。</span><span class="sxs-lookup"><span data-stu-id="43cc6-139">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="43cc6-140">有关详细信息，请参阅[测试语音路由](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="43cc6-140">For details, see [Test voice routing](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx).</span></span> 

10. <span data-ttu-id="43cc6-141">单击“确定”\*\*\*\* 保存规范化规则。</span><span class="sxs-lookup"><span data-stu-id="43cc6-141">Click **OK** to save the normalization rule.</span></span>
11. <span data-ttu-id="43cc6-142">单击“确定”\*\*\*\* 保存拨号计划。</span><span class="sxs-lookup"><span data-stu-id="43cc6-142">Click **OK** to save the dial plan.</span></span>
12. <span data-ttu-id="43cc6-143">在“拨号计划”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="43cc6-143">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span> 
    > [!Note]
    > <span data-ttu-id="43cc6-144">无论何时创建或更改规范化规则，都必须运行“全部提交”命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="43cc6-144">Whenever you create or change a normalization rule, you must run the Commit all command to publish the configuration change.</span></span> <span data-ttu-id="43cc6-145">有关详细信息，请参阅[发布待处理的语音路由配置更改](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="43cc6-145">For details, see [Publish pending changes to the voice routing configuration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx).</span></span> 

## <a name="create-or-modify-a-normalization-rule-manually"></a><span data-ttu-id="43cc6-146">手动创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="43cc6-146">Create or modify a normalization rule manually</span></span>

<span data-ttu-id="43cc6-147">如果要手动创建或修改规范化规则，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="43cc6-147">Complete the following steps if you want to create or modify a normalization rule manually.</span></span>

<span data-ttu-id="43cc6-148">**手动定义规范化规则**</span><span class="sxs-lookup"><span data-stu-id="43cc6-148">**To define a normalization rule manually**</span></span>

1. <span data-ttu-id="43cc6-149">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="43cc6-149">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="43cc6-150">有关详细信息，请参阅[委派安装权限](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="43cc6-150">For details, see [Delegate setup permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).</span></span>
2. <span data-ttu-id="43cc6-151">打开浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="43cc6-151">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="43cc6-152">有关可用于启动 Skype for Business 控制面板的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="43cc6-152">For details about the different methods you can use to start the Skype for Business Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="43cc6-153">Optional按照在步骤11中[创建拨号计划](GET LINK AFTER MIGRATION)中的步骤或通过步骤 10[修改拨号计划](GET LINK AFTER MIGRATION)。</span><span class="sxs-lookup"><span data-stu-id="43cc6-153">(Optional) Follow the steps in [Create a dial plan](GET LINK AFTER MIGRATION) through step 11 or [Modify a dial plan](GET LINK AFTER MIGRATION) through step 10.</span></span>  
4. <span data-ttu-id="43cc6-154">在“新建规范化规则”\*\*\*\* 或“编辑规范化规则”\*\*\*\* 的“名称”\*\*\*\* 中，键入描述要进行规范化的号码模式的名称（例如，将规范化规则命名为 **5DigitExtension**）。</span><span class="sxs-lookup"><span data-stu-id="43cc6-154">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule **5DigitExtension**).</span></span>
5. <span data-ttu-id="43cc6-155">（可选）在“描述”\*\*\*\* 中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。</span><span class="sxs-lookup"><span data-stu-id="43cc6-155">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>
6. <span data-ttu-id="43cc6-156">在“建立规范化规则”\*\*\*\* 中，单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="43cc6-156">In **Build a Normalization Rule**, click **Edit**.</span></span>
7. <span data-ttu-id="43cc6-157">在“键入正则表达式”中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="43cc6-157">Enter the following in Type a Regular Expression:</span></span>
    - <span data-ttu-id="43cc6-158">在“匹配此模式”\*\*\*\* 中，指定要用于匹配拨打的电话号码的模式。</span><span class="sxs-lookup"><span data-stu-id="43cc6-158">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    - <span data-ttu-id="43cc6-159">在“转换规则”\*\*\*\* 中，指定转换后的 E.164 电话号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="43cc6-159">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

    <span data-ttu-id="43cc6-160">例如，如果在**转换规则**中输入 " **^ （\d{7}） $** " 与**此模式**和 **+ 1425 $ 1**相匹配，则该规则会将5550100规范化为 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="43cc6-160">For example, if you enter **^(\d{7})$** in **Match this pattern** and **+1425$1** in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

8. <span data-ttu-id="43cc6-161">（可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="43cc6-161">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>
9. <span data-ttu-id="43cc6-p113">（可选）输入一个号码以测试规范化规则，然后单击“执行”\*\*\*\*。测试结果会显示在“输入要测试的号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="43cc6-p113">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!Note]
    > <span data-ttu-id="43cc6-164">您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。</span><span class="sxs-lookup"><span data-stu-id="43cc6-164">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="43cc6-165">有关详细信息，请参阅[测试语音路由](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="43cc6-165">For details, see [Test voice routing](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx).</span></span> 

10. <span data-ttu-id="43cc6-166">单击“确定”\*\*\*\* 保存规范化规则。</span><span class="sxs-lookup"><span data-stu-id="43cc6-166">Click **OK** to save the normalization rule.</span></span>
11. <span data-ttu-id="43cc6-167">单击“确定”\*\*\*\* 保存拨号计划。</span><span class="sxs-lookup"><span data-stu-id="43cc6-167">Click **OK** to save the dial plan.</span></span>
12. <span data-ttu-id="43cc6-168">在 "**拨号计划**" 页上，单击 " **Commi**t"，然后单击 "**全部提交**"。</span><span class="sxs-lookup"><span data-stu-id="43cc6-168">On the **Dial Plan** page, click **Commi**t, and then click **Commit all**.</span></span> 
