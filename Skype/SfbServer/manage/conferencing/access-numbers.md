---
title: '在 Skype for Business Server 中管理电话拨入式会议访问号码 '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 摘要：了解如何在 Skype for Business Server 中管理电话拨入式会议访问号码。
ms.openlocfilehash: 868d757edc6728254c1ab09d22398cd3dc60901b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806482"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="ff4c7-103">在 Skype for Business Server 中管理电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="ff4c7-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="ff4c7-104">**摘要：** 了解如何在 Skype for Business Server 中管理电话拨入式会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="ff4c7-105">部署电话拨入式会议时，需要设置用户可以从公用电话交换网 (PSTN) 拨打的电话号码，以加入会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="ff4c7-106">这些拨入访问号码显示在会议邀请和电话拨入式会议设置网页中。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="ff4c7-107">本主题介绍如何查看、修改或删除现有电话拨入式会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="ff4c7-108">若要详细了解如何创建初始拨入访问号码，请参阅在 Skype [for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md)中配置电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="ff4c7-109">查看电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="ff4c7-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="ff4c7-110">可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序查看电话拨入式会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ff4c7-111">使用 Skype for Business Server 控制面板查看拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="ff4c7-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ff4c7-112">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="ff4c7-113">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ff4c7-114">在左侧导航栏中，单击“会议”，然后单击“拨入访问号码”。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="ff4c7-115">在“拨入访问号码”页上，单击要查看的访问号码。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="ff4c7-116">在 **"** 编辑"中 **，选中"显示详细信息** "复选框。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ff4c7-117">使用 Skype for Business Server 命令行管理程序查看拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="ff4c7-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ff4c7-118">若要查看有关拨入访问号码的信息，请使用 **Get-CsDialInConferencingAccessNumber** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="ff4c7-119">以下命令返回配置为在组织使用的所有电话拨入式会议访问号码的集合：</span><span class="sxs-lookup"><span data-stu-id="ff4c7-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="ff4c7-120">以下是返回的信息类型的示例：</span><span class="sxs-lookup"><span data-stu-id="ff4c7-120">The following is an example of the type of information returned:</span></span>
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

<span data-ttu-id="ff4c7-121">有关详细信息，请参阅[Get-CsDialInConferencingAccessNumber。](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ff4c7-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="ff4c7-122">修改电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="ff4c7-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="ff4c7-123">可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序修改拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ff4c7-124">使用 Skype for Business Server 控制面板修改拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="ff4c7-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ff4c7-125">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="ff4c7-126">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ff4c7-127">在左侧导航栏中，单击“会议”，然后单击“拨入访问号码”。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="ff4c7-128">在"**拨入访问号码**"页上，单击列表中的某个拨入访问号码，再单击"编辑"，然后单击"**显示详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff4c7-129">使用搜索字段搜索拨入访问号码列表中的列的内容可能不会获得预期的结果。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-129">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="ff4c7-130">相反，按感兴趣的列对列表进行排序，以标识要查看或更改的拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-130">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="ff4c7-131">在 **"显示** 号码"中，键入公用电话交换网 (PSTN) 电话用户拨打以加入会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="ff4c7-132">此号码显示在会议邀请和电话拨入式会议设置网页中。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="ff4c7-133">在 **"显示** 名称"中，键入拨入访问号码的说明。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="ff4c7-134">这是与 Skype for Business 搜索结果中的拨入访问号码相关联的名称。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="ff4c7-135">当用户呼叫访问号码时，此名称将显示在客户端中。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="ff4c7-136">在 **线路 URI** 中，键入 TEL URI 格式的拨入访问号码的 E.164 号码，包括号码前的 + 符号和不包括空格。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-136">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="ff4c7-137">例如，tel：+14255550200。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-137">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff4c7-138">同一线路 URI 不能由另一个电话拨入式会议访问号码重复使用。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="ff4c7-139">在 **SIP URI** 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ff4c7-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="ff4c7-140">在文本框中，为此电话拨入式会议访问号码键入唯一的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="ff4c7-141">此 SIP URI 显示在各种位置，包括但不限于呼叫通知消息和以前版本的 Lync 客户端。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff4c7-142">同一 SIP URI 不能由另一个电话拨入式会议访问号码重复使用。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-142">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="ff4c7-143">创建访问号码后，不能修改 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-143">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="ff4c7-144">更改 SIP URI 的唯一方法就是删除并重新创建访问号码。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-144">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="ff4c7-145">在下拉列表框中，单击支持此拨入访问号码的会议助理应用程序的域。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="ff4c7-146">在 **池中**，单击运行支持此拨入访问号码的会议助理实例的池。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff4c7-147">如果在创建访问号码后需要更改池，则必须使用 **Move-CsApplicationEndpoint** cmdlet 或删除并重新创建访问号码。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="ff4c7-148">在 **主要语言** 中，单击为此拨入访问号码播放提示的语言。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="ff4c7-149">主要语言是会议助理用于应答呼叫的语言。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-149">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="ff4c7-150">支持的语言与"电话拨入式会议设置"网页上的每个访问电话号码一起显示。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-150">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="ff4c7-151"> (可选) 在辅助语言 **中 (最多四个) ，** 单击"添加"，选择要为此拨入访问号码的呼叫者支持的一种或多种语言，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="ff4c7-152">您可以为每个拨入访问号码选择最多四种辅助语言。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-152">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="ff4c7-153">用户在拨入会议时，可以在输入会议 ID 之前选择辅助语言。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-153">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="ff4c7-154">若要为拨入访问号码添加区域，请在"关联区域"下，单击"添加"，单击与此拨入访问号码的拨号计划关联的一个或多个区域，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="ff4c7-155">若要从拨入访问号码中删除某个区域，请在"关联区域"下，单击要删除的区域，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="ff4c7-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="ff4c7-156">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ff4c7-157">使用 Skype for Business Server 命令行管理程序修改拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="ff4c7-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ff4c7-158">若要修改拨入访问号码，请使用 **Set-CsDialInConferencingAccessNumber** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="ff4c7-159">以下命令修改 Identity 为 sip:RedmondDialIn@litwareinc.com 的电话拨入式会议访问号码的 DisplayName sip:RedmondDialIn@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-159">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com.</span></span> <span data-ttu-id="ff4c7-160">本示例中，显示名称设置为"Redmond Dial-In Access Number"：</span><span class="sxs-lookup"><span data-stu-id="ff4c7-160">In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="ff4c7-161">下一个示例将 Identity 为 sip:RedmondDialIn@litwareinc.com 电话拨入式会议访问号码修改为包括两个区域：Redmond 和 Seattle。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-161">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle.</span></span> <span data-ttu-id="ff4c7-162">为执行此操作，命令调用了 Regions 参数，后跟这两个地区（以逗号分隔的两个字符串值）。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-162">To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas).</span></span> <span data-ttu-id="ff4c7-163">注意，除非已在拨号计划中定义了 Redmond 和 Seattle 这两个地区，否则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-163">Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="ff4c7-164">有关详细信息，请参阅[Set-CsDialInConferencingAccessNumber。](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ff4c7-164">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="ff4c7-165">删除电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="ff4c7-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="ff4c7-166">可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序删除电话拨入式会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ff4c7-167">使用 Skype for Business Server 控制面板删除电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="ff4c7-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="ff4c7-168">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="ff4c7-169">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ff4c7-170">在左侧导航栏中，单击“会议”，然后单击“拨入访问号码”。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="ff4c7-171">在页面上，单击列表中要删除的电话拨入式号码，再单击“编辑”，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="ff4c7-172">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ff4c7-173">使用 Skype for Business Server 命令行管理程序删除电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="ff4c7-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ff4c7-174">若要删除电话拨入式会议访问号码，请使用 **Remove-CsDialInConferencingAccessNumber**。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="ff4c7-175">以下命令删除 Identity 为 sip:RedmondDialInAccess@litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="ff4c7-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="ff4c7-176">下一个命令删除与 Northwest 区域关联的所有电话拨入式会议访问号码：</span><span class="sxs-lookup"><span data-stu-id="ff4c7-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="ff4c7-177">下一个命令删除意大利语是主要语言的所有电话拨入式会议访问号码：</span><span class="sxs-lookup"><span data-stu-id="ff4c7-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="ff4c7-178">有关详细信息，请参阅 [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ff4c7-178">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

