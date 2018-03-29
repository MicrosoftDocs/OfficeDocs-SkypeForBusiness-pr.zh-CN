---
title: 在 Skype for Business Server 2015 中创建或修改未分配号码范围
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 创建、 修改或删除为 Skype 业务服务器企业语音的发布应用程序未指定数字的范围。 这将影响如何处理打给未分配号码的呼叫。
ms.openlocfilehash: e4a62072eeffd1cfe8d1cb81fceeb4e52cc68199
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server-2015"></a><span data-ttu-id="f8ae0-104">在 Skype for Business Server 2015 中创建或修改未分配号码范围</span><span class="sxs-lookup"><span data-stu-id="f8ae0-104">Create or modify an unassigned number range in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f8ae0-105">创建、 修改或删除为 Skype 业务服务器企业语音的发布应用程序未指定数字的范围。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="f8ae0-106">这将影响如何处理打给未分配号码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="f8ae0-107">Skype 业务服务器可以说为适用于您的组织，但未指派给一个用户或一部电话的电话号码的来电会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="f8ae0-108">为了处理此类呼叫，请设置未分配号码表。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="f8ae0-109">该表用于将呼叫路由到发布应用程序或 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="f8ae0-p104">配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码修改所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码，然后将其分配给提供新号码的通知。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="f8ae0-116">配置未分配电话号码</span><span class="sxs-lookup"><span data-stu-id="f8ae0-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="f8ae0-117">使用以下过程之一来配置发布应用程序未指定数字的范围。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f8ae0-118">您的系统配置未指定编号的表之前，必须已经定义的通知有两种： 或者 Exchange 统一消息 (UM) 自动助理设置。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="f8ae0-119">当有人呼叫未分配的号码时，Skype 业务服务器的搜索从上到下的未分配数字表，并使用第一个匹配的范围。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="f8ae0-120">因此，要在万不得已时执行的操作应指定给表中最后一个范围。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="f8ae0-121">若要使用 Skype 业务服务器控制面板配置未指定的电话号码</span><span class="sxs-lookup"><span data-stu-id="f8ae0-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="f8ae0-122">作为 RTCUniversalServerAdmins 组的成员身份或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员登录到该计算机。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f8ae0-123">有关详细信息，请参阅**代理安装程序权限**。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-123">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="f8ae0-124">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f8ae0-125">在左侧导航栏中，单击“语音功能”****，然后单击“未分配号码”****。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="f8ae0-126">在“未分配号码”****页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f8ae0-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="f8ae0-p107">若要创建新的号码范围，请单击“新建”****。在“名称”****中，键入此号码范围的标识名称。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-p107">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f8ae0-129">新的未分配号码范围提交到数据库后，将无法更改该名称。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="f8ae0-p108">若要修改现有号码范围，请在搜索字段中键入号码范围的全部或部分名称。在号码范围的结果列表中，单击所需的名称，再单击“编辑”****，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-p108">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f8ae0-132">在第一个“号码范围”****字段中，键入号码范围的起始号码，在第二个“号码范围”****字段中，键入该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="f8ae0-133">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="f8ae0-134">如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="f8ae0-135">数量必须匹配的正则表达式 (tel:) ? (\+) ? [1-9] \d {0,17} (; ext = [1-9] \d {0,9}) ?。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="f8ae0-136">这意味着数可能开始与字符串 tel: （如果不指定该字符串，它将会自动为您添加），加号 （+） 和数字 1 到 9。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="f8ae0-137">电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="f8ae0-138">在“通知服务”****中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f8ae0-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="f8ae0-139">单击“通知”****。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="f8ae0-140">单击“Exchange UM”****。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="f8ae0-141">如果在上一步中单击了“通知”****，则执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f8ae0-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="f8ae0-142">a.</span><span class="sxs-lookup"><span data-stu-id="f8ae0-142">a.</span></span> <span data-ttu-id="f8ae0-143">在**目标服务器的 FQDN**，单击**选择**下，单击运行发布应用程序将处理传入呼叫到未分配的编号，该范围，然后单击**确定**应用程序服务的服务 ID。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="f8ae0-144">b.</span><span class="sxs-lookup"><span data-stu-id="f8ae0-144">b.</span></span> <span data-ttu-id="f8ae0-145">在“通知”****中，单击要为此未分配号码范围播放的通知。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="f8ae0-146">如果在上一步中单击了“Exchange UM”****，则在“自动助理电话号码”****下，单击“选择”****，再单击将用于此未分配号码范围的电话号码，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="f8ae0-147">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="f8ae0-p112">在“未分配号码”****页上，确保未分配号码范围按照所需顺序排列。要更改号码范围在表中的位置，请在范围列表中单击一个或多个连续名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-p112">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="f8ae0-150">Skype 业务服务器从顶部到底部未分配数字表中搜索，并使用未赋值的号相匹配的第一个范围。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="f8ae0-151">如果有重叠的范围并且有一个范围指定了最后的操作，请确保将该范围置于列表底部。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="f8ae0-152">按照希望的顺序排列未分配号码范围后，单击“全部提交”****。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="f8ae0-153">若要使用 Skype 业务服务器管理外壳的配置未指定的电话号码</span><span class="sxs-lookup"><span data-stu-id="f8ae0-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="f8ae0-154">登录到业务服务器管理外壳的 Skype 为成员的 RTCUniversalServerAdmins 组或**委托安装程序权限**中所述的必要的用户权限的安装位置的计算机上。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="f8ae0-155">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f8ae0-156">使用**New CsUnassignedNumber**创建一个新的未分配编号范围。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="f8ae0-157">使用**一组 CsUnassignedNumber**修改现有未分配编号范围。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="f8ae0-p115">如果您具有重叠的范围并希望按某个特定顺序应用这些范围，请包含 Priority 参数。优先级最高的范围将应用于呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-p115">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter. The range with the highest priority will be applied to the call.</span></span> 
  
    <span data-ttu-id="f8ae0-160">在命令行中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f8ae0-160">At the command line, do one of the following:</span></span>
    
     - <span data-ttu-id="f8ae0-161">若要创建公告服务的号码范围，请运行：</span><span class="sxs-lookup"><span data-stu-id="f8ae0-161">To create a number range for an Announcement service, run:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="f8ae0-162">或者，若要创建 Exchange UM 自动助理的号码范围，请运行：</span><span class="sxs-lookup"><span data-stu-id="f8ae0-162">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="f8ae0-163">例如：</span><span class="sxs-lookup"><span data-stu-id="f8ae0-163">For example:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="f8ae0-164">或</span><span class="sxs-lookup"><span data-stu-id="f8ae0-164">Or</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

    <span data-ttu-id="f8ae0-165">以下示例介绍如何修改现有未分配号码范围中的号码：</span><span class="sxs-lookup"><span data-stu-id="f8ae0-165">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="f8ae0-166">删除未分配号码范围</span><span class="sxs-lookup"><span data-stu-id="f8ae0-166">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="f8ae0-167">若要使用 Skype 业务服务器控件面板中删除未分配的编号范围</span><span class="sxs-lookup"><span data-stu-id="f8ae0-167">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="f8ae0-168">作为 RTCUniversalServerAdmins 组的成员身份或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员登录到该计算机。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-168">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f8ae0-169">有关详细信息，请参阅**代理安装程序权限**。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-169">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="f8ae0-170">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f8ae0-171">在左侧导航栏中，单击“语音功能”****，然后单击“未分配号码”****。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-171">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="f8ae0-172">在“未分配号码”****页上的搜索字段中，键入要删除的未分配号码范围的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-172">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="f8ae0-173">在号码范围的结果列表中，单击名称，再单击“编辑”****，然后单击“删除”****。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-173">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="f8ae0-174">单击“全部提交”****。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-174">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="f8ae0-175">若要使用 Skype 的业务服务器管理外壳程序若要删除未分配的编号范围</span><span class="sxs-lookup"><span data-stu-id="f8ae0-175">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="f8ae0-176">登录到业务服务器管理外壳的 Skype 为成员的 RTCUniversalServerAdmins 组或**委托安装程序权限**中所述的必要的用户权限的安装位置的计算机上。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-176">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="f8ae0-177">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-177">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f8ae0-178">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="f8ae0-178">At the command line, type:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="f8ae0-179">例如：</span><span class="sxs-lookup"><span data-stu-id="f8ae0-179">For example:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="f8ae0-180">有关更多选项的详细信息，请参阅[删除 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f8ae0-180">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f8ae0-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8ae0-181">See also</span></span>

#### 

[<span data-ttu-id="f8ae0-182">新 CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="f8ae0-182">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="f8ae0-183">一组 CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="f8ae0-183">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="f8ae0-184">获得 CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="f8ae0-184">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)

