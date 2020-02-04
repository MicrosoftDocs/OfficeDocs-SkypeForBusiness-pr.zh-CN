---
title: Lync Server 2013：手动创建或修改翻译规则
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
ms.openlocfilehash: 372b394619a83ec01ca7a36bac4037c815f09fc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>在 Lync Server 2013 中手动创建或修改翻译规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-08-06_

如果要通过编写匹配模式和转换规则的正则表达式来定义翻译规则，请执行以下步骤。 或者，你可以在 "**生成翻译规则**" 工具中输入一组值，并启用 Lync Server 控制面板来为你生成相应的匹配模式和转换规则。 有关详细信息，请参阅[使用 Lync Server 2013 中的 "生成翻译规则" 工具创建或修改翻译规则](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)。

<div>

## <a name="to-define-a-translation-rule-manually"></a>手动定义转换规则

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  若要开始定义翻译规则，请按照在 Lync server 2013 中的 "通过[媒体绕过媒体配置主干](lync-server-2013-configure-a-trunk-with-media-bypass.md)" 中的步骤执行步骤10，或在[lync server 2013 中通过步骤9配置中继而不绕过媒体旁路](lync-server-2013-configure-a-trunk-without-media-bypass.md)。

4.  在“新建转换规则”**** 或“编辑转换规则”**** 页上的“名称”**** 字段中，键入描述要转换的号码模式的名称。

5.  （可选）在“说明”**** 中，键入转换规则的说明，例如，**US International long-distance dialing**。

6.  单击“构建转换规则”**** 部分底部的“编辑”****。

7.  在“键入正则表达式”**** 中输入以下内容：
    
      - 在“匹配此模式”**** 中，指定将用于匹配要转换的号码的模式。
    
      - 在“转换规则”**** 中，指定转换号码格式的模式。
    
    例如，如果在 "**转换规则**" 中输入** ^ \\"+" （\\d{9}\\d +） $** **与此模式**和**011 $ 1** ，则规则将 + 441235551010 转换为011441235551010。

8.  单击“确定”**** 保存转换规则。

9.  单击“确定”**** 保存中继配置。

10. 在“Trunk 配置”**** 页上，单击“提交”****，然后单击“全部提交”****。
    
    <div>
    

    > [!NOTE]  
    > 每当创建或修改转换规则时，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。 有关详细信息，请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[使用 Lync Server 2013 中的 "生成翻译规则" 工具创建或修改翻译规则](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中配置不使用 "媒体旁路" 的主干](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[将挂起的更改发布到 Lync Server 2013 中的语音路由配置](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013 中的全局媒体绕过选项](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

