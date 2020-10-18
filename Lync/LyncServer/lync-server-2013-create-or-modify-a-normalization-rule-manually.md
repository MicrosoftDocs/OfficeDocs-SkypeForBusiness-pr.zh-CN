---
title: Lync Server 2013：手动创建或修改规范化规则
description: Lync Server 2013：手动创建或修改规范化规则。
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
ms.openlocfilehash: a7cc61706dd91b52822747d59693c8998d244c08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574578"
---
# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>在 Lync Server 2013 中手动创建或修改规范化规则

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-22_

如果要手动创建或修改规范化规则，请执行以下步骤。 如果要使用 "在 Lync Server 控制面板中构建规范化规则" 创建或修改规范化规则，请参阅 [在 Lync server 2013 中使用 build a 规范化规则创建或修改规范化规则](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)。

<div>

## <a name="to-define-a-normalization-rule-manually"></a>手动定义规范化规则

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.   (可选) 按照 "在 [Lync server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md) " 或 ["在 lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)" 中的步骤操作。

4.  在“新建规范化规则”**** 或“编辑规范化规则”**** 的“名称”**** 中，键入描述要进行规范化的号码模式的名称（例如，将规范化规则命名为 **5DigitExtension**）。

5.  （可选）在“说明”**** 字段中，键入规范化规则的说明（例如，“Translates 5-digit extensions”）。

6.  在“建立规范化规则”**** 中，单击“编辑”****。

7.  在“键入正则表达式”**** 中输入以下内容：
    
      - 在“匹配此模式”**** 中，指定要用于匹配拨打的电话号码的模式。
    
      - 在“转换规则”**** 中，指定转换后的 E.164 电话号码格式的模式。
    
    例如，如果在**转换规则**中输入 **^ (\\ d {7}) $** **与此模式**和 **+ 1425 $ 1**相匹配，则该规则会将5550100规范化为 + 14255550100。

8.  （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”****。

9.  （可选）输入一个号码以测试规范化规则，然后单击“执行”****。测试结果会显示在“输入要测试的号码”**** 下。
    
    <div>
    

    > [!NOTE]  
    > 您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。 有关详细信息，请参阅 <A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。

    
    </div>

10. 单击“确定”**** 保存规范化规则。

11. 单击“确定”**** 保存拨号计划。

12. 在“拨号计划”**** 页上，单击“提交”****，然后单击“全部提交”****。
    
    <div>
    

    > [!NOTE]  
    > 无论何时创建或更改规范化规则，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。 有关详细信息，请参阅操作文档中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A> 。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中使用 Build a 规范化规则创建或修改规范化规则](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)  
[在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)  
[在 Lync Server 2013 中发布对语音路由配置所做的挂起更改](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

