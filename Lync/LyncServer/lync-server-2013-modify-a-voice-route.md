---
title: Lync Server 2013：修改语音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0731383eea99e7510ef1748777e7139e2d9f369
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="33165-102">在 Lync Server 2013 中修改语音路由</span><span class="sxs-lookup"><span data-stu-id="33165-102">Modify a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33165-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="33165-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="33165-104">本主题介绍如何编辑语音路线。</span><span class="sxs-lookup"><span data-stu-id="33165-104">This topic explains how to edit a voice route.</span></span> <span data-ttu-id="33165-105">若要创建新的路由，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="33165-105">To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>

<div>

## <a name="to-modify-a-voice-route"></a><span data-ttu-id="33165-106">修改语音路由</span><span class="sxs-lookup"><span data-stu-id="33165-106">To modify a voice route</span></span>

1.  <span data-ttu-id="33165-107">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="33165-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="33165-108">有关详细信息，请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="33165-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="33165-109">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="33165-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="33165-110">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="33165-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="33165-111">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="33165-111">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>

4.  <span data-ttu-id="33165-112">在“路由”\*\*\*\* 页上，使用以下任意一种方式修改语音路由：</span><span class="sxs-lookup"><span data-stu-id="33165-112">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
      - <span data-ttu-id="33165-113">单击语音路由名称，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="33165-113">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="33165-p104">单击语音路由名称，再单击“编辑”\*\*\*\*、“复制”\*\*\*\*，然后单击“粘贴”\*\*\*\*。单击刚创建的新语音路由副本，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="33165-p104">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="33165-116">在“编辑语音路由”\*\*\*\* 页上的“名称”\*\*\*\* 字段中，为语音路由键入一个描述性名称。</span><span class="sxs-lookup"><span data-stu-id="33165-116">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>

6.  <span data-ttu-id="33165-117">（可选）在“说明”\*\*\*\* 字段中，为语音路由键入其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="33165-117">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>

7.  <span data-ttu-id="33165-118">要指定希望此路由满足的模式，可以使用“建立匹配的模式”\*\*\*\* 工具生成正则表达式，或手动写入正则表达式。</span><span class="sxs-lookup"><span data-stu-id="33165-118">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="33165-p105">要使用“建立匹配的模式”\*\*\*\* 工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：</span><span class="sxs-lookup"><span data-stu-id="33165-p105">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="33165-121">**要允许的数字的起始位数：** 输入此路线必须容纳的前缀值（包括前导 + （如果需要）。</span><span class="sxs-lookup"><span data-stu-id="33165-121">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="33165-122">例如，键入 **+425**，然后单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="33165-122">For example, type **+425** and then click **Add**.</span></span> <span data-ttu-id="33165-123">对希望包含在路由中的每个前缀值重复此过程。</span><span class="sxs-lookup"><span data-stu-id="33165-123">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="33165-124">**例外：** 如果要为前缀值指定一个或多个例外，请突出显示前缀，然后单击 "**例外**"。</span><span class="sxs-lookup"><span data-stu-id="33165-124">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="33165-125">为 *不*希望此路由满足的匹配模式键入一个或多个值。</span><span class="sxs-lookup"><span data-stu-id="33165-125">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="33165-126">例如，要从路由中排除以 +425237 开头的号码，请在“例外”\*\*\*\* 字段中输入值 **+425237**，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="33165-126">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="33165-127">若要手动定义匹配模式，请在“构建要匹配的模式”\*\*\*\* 工具中单击“编辑” \*\*\*\*，然后键入 .NET Framework 正则表达式，以便为应用路由的目标电话号码指定匹配模式。</span><span class="sxs-lookup"><span data-stu-id="33165-127">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="33165-128">有关如何编写正则表达式的信息，请参阅的[http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)".Net Framework 正则表达式"。</span><span class="sxs-lookup"><span data-stu-id="33165-128">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

8.  <span data-ttu-id="33165-p109">如果不希望对呼叫接收人显示发起出站呼叫的电话的 ID，请选择“隐藏呼叫者 ID”\*\*\*\*。如果选择此选项，必须指定显示在接收人的呼叫者 ID 显示器上的“备用呼叫者 ID”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="33165-p109">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

9.  <span data-ttu-id="33165-131">要将一个或多个公用电话交换网 (PSTN) 中继与语音路由相关联，请单击“添加”\*\*\*\*，然后从列表中选择中继。</span><span class="sxs-lookup"><span data-stu-id="33165-131">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33165-132">如果你的部署包含任何 Microsoft Office 通信服务器 2007 R2 中介服务器，则这些服务器也将在列表中可用。</span><span class="sxs-lookup"><span data-stu-id="33165-132">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

10. <span data-ttu-id="33165-133">若要将一个或多个 PSTN 用途与语音路由相关联，请单击 "**选择**"，然后从已为您的企业语音部署定义的 PSTN 使用记录列表中选择一条记录。</span><span class="sxs-lookup"><span data-stu-id="33165-133">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33165-134">若要查看每个可用 PSTN 使用记录的属性，请参阅<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 PSTN 使用情况记录</A>。</span><span class="sxs-lookup"><span data-stu-id="33165-134">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="33165-135">若要创建或编辑 PSTN 使用记录，请参阅<A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">在 Lync server 2013 中创建语音策略和配置 pstn 使用记录</A>或<A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">在 lync Server 2013 中修改语音策略和配置 pstn 使用记录</A>。</span><span class="sxs-lookup"><span data-stu-id="33165-135">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="33165-p110">排列 PSTN 用法记录以获得最佳性能。要更改记录在列表中的位置，请突出显示相应的记录名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="33165-p110">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33165-138">与列出 PSTN 使用记录的顺序非常重要的语音策略相反，在语音路由中，PSTN 使用记录的顺序是多余的。</span><span class="sxs-lookup"><span data-stu-id="33165-138">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="33165-139">但是，我们建议你按使用频率组织列表，例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="33165-139">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="33165-140">（Lync Server 从上到下遍历列表。）</span><span class="sxs-lookup"><span data-stu-id="33165-140">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

12. <span data-ttu-id="33165-p112">（可选）在“输入转换后的号码以进行测试”\*\*\*\* 字段中键入一个值，然后单击“执行”\*\*\*\*。测试结果将显示在该字段下面。</span><span class="sxs-lookup"><span data-stu-id="33165-p112">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33165-143">你可以保存尚未通过测试的语音路由，然后稍后重新配置它。</span><span class="sxs-lookup"><span data-stu-id="33165-143">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="33165-144">有关详细信息，请参阅<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="33165-144">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="33165-145">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="33165-145">Click **OK**.</span></span>

14. <span data-ttu-id="33165-146">在“路由”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="33165-146">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33165-147">每当创建或修改语音路由时，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="33165-147">Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="33165-148">有关详细信息，请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。</span><span class="sxs-lookup"><span data-stu-id="33165-148">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33165-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33165-149">See Also</span></span>


[<span data-ttu-id="33165-150">在 Lync Server 2013 中创建语音路由</span><span class="sxs-lookup"><span data-stu-id="33165-150">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="33165-151">在 Lync Server 2013 中查看 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="33165-151">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="33165-152">在 Lync Server 2013 中创建语音策略和配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="33165-152">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="33165-153">在 Lync Server 2013 中修改语音策略和配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="33165-153">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="33165-154">将挂起的更改发布到 Lync Server 2013 中的语音路由配置</span><span class="sxs-lookup"><span data-stu-id="33165-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="33165-155">在 Lync Server 2013 中测试语音路由</span><span class="sxs-lookup"><span data-stu-id="33165-155">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

