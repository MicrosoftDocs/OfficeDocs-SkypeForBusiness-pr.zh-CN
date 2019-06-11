---
title: 'Lync Server 2013: 创建语音路由'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe4c6a9492cbbecafff95a1f6e626087e79f62d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="9d72c-102">在 Lync Server 2013 中创建语音路由</span><span class="sxs-lookup"><span data-stu-id="9d72c-102">Create a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d72c-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9d72c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9d72c-104">以下过程介绍了如何使用 Lync Server 2013 控制面板创建新的语音路由。</span><span class="sxs-lookup"><span data-stu-id="9d72c-104">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="9d72c-105">若要编辑现有路线, 请参阅[在 Lync Server 2013 中为过程修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="9d72c-105">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="9d72c-106">使用 Lync Server "控制面板" 创建语音路由</span><span class="sxs-lookup"><span data-stu-id="9d72c-106">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9d72c-107">以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="9d72c-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="9d72c-108">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="9d72c-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9d72c-109">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="9d72c-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9d72c-110">在左侧导航栏中，单击“语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9d72c-110">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="9d72c-111">单击“路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9d72c-111">Click **Route**.</span></span>

5.  <span data-ttu-id="9d72c-112">单击“新建”\*\*\*\* 以显示“新建语音路由”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="9d72c-112">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="9d72c-113">在“名称”\*\*\*\* 中，键入语音路由的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="9d72c-113">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="9d72c-114">（可选）在“说明”\*\*\*\* 中，为语音路由键入其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="9d72c-114">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="9d72c-115">要指定希望此路由满足的模式，可以使用“建立匹配的模式”\*\*\*\* 工具生成正则表达式，或手动写入正则表达式。</span><span class="sxs-lookup"><span data-stu-id="9d72c-115">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="9d72c-p103">要使用“建立匹配的模式”\*\*\*\* 工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：</span><span class="sxs-lookup"><span data-stu-id="9d72c-p103">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="9d72c-118">**要允许的数字的起始位数:** 输入此路线必须容纳的前缀值 (包括前导 + (如果需要)。</span><span class="sxs-lookup"><span data-stu-id="9d72c-118">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="9d72c-119">例如，键入 **+425**，然后单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9d72c-119">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="9d72c-120">对希望包含在路由中的每个前缀值重复此过程。</span><span class="sxs-lookup"><span data-stu-id="9d72c-120">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="9d72c-121">**例外:** 如果要为前缀值指定一个或多个例外, 请突出显示前缀, 然后单击 "**例外**"。</span><span class="sxs-lookup"><span data-stu-id="9d72c-121">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="9d72c-122">为 *不*希望此路由满足的匹配模式键入一个或多个值。</span><span class="sxs-lookup"><span data-stu-id="9d72c-122">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="9d72c-123">例如，要从路由中排除以 +425237 开头的号码，请在“例外”\*\*\*\* 字段中输入值 **+425237**，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9d72c-123">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="9d72c-124">若要手动定义匹配模式，请在“构建要匹配的模式”\*\*\*\* 工具中单击“编辑” \*\*\*\*，然后键入 .NET Framework 正则表达式，以便为应用路由的目标电话号码指定匹配模式。</span><span class="sxs-lookup"><span data-stu-id="9d72c-124">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="9d72c-125">有关如何编写正则表达式的详细信息, 请参阅的[http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)".Net Framework 正则表达式"。</span><span class="sxs-lookup"><span data-stu-id="9d72c-125">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="9d72c-p107">如果不希望对呼叫接收人显示发起出站呼叫的电话的 ID，请选择“隐藏呼叫者 ID”\*\*\*\*。如果选择此选项，必须指定显示在接收人的呼叫者 ID 显示器上的“备用呼叫者 ID”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9d72c-p107">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="9d72c-128">要将一个或多个中继与语音路由相关联，请单击“添加”\*\*\*\*，然后从列表中选择中继。</span><span class="sxs-lookup"><span data-stu-id="9d72c-128">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9d72c-129">如果你的部署包含任何 Microsoft Office 通信服务器 2007 R2 中介服务器, 则这些服务器也将在列表中可用。</span><span class="sxs-lookup"><span data-stu-id="9d72c-129">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="9d72c-130">若要将一个或多个公共交换电话网络 (PSTN) 用途与语音路由相关联, 请单击 "**选择**", 然后从已为你的企业语音部署定义的 PSTN 使用记录列表中选择一条记录。</span><span class="sxs-lookup"><span data-stu-id="9d72c-130">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9d72c-131">若要查看每个可用 PSTN 使用记录的属性, 请参阅<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 PSTN 使用情况记录</A>。</span><span class="sxs-lookup"><span data-stu-id="9d72c-131">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="9d72c-132">若要创建或编辑 PSTN 使用记录, 请参阅<A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">在 Lync server 2013 中创建语音策略和配置 pstn 使用记录</A>或<A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">在 lync Server 2013 中修改语音策略和配置 pstn 使用记录</A>。</span><span class="sxs-lookup"><span data-stu-id="9d72c-132">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="9d72c-p108">排列 PSTN 用法记录以获得最佳性能。要更改记录在列表中的位置，请突出显示相应的记录名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="9d72c-p108">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9d72c-135">在语音策略中，PSTN 用法记录的列出顺序非常重要，而在语音路由中，PSTN 用法记录的列出顺序则无关紧要。</span><span class="sxs-lookup"><span data-stu-id="9d72c-135">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="9d72c-136">但是，建议您按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="9d72c-136">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="9d72c-137">（skype16_server_short 按照从上到下的顺序遍历该列表。</span><span class="sxs-lookup"><span data-stu-id="9d72c-137">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="9d72c-138">(Lync Server 从上到下遍历列表。)</span><span class="sxs-lookup"><span data-stu-id="9d72c-138">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="9d72c-p110">（可选）在“输入转换后的号码以进行测试”\*\*\*\* 字段中键入一个值，然后单击“执行”\*\*\*\*。测试结果将显示在该字段下面。</span><span class="sxs-lookup"><span data-stu-id="9d72c-p110">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9d72c-141">你可以保存尚未通过测试的语音路由, 然后稍后重新配置它。</span><span class="sxs-lookup"><span data-stu-id="9d72c-141">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="9d72c-142">有关详细信息, 请参阅<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="9d72c-142">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="9d72c-143">单击“确定”\*\*\*\* 保存语音路由。</span><span class="sxs-lookup"><span data-stu-id="9d72c-143">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9d72c-144">任何时候创建语音路由，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="9d72c-144">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="9d72c-145">有关详细信息, 请参阅<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">在 Lync Server 2013 中将挂起的更改发布到语音路由配置</A>。</span><span class="sxs-lookup"><span data-stu-id="9d72c-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9d72c-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d72c-146">See Also</span></span>


[<span data-ttu-id="9d72c-147">在 Lync Server 2013 中修改语音路由</span><span class="sxs-lookup"><span data-stu-id="9d72c-147">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="9d72c-148">在 Lync Server 2013 中查看 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="9d72c-148">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="9d72c-149">在 Lync Server 2013 中创建语音策略和配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="9d72c-149">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="9d72c-150">在 Lync Server 2013 中修改语音策略和配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="9d72c-150">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="9d72c-151">将挂起的更改发布到 Lync Server 2013 中的语音路由配置</span><span class="sxs-lookup"><span data-stu-id="9d72c-151">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="9d72c-152">在 Lync Server 2013 中测试语音路由</span><span class="sxs-lookup"><span data-stu-id="9d72c-152">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

