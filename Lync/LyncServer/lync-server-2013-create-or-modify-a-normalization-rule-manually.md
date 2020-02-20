---
title: Lync Server 2013：手动创建或修改规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e265563bb7091b72967174a2de11f07d8b8cc29b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a><span data-ttu-id="39a1b-102">在 Lync Server 2013 中手动创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="39a1b-102">Create or modify a normalization rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39a1b-103">_**上次修改的主题：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="39a1b-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="39a1b-104">如果要手动创建或修改规范化规则，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="39a1b-104">Complete the following steps if you want to create or modify a normalization rule manually.</span></span> <span data-ttu-id="39a1b-105">如果要使用 "在 Lync Server 控制面板中构建规范化规则" 创建或修改规范化规则，请参阅[在 Lync server 2013 中使用 build a 规范化规则创建或修改规范化规则](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)。</span><span class="sxs-lookup"><span data-stu-id="39a1b-105">If you want to create or modify a normalization rule by using Build a Normalization Rule in Lync Server Control Panel, see [Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span></span>

<div>

## <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="39a1b-106">手动定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="39a1b-106">To define a normalization rule manually</span></span>

1.  <span data-ttu-id="39a1b-107">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="39a1b-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="39a1b-108">有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="39a1b-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="39a1b-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="39a1b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="39a1b-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="39a1b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="39a1b-111">Optional按照在[Lync server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)中的步骤或[在 lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="39a1b-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

4.  <span data-ttu-id="39a1b-112">在“新建规范化规则”\*\*\*\* 或“编辑规范化规则”\*\*\*\* 的“名称”\*\*\*\* 中，键入描述要进行规范化的号码模式的名称（例如，将规范化规则命名为 **5DigitExtension**）。</span><span class="sxs-lookup"><span data-stu-id="39a1b-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule **5DigitExtension**).</span></span>

5.  <span data-ttu-id="39a1b-113">（可选）在“说明”\*\*\*\* 字段中，键入规范化规则的说明（例如，“Translates 5-digit extensions”）。</span><span class="sxs-lookup"><span data-stu-id="39a1b-113">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="39a1b-114">在“建立规范化规则”\*\*\*\* 中，单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39a1b-114">In **Build a Normalization Rule**, click **Edit**.</span></span>

7.  <span data-ttu-id="39a1b-115">在“键入正则表达式”\*\*\*\* 中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="39a1b-115">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="39a1b-116">在“匹配此模式”\*\*\*\* 中，指定要用于匹配拨打的电话号码的模式。</span><span class="sxs-lookup"><span data-stu-id="39a1b-116">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
      - <span data-ttu-id="39a1b-117">在“转换规则”\*\*\*\* 中，指定转换后的 E.164 电话号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="39a1b-117">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="39a1b-118">例如，如果在 "**转换规则**" 中输入 " **^\\{7}（d） $** " 与此模式和 **+ 1425 $ 1** **相匹配**，则该规则会将5550100规范化为 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="39a1b-118">For example, if you enter **^(\\d{7})$** in **Match this pattern** and **+1425$1** in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="39a1b-119">（可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39a1b-119">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="39a1b-p104">（可选）输入一个号码以测试规范化规则，然后单击“执行”\*\*\*\*。测试结果会显示在“输入要测试的号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="39a1b-p104">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39a1b-122">您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。</span><span class="sxs-lookup"><span data-stu-id="39a1b-122">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="39a1b-123">有关详细信息，请参阅<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="39a1b-123">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="39a1b-124">单击“确定”\*\*\*\* 保存规范化规则。</span><span class="sxs-lookup"><span data-stu-id="39a1b-124">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="39a1b-125">单击“确定”\*\*\*\* 保存拨号计划。</span><span class="sxs-lookup"><span data-stu-id="39a1b-125">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="39a1b-126">在“拨号计划”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39a1b-126">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39a1b-127">无论何时创建或更改规范化规则，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="39a1b-127">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="39a1b-128">有关详细信息，请参阅操作文档中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A>。</span><span class="sxs-lookup"><span data-stu-id="39a1b-128">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="39a1b-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39a1b-129">See Also</span></span>


[<span data-ttu-id="39a1b-130">在 Lync Server 2013 中使用 Build a 规范化规则创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="39a1b-130">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[<span data-ttu-id="39a1b-131">在 Lync Server 2013 中创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="39a1b-131">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="39a1b-132">在 Lync Server 2013 中修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="39a1b-132">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="39a1b-133">在 Lync Server 2013 中发布对语音路由配置所做的挂起更改</span><span class="sxs-lookup"><span data-stu-id="39a1b-133">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="39a1b-134">在 Lync Server 2013 中测试语音路由</span><span class="sxs-lookup"><span data-stu-id="39a1b-134">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

