---
title: 在 Skype for Business 服务器中创建或修改未分配的号码范围
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 在 Skype for business Server 企业版中创建、修改或删除用于公告应用的未分配号码范围。 这将影响如何处理打给未分配号码的呼叫。
ms.openlocfilehash: d357a97bffda50d6d387ba40a12f62dacac5ce31
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767745"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="18f71-104">在 Skype for Business 服务器中创建或修改未分配的号码范围</span><span class="sxs-lookup"><span data-stu-id="18f71-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="18f71-105">在 Skype for business Server 企业版中创建、修改或删除用于公告应用的未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="18f71-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="18f71-106">这将影响如何处理打给未分配号码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="18f71-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="18f71-107">Skype for Business 服务器使您能够说拨入的电话号码对您的组织有效，但未分配给用户或电话。</span><span class="sxs-lookup"><span data-stu-id="18f71-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="18f71-108">为了处理此类呼叫，请设置未分配号码表。</span><span class="sxs-lookup"><span data-stu-id="18f71-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="18f71-109">可以使用表将呼叫路由到公告应用程序或 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="18f71-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="18f71-p104">配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码修改所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码，然后将其分配给提供新号码的通知。</span><span class="sxs-lookup"><span data-stu-id="18f71-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="18f71-116">配置未分配电话号码</span><span class="sxs-lookup"><span data-stu-id="18f71-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="18f71-117">使用以下过程之一为公告应用程序配置未分配的号码范围。</span><span class="sxs-lookup"><span data-stu-id="18f71-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="18f71-118">配置 "未分配的号码" 表之前，您的系统必须已定义公告或 "Exchange 统一消息（UM）" 自动助理设置。</span><span class="sxs-lookup"><span data-stu-id="18f71-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="18f71-119">当某人呼叫未分配的号码时，Skype for Business 服务器将从上到下搜索 "未分配的号码" 表，并使用第一个匹配区域。</span><span class="sxs-lookup"><span data-stu-id="18f71-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="18f71-120">因此，要在万不得已时执行的操作应指定给表中最后一个范围。</span><span class="sxs-lookup"><span data-stu-id="18f71-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="18f71-121">使用 "Skype for Business 服务器" 控制面板配置未分配的电话号码</span><span class="sxs-lookup"><span data-stu-id="18f71-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="18f71-p106">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅**Delegate Setup Permissions**。</span><span class="sxs-lookup"><span data-stu-id="18f71-p106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="18f71-124">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="18f71-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="18f71-125">在左侧导航栏中，单击“语音功能”\*\*\*\*，然后单击“未分配号码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18f71-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="18f71-126">在“未分配号码”\*\*\*\* 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="18f71-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="18f71-p107">若要创建新的号码范围，请单击“新建”\*\*\*\*。在“名称”\*\*\*\* 中，键入此号码范围的标识名称。</span><span class="sxs-lookup"><span data-stu-id="18f71-p107">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="18f71-129">新的未分配号码范围提交到数据库后，将无法更改该名称。</span><span class="sxs-lookup"><span data-stu-id="18f71-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="18f71-p108">若要修改现有号码范围，请在搜索字段中键入号码范围的全部或部分名称。在号码范围的结果列表中，单击所需的名称，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18f71-p108">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="18f71-132">在第一个“号码范围”\*\*\*\* 字段中，键入号码范围的起始号码，在第二个“号码范围”\*\*\*\* 字段中，键入该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="18f71-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="18f71-133">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="18f71-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="18f71-134">如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。</span><span class="sxs-lookup"><span data-stu-id="18f71-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="18f71-135">该号码必须与正则表达式（电话：）匹配？（\+)?[1-9] \d{0,17}（; ext = [1-9] \d{0,9}）？。</span><span class="sxs-lookup"><span data-stu-id="18f71-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="18f71-136">这意味着该号码可能会以字符串电话开始：（如果不指定该字符串，将自动为您添加该字符串）、加号（+）和数字1到9。</span><span class="sxs-lookup"><span data-stu-id="18f71-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="18f71-137">电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。</span><span class="sxs-lookup"><span data-stu-id="18f71-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="18f71-138">在“通知服务”\*\*\*\* 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="18f71-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="18f71-139">单击“通知”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18f71-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="18f71-140">单击“Exchange UM”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18f71-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="18f71-141">如果在上一步中单击了“通知”\*\*\*\*，则执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="18f71-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="18f71-142">a.</span><span class="sxs-lookup"><span data-stu-id="18f71-142">a.</span></span> <span data-ttu-id="18f71-143">在 "**目标服务器的 FQDN**" 下，单击 "**选择**"，单击运行通知应用程序的应用程序服务的服务 ID，该应用程序将处理传入呼叫到此范围的未分配号码，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="18f71-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="18f71-144">b.</span><span class="sxs-lookup"><span data-stu-id="18f71-144">b.</span></span> <span data-ttu-id="18f71-145">在“通知”\*\*\*\* 中，单击要为此未分配号码范围播放的通知。</span><span class="sxs-lookup"><span data-stu-id="18f71-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="18f71-146">如果在上一步中单击了“Exchange UM”\*\*\*\*，则在“自动助理电话号码”\*\*\*\* 下，单击“选择”\*\*\*\*，再单击将用于此未分配号码范围的电话号码，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18f71-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="18f71-147">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="18f71-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="18f71-p112">在“未分配号码”\*\*\*\* 页上，确保未分配号码范围按照所需顺序排列。要更改号码范围在表中的位置，请在范围列表中单击一个或多个连续名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="18f71-p112">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="18f71-150">Skype for Business 服务器从上到下搜索 "未分配的号码" 表，并使用与未分配号码匹配的第一个区域。</span><span class="sxs-lookup"><span data-stu-id="18f71-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="18f71-151">如果有重叠的范围并且有一个范围指定了最后的操作，请确保将该范围置于列表底部。</span><span class="sxs-lookup"><span data-stu-id="18f71-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="18f71-152">按照希望的顺序排列未分配号码范围后，单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18f71-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="18f71-153">使用 Skype for Business Server Management Shell 配置未分配的电话号码</span><span class="sxs-lookup"><span data-stu-id="18f71-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="18f71-154">登录到将 Skype for Business Server Management Shell 作为 RTCUniversalServerAdmins 组的成员或必要的用户权限（如 "**委派设置权限**" 中所述）进行安装的计算机。</span><span class="sxs-lookup"><span data-stu-id="18f71-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="18f71-155">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18f71-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="18f71-156">使用 **New-CsUnassignedNumber** 可创建新的未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="18f71-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="18f71-157">使用 **Set-CsUnassignedNumber** 可修改现有未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="18f71-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="18f71-158">如果您具有重叠的范围并希望按某个特定顺序应用这些范围，请包含 Priority 参数。</span><span class="sxs-lookup"><span data-stu-id="18f71-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="18f71-159">优先级最高的范围将应用于呼叫。</span><span class="sxs-lookup"><span data-stu-id="18f71-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="18f71-160">值0表示最高优先级。</span><span class="sxs-lookup"><span data-stu-id="18f71-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="18f71-161">在命令行中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="18f71-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="18f71-162">若要创建公告服务的号码范围，请运行：</span><span class="sxs-lookup"><span data-stu-id="18f71-162">To create a number range for an Announcement service, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="18f71-163">或者，若要创建 Exchange UM 自动助理的号码范围，请运行：</span><span class="sxs-lookup"><span data-stu-id="18f71-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="18f71-164">例如：</span><span class="sxs-lookup"><span data-stu-id="18f71-164">For example:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="18f71-165">或</span><span class="sxs-lookup"><span data-stu-id="18f71-165">Or</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="18f71-166">以下示例介绍如何修改现有未分配号码范围中的号码：</span><span class="sxs-lookup"><span data-stu-id="18f71-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="18f71-167">删除未分配号码范围</span><span class="sxs-lookup"><span data-stu-id="18f71-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="18f71-168">使用 Skype for Business 服务器 "控制面板" 删除未分配的号码范围</span><span class="sxs-lookup"><span data-stu-id="18f71-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="18f71-p116">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅**Delegate Setup Permissions**。</span><span class="sxs-lookup"><span data-stu-id="18f71-p116">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="18f71-171">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="18f71-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="18f71-172">在左侧导航栏中，单击“语音功能”\*\*\*\*，然后单击“未分配号码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18f71-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="18f71-173">在“未分配号码”\*\*\*\* 页上的搜索字段中，键入要删除的未分配号码范围的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="18f71-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="18f71-174">在号码范围的结果列表中，单击名称，再单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18f71-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="18f71-175">单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18f71-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="18f71-176">使用 Skype for Business Server 命令行管理程序删除未分配的号码范围</span><span class="sxs-lookup"><span data-stu-id="18f71-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="18f71-177">登录到将 Skype for Business Server Management Shell 作为 RTCUniversalServerAdmins 组的成员或必要的用户权限（如 "**委派设置权限**" 中所述）进行安装的计算机。</span><span class="sxs-lookup"><span data-stu-id="18f71-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="18f71-178">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18f71-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="18f71-179">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="18f71-179">At the command line, type:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="18f71-180">例如：</span><span class="sxs-lookup"><span data-stu-id="18f71-180">For example:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="18f71-181">有关更多选项的详细信息，请参阅[Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="18f71-181">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="18f71-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18f71-182">See also</span></span>

[<span data-ttu-id="18f71-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="18f71-183">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="18f71-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="18f71-184">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="18f71-185">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="18f71-185">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
