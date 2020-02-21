---
title: 使用生成规范化规则创建或修改规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02bbebae55504fcc27550bae3b90d7fca662a487
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a><span data-ttu-id="8bfe3-102">在 Lync Server 2013 中使用 Build a 规范化规则创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="8bfe3-102">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bfe3-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8bfe3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8bfe3-104">如果要在 Lync Server 控制面板中创建或修改规范化规则，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-104">Complete the following steps if you want to create or modify a normalization rule in Lync Server Control Panel.</span></span> <span data-ttu-id="8bfe3-105">或者，如果您想手动创建或修改规范化规则，请参阅[在 Lync Server 2013 中手动创建或修改规范化规则](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-105">Alternatively, if you want to create or modify a normalization rule manually, see [Create or modify a normalization rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="8bfe3-106">使用“建立规范化规则”定义规则</span><span class="sxs-lookup"><span data-stu-id="8bfe3-106">To define a rule by using Build a Normalization Rule</span></span>

1.  <span data-ttu-id="8bfe3-107">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8bfe3-108">有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8bfe3-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8bfe3-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8bfe3-111">Optional按照在 Lync Server 2013 至步骤11中的[Create a 拨号计划](lync-server-2013-create-a-dial-plan.md)中的步骤操作，或在[Lync server 2013 中通过步骤10修改拨号计划](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) through step 11 or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) through step 10.</span></span>

4.  <span data-ttu-id="8bfe3-112">在“新建规范化规则”\*\*\*\* 或“编辑规范化规则”\*\*\*\* 的“名称”\*\*\*\* 中，键入描述要进行规范化的号码模式的名称（例如，**5DigitExtension**）。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>

5.  <span data-ttu-id="8bfe3-113">（可选）在“描述”\*\*\*\* 中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-113">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="8bfe3-114">在“建立规范化规则”\*\*\*\* 的以下字段中输入值：</span><span class="sxs-lookup"><span data-stu-id="8bfe3-114">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="8bfe3-115">**起始数字**   （可选）指定要使模式与之匹配的拨打号码的前导数字。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-115">**Starting digits**   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="8bfe3-116">例如，如果要使模式与以 425 开头的拨打号码匹配，则键入 **425**。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-116">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
      - <span data-ttu-id="8bfe3-117">**长度**   指定匹配模式中的位数，并选择您是否希望模式与此长度完全匹配、匹配至少为此长度的拨叫号码或匹配任意长度的拨打号码。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-117">**Length**   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
      - <span data-ttu-id="8bfe3-118">**要删除**   的数字（可选）指定要从所需模式匹配的拨叫号码中删除的起始数字的数量。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-118">**Digits to remove**   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
      - <span data-ttu-id="8bfe3-119">**要添加**   的数字（可选）指定要添加到要模式匹配的拨打的号码的数字。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-119">**Digits to add**   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="8bfe3-p105">这些字段中输入的值将反映在“要匹配的模式”\*\*\*\* 和“转换规则”\*\*\*\* 中。例如，如果将“起始数字”\*\*\*\* 留空，在“长度”\*\*\*\* 字段中键入 **7** 并选择“完全匹配”\*\*\*\*，然后在“要删除的数字”\*\*\*\* 中指定 **0**，则在“要匹配的模式”\*\*\*\* 中生成的正则表达式如下所示：</span><span class="sxs-lookup"><span data-stu-id="8bfe3-p105">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**. For example, if you leave **Starting digits** empty, type **7** into the **Length** field and select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="8bfe3-122">**^ （\\d{7}） $**</span><span class="sxs-lookup"><span data-stu-id="8bfe3-122">**^(\\d{7})$**</span></span>

7.  <span data-ttu-id="8bfe3-123">在“转换规则”\*\*\*\* 中，指定转换后的 E.164 电话号码格式的模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8bfe3-123">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
      - <span data-ttu-id="8bfe3-124">代表匹配模式中指定的号码位数的值。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-124">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="8bfe3-125">例如，如果匹配模式是 **^ （\\d{7}） $** ，则转换规则中的 **$1**代表7位拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-125">For example, if the matching pattern is **^(\\d{7})$** then **$1** in the translation rule represents 7-digit dialed numbers.</span></span>
    
      - <span data-ttu-id="8bfe3-126">（可选）在“要添加的数字”\*\*\*\* 字段中键入值，指定要附加到转换后的号码前面的数字（例如 **+1425**）。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-126">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="8bfe3-127">例如，如果**要匹配的模式**包含 **^ （\\d{7}） $** 作为拨打的号码和**转换规则**的模式，则包含 **+ 1425 $ 1**作为 e.164 电话号码的模式，该规则会将5550100规范化为 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-127">For example, if **Pattern to match** contains **^(\\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="8bfe3-128">（可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-128">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="8bfe3-p107">（可选）输入一个号码以测试规范化规则，然后单击“执行”\*\*\*\*。测试结果会显示在“输入要测试的号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-p107">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8bfe3-131">您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-131">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="8bfe3-132">有关详细信息，请参阅<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-132">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="8bfe3-133">单击“确定”\*\*\*\* 保存规范化规则。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-133">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="8bfe3-134">单击“确定”\*\*\*\* 保存拨号计划。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-134">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="8bfe3-135">在“拨号计划”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-135">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8bfe3-136">无论何时创建或更改规范化规则，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-136">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="8bfe3-137">有关详细信息，请参阅操作文档中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A>。</span><span class="sxs-lookup"><span data-stu-id="8bfe3-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8bfe3-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bfe3-138">See Also</span></span>


[<span data-ttu-id="8bfe3-139">在 Lync Server 2013 中手动创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="8bfe3-139">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[<span data-ttu-id="8bfe3-140">在 Lync Server 2013 中创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="8bfe3-140">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="8bfe3-141">在 Lync Server 2013 中修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="8bfe3-141">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="8bfe3-142">在 Lync Server 2013 中发布对语音路由配置所做的挂起更改</span><span class="sxs-lookup"><span data-stu-id="8bfe3-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="8bfe3-143">在 Lync Server 2013 中测试语音路由</span><span class="sxs-lookup"><span data-stu-id="8bfe3-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

