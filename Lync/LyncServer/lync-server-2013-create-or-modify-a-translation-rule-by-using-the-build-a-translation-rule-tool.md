---
title: 使用 "生成翻译规则" 工具创建或修改翻译规则
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
ms.openlocfilehash: d45ca4e04146a175ec2782aa798ac27559fce495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>使用 Lync Server 2013 中的 "生成翻译规则" 工具创建或修改翻译规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-05_

如果要定义翻译规则，请执行以下步骤：在 "**生成翻译规则**" 工具中输入一组值，并启用 Lync Server "控制面板" 为你生成相应的匹配模式和转换规则。 或者，可以手动编写正则表达式来定义匹配模式和转换规则。 有关详细信息，请参阅[在 Lync Server 2013 中手动创建或修改翻译规则](lync-server-2013-create-or-modify-a-translation-rule-manually.md)。

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>使用“构建转换规则”工具定义规则

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  若要开始定义翻译规则，请按照在 Lync server 2013 中的 "通过[媒体绕过媒体配置主干](lync-server-2013-configure-a-trunk-with-media-bypass.md)" 中的步骤执行步骤10，或在[lync server 2013 中通过步骤9配置中继而不绕过媒体旁路](lync-server-2013-configure-a-trunk-without-media-bypass.md)。

4.  在“新建转换规则”**** 或“编辑转换规则”**** 页上的“名称”**** 下，键入描述要转换的号码模式的名称。

5.  （可选）在“说明”**** 下，键入转换规则的说明，例如，**US International long-distance dialing**。

6.  在对话框的“构建转换规则”**** 部分的以下字段中输入值：
    
      - **起始数字**：（可选）指定要使模式与之匹配的号码的前导数字。 例如，在此**+** 字段中输入，以匹配 E. 164 格式的数字（以 + 开头）。
    
      - **长度**：指定匹配模式中的数字位数，并选择希望模式匹配的号码是必须具有此准确长度、至少具有此长度还是可以具有任何长度。例如，输入 **11** 并在下拉列表中选择**At least**可匹配长度至少为 11 位的号码。
    
      - **要删除的数字**：（可选）指定要删除的起始数字的位数。 例如，输入 " **1** " **+** 将从号码的开头去掉。
    
      - **要添加的数字**：（可选）指定要附加到转换号码前面的数字。例如，如果要在应用规则时将 011 附加到转换号码的前面，则输入 **011**。
    
    这些字段中输入的值将反映在“要匹配的模式”**** 和“转换规则”**** 字段中。例如，如果指定前面示例中的值，则“要匹配的模式”**** 字段中生成的正则表达式为：
    
    **^\\+ （\\d{9}\\d +） $**
    
    “转换规则”**** 字段指定转换号码格式的模式。该模式由两部分组成：
    
      - 代表匹配模式中数字位数的值（例如，**$1**）
    
      - （可选）可以通过在“要添加的数字”**** 字段中输入来附加的值
    
    如果使用前面示例中的值，“转换规则”**** 字段中将显示 **011$1**。
    
    应用此转换规则后，+441235551010 将变为 011441235551010。

7.  单击“确定”**** 保存转换规则。

8.  单击“确定”**** 保存中继配置。

9.  在“Trunk 配置”**** 页上，单击“提交”****，然后单击“全部提交”****。
    
    <div>
    

    > [!NOTE]
    > 每当创建或修改转换规则时，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。 有关详细信息，请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中手动创建或修改翻译规则](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
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

