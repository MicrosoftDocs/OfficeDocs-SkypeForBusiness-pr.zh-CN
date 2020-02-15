---
title: Lync Server 2013：手动创建或修改转换规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ae305052523c05bacb294928c1f81afd4e51931
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41995537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="d96be-102">在 Lync Server 2013 中手动创建或修改转换规则</span><span class="sxs-lookup"><span data-stu-id="d96be-102">Create or modify a translation rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d96be-103">_**上次修改的主题：** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="d96be-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="d96be-104">如果要通过为匹配模式和转换规则编写正则表达式来定义转换规则，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="d96be-104">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="d96be-105">或者，也可以在 "**生成转换规则**" 工具中输入一组值，并启用 Lync Server 控制面板以生成对应的匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="d96be-105">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="d96be-106">有关详细信息，请参阅[创建或修改转换规则，方法是使用 Lync Server 2013 中的 "构建转换规则" 工具](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="d96be-106">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="d96be-107">手动定义转换规则</span><span class="sxs-lookup"><span data-stu-id="d96be-107">To define a translation rule manually</span></span>

1.  <span data-ttu-id="d96be-108">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="d96be-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="d96be-109">有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="d96be-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d96be-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="d96be-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d96be-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="d96be-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d96be-112">若要开始定义转换规则，请按照在[lync server 2013 中的 "使用媒体旁路配置中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)" 中的步骤，通过步骤10或[在 lync server 2013 中](lync-server-2013-configure-a-trunk-without-media-bypass.md)的步骤9中配置不使用媒体旁路的中继。</span><span class="sxs-lookup"><span data-stu-id="d96be-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="d96be-113">在“新建转换规则”\*\*\*\* 或“编辑转换规则”\*\*\*\* 页上的“名称”\*\*\*\* 字段中，键入描述要转换的号码模式的名称。</span><span class="sxs-lookup"><span data-stu-id="d96be-113">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="d96be-114">（可选）在“说明”\*\*\*\* 字段中，键入转换规则的说明，例如，**美国国际长途拨号**。</span><span class="sxs-lookup"><span data-stu-id="d96be-114">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="d96be-115">单击“构建转换规则”\*\*\*\* 部分底部的“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d96be-115">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="d96be-116">在“键入正则表达式”\*\*\*\* 中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="d96be-116">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="d96be-117">在“匹配此模式”\*\*\*\* 中，指定将用于匹配要转换的号码的模式。</span><span class="sxs-lookup"><span data-stu-id="d96be-117">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="d96be-118">在“转换规则”\*\*\*\* 中，指定转换号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="d96be-118">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="d96be-119">例如，如果在 "**转换规则**" 中输入\*\* ^ \\"+"\\（d{9}\\d +） $\*\* 与**此模式**和**011 $ 1** ，则该规则会将 + 441235551010 转换为011441235551010。</span><span class="sxs-lookup"><span data-stu-id="d96be-119">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="d96be-120">单击“确定”\*\*\*\* 保存转换规则。</span><span class="sxs-lookup"><span data-stu-id="d96be-120">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="d96be-121">单击“确定”\*\*\*\* 保存 Trunk 配置。</span><span class="sxs-lookup"><span data-stu-id="d96be-121">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="d96be-122">在“Trunk 配置”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d96be-122">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d96be-123">每当创建或修改转换规则时，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="d96be-123">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="d96be-124">有关详细信息，请参阅操作文档中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A>。</span><span class="sxs-lookup"><span data-stu-id="d96be-124">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d96be-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d96be-125">See Also</span></span>


[<span data-ttu-id="d96be-126">使用 Lync Server 2013 中的 "构建转换规则" 工具创建或修改转换规则</span><span class="sxs-lookup"><span data-stu-id="d96be-126">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="d96be-127">在 Lync Server 2013 中配置具有媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="d96be-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="d96be-128">在 Lync Server 2013 中配置无媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="d96be-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="d96be-129">在 Lync Server 2013 中发布对语音路由配置所做的挂起更改</span><span class="sxs-lookup"><span data-stu-id="d96be-129">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="d96be-130">Lync Server 2013 中的全局媒体旁路选项</span><span class="sxs-lookup"><span data-stu-id="d96be-130">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

