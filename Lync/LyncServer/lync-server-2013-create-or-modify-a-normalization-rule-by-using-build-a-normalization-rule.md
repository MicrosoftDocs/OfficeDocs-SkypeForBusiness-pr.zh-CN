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

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>在 Lync Server 2013 中使用 Build a 规范化规则创建或修改规范化规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

如果要在 Lync Server 控制面板中创建或修改规范化规则，请完成以下步骤。 或者，如果您想手动创建或修改规范化规则，请参阅[在 Lync Server 2013 中手动创建或修改规范化规则](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)。

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>使用“建立规范化规则”定义规则

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  Optional按照在 Lync Server 2013 至步骤11中的[Create a 拨号计划](lync-server-2013-create-a-dial-plan.md)中的步骤操作，或在[Lync server 2013 中通过步骤10修改拨号计划](lync-server-2013-modify-a-dial-plan.md)。

4.  在“新建规范化规则”**** 或“编辑规范化规则”**** 的“名称”**** 中，键入描述要进行规范化的号码模式的名称（例如，**5DigitExtension**）。

5.  （可选）在“描述”**** 中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。

6.  在“建立规范化规则”**** 的以下字段中输入值：
    
      - **起始数字**   （可选）指定要使模式与之匹配的拨打号码的前导数字。 例如，如果要使模式与以 425 开头的拨打号码匹配，则键入 **425**。
    
      - **长度**   指定匹配模式中的位数，并选择您是否希望模式与此长度完全匹配、匹配至少为此长度的拨叫号码或匹配任意长度的拨打号码。
    
      - **要删除**   的数字（可选）指定要从所需模式匹配的拨叫号码中删除的起始数字的数量。
    
      - **要添加**   的数字（可选）指定要添加到要模式匹配的拨打的号码的数字。
    
    这些字段中输入的值将反映在“要匹配的模式”**** 和“转换规则”**** 中。例如，如果将“起始数字”**** 留空，在“长度”**** 字段中键入 **7** 并选择“完全匹配”****，然后在“要删除的数字”**** 中指定 **0**，则在“要匹配的模式”**** 中生成的正则表达式如下所示：
    
    **^ （\\d{7}） $**

7.  在“转换规则”**** 中，指定转换后的 E.164 电话号码格式的模式，如下所示：
    
      - 代表匹配模式中指定的号码位数的值。 例如，如果匹配模式是 **^ （\\d{7}） $** ，则转换规则中的 **$1**代表7位拨打的号码。
    
      - （可选）在“要添加的数字”**** 字段中键入值，指定要附加到转换后的号码前面的数字（例如 **+1425**）。
    
    例如，如果**要匹配的模式**包含 **^ （\\d{7}） $** 作为拨打的号码和**转换规则**的模式，则包含 **+ 1425 $ 1**作为 e.164 电话号码的模式，该规则会将5550100规范化为 + 14255550100。

8.  （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”****。

9.  （可选）输入一个号码以测试规范化规则，然后单击“执行”****。测试结果会显示在“输入要测试的号码”**** 下。
    
    <div>
    

    > [!NOTE]
    > 您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。 有关详细信息，请参阅<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。

    
    </div>

10. 单击“确定”**** 保存规范化规则。

11. 单击“确定”**** 保存拨号计划。

12. 在“拨号计划”**** 页上，单击“提交”****，然后单击“全部提交”****。
    
    <div>
    

    > [!NOTE]
    > 无论何时创建或更改规范化规则，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。 有关详细信息，请参阅操作文档中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中手动创建或修改规范化规则](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
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

