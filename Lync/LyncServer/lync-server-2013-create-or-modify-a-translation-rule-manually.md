---
title: 'Lync Server 2013: 手动创建或修改翻译规则'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445b17b5a878e066ed0a77c725ae035101d57469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="b3caf-102">在 Lync Server 2013 中手动创建或修改翻译规则</span><span class="sxs-lookup"><span data-stu-id="b3caf-102">Create or modify a translation rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3caf-103">_**主题上次修改时间:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="b3caf-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="b3caf-104">如果要通过编写匹配模式和转换规则的正则表达式来定义翻译规则, 请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b3caf-104">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="b3caf-105">或者, 你可以在 "**生成翻译规则**" 工具中输入一组值, 并启用 Lync Server 控制面板来为你生成相应的匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="b3caf-105">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="b3caf-106">有关详细信息, 请参阅[使用 Lync Server 2013 中的 "生成翻译规则" 工具创建或修改翻译规则](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="b3caf-106">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="b3caf-107">手动定义转换规则</span><span class="sxs-lookup"><span data-stu-id="b3caf-107">To define a translation rule manually</span></span>

1.  <span data-ttu-id="b3caf-108">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="b3caf-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b3caf-109">有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="b3caf-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b3caf-110">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b3caf-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b3caf-111">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b3caf-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b3caf-112">若要开始定义翻译规则, 请按照在 Lync server 2013 中的 "通过[媒体绕过媒体配置主干](lync-server-2013-configure-a-trunk-with-media-bypass.md)" 中的步骤执行步骤 10, 或在[lync server 2013 中通过步骤9配置中继而不绕过媒体旁路](lync-server-2013-configure-a-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="b3caf-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="b3caf-113">在“新建转换规则”\*\*\*\* 或“编辑转换规则”\*\*\*\* 页上的“名称”\*\*\*\* 字段中，键入描述要转换的号码模式的名称。</span><span class="sxs-lookup"><span data-stu-id="b3caf-113">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="b3caf-114">（可选）在“说明”\*\*\*\* 中，键入转换规则的说明，例如，**US International long-distance dialing**。</span><span class="sxs-lookup"><span data-stu-id="b3caf-114">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="b3caf-115">单击“构建转换规则”\*\*\*\* 部分底部的“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b3caf-115">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="b3caf-116">在“键入正则表达式”\*\*\*\* 中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="b3caf-116">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="b3caf-117">在“匹配此模式”\*\*\*\* 中，指定将用于匹配要转换的号码的模式。</span><span class="sxs-lookup"><span data-stu-id="b3caf-117">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="b3caf-118">在“转换规则”\*\*\*\* 中，指定转换号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="b3caf-118">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="b3caf-119">例如, 如果在 "**转换规则**" 中输入\*\* ^ \\"+" (\\d{9}\\d +) $\*\* **与此模式**和**011 $ 1** , 则规则将 + 441235551010 转换为011441235551010。</span><span class="sxs-lookup"><span data-stu-id="b3caf-119">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="b3caf-120">单击“确定”\*\*\*\* 保存转换规则。</span><span class="sxs-lookup"><span data-stu-id="b3caf-120">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="b3caf-121">单击“确定”\*\*\*\* 保存中继配置。</span><span class="sxs-lookup"><span data-stu-id="b3caf-121">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="b3caf-122">在“Trunk 配置”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b3caf-122">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3caf-123">每当创建或修改转换规则时，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="b3caf-123">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="b3caf-124">有关详细信息, 请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。</span><span class="sxs-lookup"><span data-stu-id="b3caf-124">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3caf-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3caf-125">See Also</span></span>


[<span data-ttu-id="b3caf-126">使用 Lync Server 2013 中的 "生成翻译规则" 工具创建或修改翻译规则</span><span class="sxs-lookup"><span data-stu-id="b3caf-126">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="b3caf-127">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3caf-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="b3caf-128">在 Lync Server 2013 中配置不使用 "媒体旁路" 的主干</span><span class="sxs-lookup"><span data-stu-id="b3caf-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="b3caf-129">将挂起的更改发布到 Lync Server 2013 中的语音路由配置</span><span class="sxs-lookup"><span data-stu-id="b3caf-129">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="b3caf-130">Lync Server 2013 中的全局媒体绕过选项</span><span class="sxs-lookup"><span data-stu-id="b3caf-130">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

