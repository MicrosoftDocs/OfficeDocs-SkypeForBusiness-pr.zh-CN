---
title: 在 Skype for Business 中创建或修改语音路由
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
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 摘要：了解如何使用 Skype for Business Server 控制面板在 Skype for Business Server 中创建或修改语音路由。
ms.openlocfilehash: c9f1a234bf8aeeb1bfeb05f1464a48eb0e964405
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820452"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a><span data-ttu-id="d2409-103">在 Skype for Business 中创建或修改语音路由</span><span class="sxs-lookup"><span data-stu-id="d2409-103">Create or modify a voice route in Skype for Business</span></span>
 
<span data-ttu-id="d2409-104">**摘要：** 了解如何使用 Skype for Business Server 控制面板在 Skype for Business Server 中创建或修改语音路由。</span><span class="sxs-lookup"><span data-stu-id="d2409-104">**Summary:** Learn how to create or modify a voice route in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="d2409-105">使用 Skype for Business Server 控制面板创建语音路由</span><span class="sxs-lookup"><span data-stu-id="d2409-105">To create a voice route by using the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d2409-106">以 RTCUniversalServerAdmins 组成员或 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="d2409-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="d2409-107">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="d2409-107">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d2409-108">在左侧导航栏中，单击 **“语音路由”**。</span><span class="sxs-lookup"><span data-stu-id="d2409-108">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="d2409-109">单击“路由”。</span><span class="sxs-lookup"><span data-stu-id="d2409-109">Click **Route**.</span></span>
    
5. <span data-ttu-id="d2409-110">单击 **“新建”** 以显示 **“新建语音路由”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="d2409-110">Click **New** to display the **New Voice Route** dialog box.</span></span>
    
6. <span data-ttu-id="d2409-111">在 **"名称**"中，键入语音路由的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="d2409-111">In **Name**, type a descriptive name for the voice route.</span></span>
    
7. <span data-ttu-id="d2409-112"> (") ，键入语音路由的其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="d2409-112">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>
    
8. <span data-ttu-id="d2409-113">若要指定希望此路由适应的模式，可以使用"生成模式以匹配工具"来生成正则表达式，也可以手动编写正则表达式。</span><span class="sxs-lookup"><span data-stu-id="d2409-113">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
   - <span data-ttu-id="d2409-p101">要使用 **“建立匹配的模式”** 工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：</span><span class="sxs-lookup"><span data-stu-id="d2409-p101">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
    
   - <span data-ttu-id="d2409-116">**希望允许的号码起始数字**：输入此路由必须满足的前缀值（如有必要，包括前导 +）。</span><span class="sxs-lookup"><span data-stu-id="d2409-116">**Starting digits for numbers that you want to allow**: Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="d2409-117">例如，键入 +425，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="d2409-117">For example, type +425, and then click **Add**.</span></span> <span data-ttu-id="d2409-118">对希望包含在路由中的每个前缀值重复此过程。</span><span class="sxs-lookup"><span data-stu-id="d2409-118">Repeat this for each prefix value that you want to include in the route.</span></span>
    
   - <span data-ttu-id="d2409-119">**例外**：如果要为前缀值指定一个或多个例外，请突出显示相应的前缀并单击 **“例外”**。</span><span class="sxs-lookup"><span data-stu-id="d2409-119">**Exceptions**: If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="d2409-120">为不希望此路由容纳的匹配  *模式键入一*  个或多个值。</span><span class="sxs-lookup"><span data-stu-id="d2409-120">Type in one or more values for the matching patterns that you do  *not*  want this route to accommodate.</span></span> <span data-ttu-id="d2409-121">例如，若要从路由中排除以 +425237 开始的数字，请在"例外"字段中输入 +425237 的值，然后单击"**确定"。** </span><span class="sxs-lookup"><span data-stu-id="d2409-121">For example, to exclude numbers starting with +425237 from the route, enter a value of+425237 in the **Exceptions** field, and then click **OK**.</span></span>
    
   - <span data-ttu-id="d2409-122">若要手动定义匹配模式，请在“构建要匹配的模式”工具中单击“编辑”，然后键入 .NET Framework 正则表达式，以便为应用路由的目标电话号码指定匹配模式。</span><span class="sxs-lookup"><span data-stu-id="d2409-122">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="d2409-123">若要详细了解如何编写正则表达式，请参阅[".NET Framework 正则表达式"。](https://go.microsoft.com/fwlink/p/?linkId=140927)</span><span class="sxs-lookup"><span data-stu-id="d2409-123">For details about how to write regular expressions, see [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span> 
    
9. <span data-ttu-id="d2409-124">如果不希望对呼叫接收人显示发起出站呼叫的电话的 ID，请选择 **“隐藏呼叫者 ID”**。</span><span class="sxs-lookup"><span data-stu-id="d2409-124">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="d2409-125">如果选择此选项，则必须指定将在收件人的呼叫者 **ID** 显示器上显示的备用呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="d2409-125">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient's caller ID display.</span></span>
    
10. <span data-ttu-id="d2409-126">若要将一个或多个中继与语音路由关联，请单击"添加"，然后从列表中选择中继。</span><span class="sxs-lookup"><span data-stu-id="d2409-126">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
11. <span data-ttu-id="d2409-127">若要将一个或多个公用电话交换网 (PSTN) 用法与语音路由关联，请单击"选择"，然后从为 企业语音 部署定义的 PSTN 用法记录列表中选择一条记录。</span><span class="sxs-lookup"><span data-stu-id="d2409-127">To associate one or more Public Switched Telephone Network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d2409-128">若要查看每个可用的 PSTN 用法记录的属性，请参阅查看 Skype for Business 中的 [PSTN 用法记录](view-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="d2409-128">To view the properties of each of the available PSTN usage records, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span> <span data-ttu-id="d2409-129">> 创建或编辑 PSTN 用法记录，请参阅"创建或修改语音策略"，并配置 Skype for Business 中的 [PSTN 用法记录](voice-policy-and-pstn-usage-records.md)</span><span class="sxs-lookup"><span data-stu-id="d2409-129">> To create or edit PSTN usage records, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md)</span></span>
  
12. <span data-ttu-id="d2409-130">排列 PSTN 用法记录以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="d2409-130">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="d2409-131">若要更改记录在列表中的位置，请突出显示记录名称，然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="d2409-131">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d2409-132">与语音策略（其中 PSTN 用法记录的列出顺序非常重要）相反，PSTN 用法记录在语音路由中的列出顺序无关紧要。</span><span class="sxs-lookup"><span data-stu-id="d2409-132">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="d2409-133">但是，建议您按使用频率组织列表。</span><span class="sxs-lookup"><span data-stu-id="d2409-133">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="d2409-134">例如：RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="d2409-134">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="d2409-135"> (Skype for Business Server 从上到下遍历列表。) </span><span class="sxs-lookup"><span data-stu-id="d2409-135">(Skype for Business Server traverses the list from the top down.)</span></span> 
  
13. <span data-ttu-id="d2409-p109">（可选）在 **“输入转换后的号码以进行测试”** 字段中键入一个值，然后单击 **“执行”**。测试结果将显示在该字段下面。</span><span class="sxs-lookup"><span data-stu-id="d2409-p109">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
14. <span data-ttu-id="d2409-138">单击 **“确定”** 保存语音路由。</span><span class="sxs-lookup"><span data-stu-id="d2409-138">Click **OK** to save the voice route.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d2409-139">任何时候创建语音路由，都必须运行 **"全部提交** "命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="d2409-139">Whenever you create a voice route, you must run the **Commit All** command to publish the configuration change.</span></span> <span data-ttu-id="d2409-140">有关详细信息，请参阅在 Skype for Business 中发布对语音 [路由配置的挂起更改](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="d2409-140">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md).</span></span> 
  
### <a name="to-modify-a-voice-route"></a><span data-ttu-id="d2409-141">修改语音路由</span><span class="sxs-lookup"><span data-stu-id="d2409-141">To modify a voice route</span></span>

1. <span data-ttu-id="d2409-142">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="d2409-142">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="d2409-143">在左侧导航栏中，单击“语音路由”，然后单击“路由”。</span><span class="sxs-lookup"><span data-stu-id="d2409-143">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>
    
3. <span data-ttu-id="d2409-144">在 **“路由”** 页上，使用以下任意一种方式修改语音路由：</span><span class="sxs-lookup"><span data-stu-id="d2409-144">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
   - <span data-ttu-id="d2409-145">单击语音路由名称，再单击 **“编辑”**，然后单击 **“显示详细信息”**。</span><span class="sxs-lookup"><span data-stu-id="d2409-145">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="d2409-p111">单击语音路由名称，再单击 **“编辑”**、**“复制”**，然后单击 **“粘贴”**。单击刚创建的新语音路由副本，再单击 **“编辑”**，然后单击 **“显示详细信息”**。</span><span class="sxs-lookup"><span data-stu-id="d2409-p111">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>
    
4. <span data-ttu-id="d2409-148">在 **“编辑语音路由”** 页上的 **“名称”** 字段中，为语音路由键入一个描述性名称。</span><span class="sxs-lookup"><span data-stu-id="d2409-148">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>
    
5. <span data-ttu-id="d2409-149">（可选）在 **“说明”** 字段中，为语音路由键入其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="d2409-149">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>
    
6. <span data-ttu-id="d2409-150">要指定希望此路由满足的模式，可以使用 **“建立匹配的模式”** 工具生成正则表达式，或手动写入正则表达式。</span><span class="sxs-lookup"><span data-stu-id="d2409-150">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
   - <span data-ttu-id="d2409-p112">要使用 **“建立匹配的模式”** 工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：</span><span class="sxs-lookup"><span data-stu-id="d2409-p112">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
    
   - <span data-ttu-id="d2409-153">**希望允许的号码起始数字**：输入此路由必须满足的前缀值（如有必要，包括前导 +）。</span><span class="sxs-lookup"><span data-stu-id="d2409-153">**Starting digits for numbers that you want to allow**: Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="d2409-154">例如，键入 +425，然后单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="d2409-154">For example, type +425 and then click **Add**.</span></span> <span data-ttu-id="d2409-155">对希望包含在路由中的每个前缀值重复此过程。</span><span class="sxs-lookup"><span data-stu-id="d2409-155">Repeat this for each prefix value that you want to include in the route.</span></span>
    
   - <span data-ttu-id="d2409-156">**例外**：如果要为前缀值指定一个或多个例外，请突出显示相应的前缀并单击 **“例外”**。</span><span class="sxs-lookup"><span data-stu-id="d2409-156">**Exceptions**: If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="d2409-157">为不希望此路由容纳的匹配  *模式键入一*  个或多个值。</span><span class="sxs-lookup"><span data-stu-id="d2409-157">Type in one or more values for the matching patterns that you do  *not*  want this route to accommodate.</span></span> <span data-ttu-id="d2409-158">例如，若要从路由中排除以 +425237 开始的数字，请在"例外"字段中输入 +425237 的值，然后单击"**确定"。** </span><span class="sxs-lookup"><span data-stu-id="d2409-158">For example, to exclude numbers starting with +425237 from the route, enter a value of+425237 in the **Exceptions** field, and then click **OK**.</span></span>
    
   - <span data-ttu-id="d2409-159">若要手动定义匹配模式，请单击"生成模式以匹配工具"中的"编辑"，然后在 .NET Framework 正则表达式中键入以指定应用路由的目标电话号码的匹配模式。若要详细了解如何编写正则表达式，请参阅[".NET Framework 正则表达式"。](https://go.microsoft.com/fwlink/p/?linkId=140927)</span><span class="sxs-lookup"><span data-stu-id="d2409-159">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.For details about how to write regular expressions, see [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span> 
    
7. <span data-ttu-id="d2409-160">如果 **不希望** 发起出站呼叫的电话的 ID 向呼叫接收人显示，请选择"隐藏呼叫者 ID"。</span><span class="sxs-lookup"><span data-stu-id="d2409-160">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="d2409-161">如果选择此选项，则必须指定将在收件人的呼叫者 **ID** 显示器上显示的备用呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="d2409-161">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient's caller ID display.</span></span>
    
8. <span data-ttu-id="d2409-162">若要将一个或多个公用电话交换网 (PSTN) 中继与语音路由关联，请单击"添加"，然后从列表中选择中继。</span><span class="sxs-lookup"><span data-stu-id="d2409-162">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
9. <span data-ttu-id="d2409-163">若要将一个或多个 PSTN 用法与语音路由关联，请单击"选择"，然后从为部署定义的 PSTN 用法记录列表中选择企业语音记录。</span><span class="sxs-lookup"><span data-stu-id="d2409-163">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d2409-164">若要查看每个可用的 PSTN 用法记录的属性，请参阅查看 Skype for Business 中的 [PSTN 用法记录](view-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="d2409-164">To view the properties of each of the available PSTN usage records, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span> <span data-ttu-id="d2409-165">> 创建或编辑 PSTN 用法记录，请参阅在 Skype for Business 中创建或修改语音策略和配置 [PSTN 用法记录](voice-policy-and-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="d2409-165">> To create or edit PSTN usage records, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md).</span></span> 
  
10. <span data-ttu-id="d2409-166">排列 PSTN 用法记录以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="d2409-166">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="d2409-167">若要更改记录在列表中的位置，请突出显示记录名称，然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="d2409-167">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d2409-168">与 PSTN 用法记录的列出顺序很重要的语音策略相反，语音路由中的 PSTN 用法记录的顺序无关紧要。</span><span class="sxs-lookup"><span data-stu-id="d2409-168">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="d2409-169">但是，建议您按使用频率组织列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="d2409-169">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="d2409-170"> (Skype for Business Server 从上到下遍历列表。) </span><span class="sxs-lookup"><span data-stu-id="d2409-170">(Skype for Business Server traverses the list from the top down.)</span></span> 
  
11. <span data-ttu-id="d2409-p119">（可选）在 **“输入转换后的号码以进行测试”** 字段中键入一个值，然后单击 **“执行”**。测试结果将显示在该字段下面。</span><span class="sxs-lookup"><span data-stu-id="d2409-p119">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
12. <span data-ttu-id="d2409-173">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d2409-173">Click **OK**.</span></span>
    
13. <span data-ttu-id="d2409-174">在 **“路由”** 页上，单击 **“提交”**，然后单击 **“全部提交”**。</span><span class="sxs-lookup"><span data-stu-id="d2409-174">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d2409-175">任何时候创建或修改语音路由，都必须运行 **"** 全部提交"命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="d2409-175">Whenever you create or modify a voice route, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="d2409-176">有关详细信息，请参阅操作文档中的"在 [Skype for Business 中](voice-route-config-changes.md) 发布对语音路由配置的挂起更改"。</span><span class="sxs-lookup"><span data-stu-id="d2409-176">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d2409-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2409-177">See also</span></span>

[<span data-ttu-id="d2409-178">在 Skype for Business 中查看 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="d2409-178">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
  
[<span data-ttu-id="d2409-179">在 Skype for Business 中创建或修改语音策略和配置 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="d2409-179">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
  
[<span data-ttu-id="d2409-180">在 Skype for Business 中发布对语音路由配置的挂起更改</span><span class="sxs-lookup"><span data-stu-id="d2409-180">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

