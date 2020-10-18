---
title: Lync Server 2013：手动创建或修改转换规则
description: Lync Server 2013：手动创建或修改转换规则。
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
ms.openlocfilehash: 4f393ca1983e072090cc27d47b142dace8b566c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574498"
---
# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="0e8a5-103">在 Lync Server 2013 中手动创建或修改转换规则</span><span class="sxs-lookup"><span data-stu-id="0e8a5-103">Create or modify a translation rule manually in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e8a5-104">_**上次修改的主题：** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="0e8a5-104">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="0e8a5-105">如果要通过为匹配模式和转换规则编写正则表达式来定义转换规则，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-105">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="0e8a5-106">或者，也可以在 " **生成转换规则** " 工具中输入一组值，并启用 Lync Server 控制面板以生成对应的匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-106">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="0e8a5-107">有关详细信息，请参阅 [创建或修改转换规则，方法是使用 Lync Server 2013 中的 "构建转换规则" 工具](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-107">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="0e8a5-108">手动定义转换规则</span><span class="sxs-lookup"><span data-stu-id="0e8a5-108">To define a translation rule manually</span></span>

1.  <span data-ttu-id="0e8a5-109">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0e8a5-110">有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="0e8a5-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0e8a5-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0e8a5-113">若要开始定义转换规则，请按照在 [lync server 2013 中的 "使用媒体旁路配置中继](lync-server-2013-configure-a-trunk-with-media-bypass.md) " 中的步骤，通过步骤10或 [在 lync server 2013 中](lync-server-2013-configure-a-trunk-without-media-bypass.md) 的步骤9中配置不使用媒体旁路的中继。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-113">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="0e8a5-114">在“新建转换规则”\*\*\*\* 或“编辑转换规则”\*\*\*\* 页上的“名称”\*\*\*\* 字段中，键入描述要转换的号码模式的名称。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-114">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="0e8a5-115">（可选）在“说明”\*\*\*\* 字段中，键入转换规则的说明，例如，**美国国际长途拨号**。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-115">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="0e8a5-116">单击“构建转换规则”\*\*\*\* 部分底部的“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-116">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="0e8a5-117">在“键入正则表达式”\*\*\*\* 中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="0e8a5-117">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="0e8a5-118">在“匹配此模式”\*\*\*\* 中，指定将用于匹配要转换的号码的模式。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-118">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="0e8a5-119">在“转换规则”\*\*\*\* 中，指定转换号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-119">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="0e8a5-120">例如，如果在**转换规则**中输入\*\* ^ \\ + (\\ d {9} \\ d +) $\*\* **与此模式**和**011 $ 1**相匹配，则该规则会将 + 441235551010 转换为011441235551010。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-120">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="0e8a5-121">单击“确定”\*\*\*\* 保存转换规则。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-121">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="0e8a5-122">单击“确定”\*\*\*\* 保存 Trunk 配置。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-122">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="0e8a5-123">在“Trunk 配置”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-123">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0e8a5-124">每当创建或修改转换规则时，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-124">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="0e8a5-125">有关详细信息，请参阅操作文档中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A> 。</span><span class="sxs-lookup"><span data-stu-id="0e8a5-125">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0e8a5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e8a5-126">See Also</span></span>


[<span data-ttu-id="0e8a5-127">使用 Lync Server 2013 中的 "构建转换规则" 工具创建或修改转换规则</span><span class="sxs-lookup"><span data-stu-id="0e8a5-127">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="0e8a5-128">在 Lync Server 2013 中配置具有媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="0e8a5-128">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="0e8a5-129">在 Lync Server 2013 中配置无媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="0e8a5-129">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="0e8a5-130">在 Lync Server 2013 中发布对语音路由配置所做的挂起更改</span><span class="sxs-lookup"><span data-stu-id="0e8a5-130">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="0e8a5-131">Lync Server 2013 中的全局媒体旁路选项</span><span class="sxs-lookup"><span data-stu-id="0e8a5-131">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

