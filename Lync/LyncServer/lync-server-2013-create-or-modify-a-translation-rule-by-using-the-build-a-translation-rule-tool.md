---
title: 使用 "生成转换规则" 工具创建或修改转换规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8321603c699fb0f25fc0a3a1b94e8b216761c6b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="c8dfb-102">使用 Lync Server 2013 中的 "构建转换规则" 工具创建或修改转换规则</span><span class="sxs-lookup"><span data-stu-id="c8dfb-102">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8dfb-103">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c8dfb-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c8dfb-104">如果要定义转换规则，请执行以下步骤：在 "**生成转换规则**" 工具中输入一组值并启用 Lync Server 控制面板为您生成相应的匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-104">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="c8dfb-105">或者，可以手动编写正则表达式来定义匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-105">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="c8dfb-106">有关详细信息，请参阅[在 Lync Server 2013 中手动创建或修改转换规则](lync-server-2013-create-or-modify-a-translation-rule-manually.md)。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-106">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="c8dfb-107">使用“构建转换规则”工具定义规则</span><span class="sxs-lookup"><span data-stu-id="c8dfb-107">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="c8dfb-108">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c8dfb-109">有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c8dfb-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c8dfb-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c8dfb-112">若要开始定义转换规则，请按照在[lync server 2013 中的 "使用媒体旁路配置中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)" 中的步骤，通过步骤10或[在 lync server 2013 中](lync-server-2013-configure-a-trunk-without-media-bypass.md)的步骤9中配置不使用媒体旁路的中继。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="c8dfb-113">在“新建转换规则”\*\*\*\* 或“编辑转换规则”\*\*\*\* 页上的“名称”\*\*\*\* 下，键入描述要转换的号码模式的名称。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-113">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="c8dfb-114">（可选）在“说明”\*\*\*\* 下，键入转换规则的说明，例如，**美国国际长途拨号**。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-114">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="c8dfb-115">在对话框的“构建转换规则”\*\*\*\* 部分的以下字段中输入值：</span><span class="sxs-lookup"><span data-stu-id="c8dfb-115">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="c8dfb-116">**起始数字**：（可选）指定要使模式与之匹配的号码的前导数字。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-116">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="c8dfb-117">例如，在此**+** 字段中输入，以匹配采用. 164 格式的数字（以 + 开头）。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-117">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="c8dfb-p105">**长度**：指定匹配模式中的数字位数，并选择希望模式匹配的号码是必须具有此准确长度、至少具有此长度还是可以具有任何长度。例如，输入 **11** 并在下拉列表中选择**至少**可匹配长度至少为 11 位的号码。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-p105">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length. For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="c8dfb-120">**要删除的数字**：（可选）指定要删除的起始数字的位数。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-120">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="c8dfb-121">例如，输入**1**以**+** 从数字开头处抽出。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-121">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="c8dfb-p107">**要添加的数字**：（可选）指定要附加到转换号码前面的数字。例如，如果要在应用规则时将 011 附加到转换号码的前面，则输入 **011**。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-p107">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="c8dfb-p108">这些字段中输入的值将反映在“要匹配的模式”\*\*\*\* 和“转换规则”\*\*\*\* 字段中。例如，如果指定前面示例中的值，则“要匹配的模式”\*\*\*\* 字段中生成的正则表达式为：</span><span class="sxs-lookup"><span data-stu-id="c8dfb-p108">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="c8dfb-126">**^\\+ （\\d{9}\\d +） $**</span><span class="sxs-lookup"><span data-stu-id="c8dfb-126">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="c8dfb-p109">“转换规则”\*\*\*\* 字段指定转换号码格式的模式。该模式由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="c8dfb-p109">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
      - <span data-ttu-id="c8dfb-129">代表匹配模式中数字位数的值（例如，**$1**）</span><span class="sxs-lookup"><span data-stu-id="c8dfb-129">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="c8dfb-130">（可选）可以通过在“要添加的数字”\*\*\*\* 字段中输入来附加的值</span><span class="sxs-lookup"><span data-stu-id="c8dfb-130">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="c8dfb-131">如果使用前面示例中的值，“转换规则”\*\*\*\* 字段中将显示 **011$1**。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-131">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="c8dfb-132">应用此转换规则后，+441235551010 将变为 011441235551010。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-132">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="c8dfb-133">单击“确定”\*\*\*\* 保存转换规则。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-133">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="c8dfb-134">单击“确定”\*\*\*\* 保存 Trunk 配置。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-134">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="c8dfb-135">在“Trunk 配置”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-135">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="c8dfb-136">每当创建或修改转换规则时，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-136">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="c8dfb-137">有关详细信息，请参阅操作文档中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A>。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8dfb-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8dfb-138">See Also</span></span>


[<span data-ttu-id="c8dfb-139">在 Lync Server 2013 中手动创建或修改转换规则</span><span class="sxs-lookup"><span data-stu-id="c8dfb-139">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="c8dfb-140">在 Lync Server 2013 中配置具有媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="c8dfb-140">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="c8dfb-141">在 Lync Server 2013 中配置无媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="c8dfb-141">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="c8dfb-142">在 Lync Server 2013 中发布对语音路由配置所做的挂起更改</span><span class="sxs-lookup"><span data-stu-id="c8dfb-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="c8dfb-143">Lync Server 2013 中的全局媒体旁路选项</span><span class="sxs-lookup"><span data-stu-id="c8dfb-143">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

