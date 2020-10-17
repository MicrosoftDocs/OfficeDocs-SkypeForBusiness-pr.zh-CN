---
title: Lync Server 2013：创建语音路由测试用例
description: Lync Server 2013：创建语音路由测试用例。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d81f4d39a6e3972ebf036fdaca59936f3f6b86bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562398"
---
# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>在 Lync Server 2013 中创建语音路由测试用例

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>创建测试用例

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“语音路由”****，然后单击“测试语音路由”****。

4.  在“测试语音路由”**** 页上，单击“新建”**** 创建新的测试用例。

5.  在“名称”**** 字段中，键入测试用例的唯一名称。
    
    此名称在企业语音部署中的所有语音路由测试用例中必须是唯一的。 它的长度最高为32个字符，并且可以包含任何字母数字字符，除了反斜杠 (\\) 、句点 ( ) 或下划线 (\_) 。

6.  在“要测试的拨打号码”**** 中，键入要用于测试为此测试用例指定的路由配置的拨打号码。基于拨号计划、路由和语音策略，将对此号码进行规范化，并作为输出内容予以显示。

7.  在“拨号计划”**** 列表中，选择在运行测试时要使用的拨号计划。默认为全局拨号计划。

8.  在“语音策略”**** 列表中，选择在运行测试时要使用的语音策略。默认为全局语音策略。

9.  在“预期转换”**** 中，按照预期的转换后的格式键入电话号码。这是要测试的电话号码在按照选定拨号计划中匹配的第一个规范化规则进行转换后的值。在运行测试用例时，如果要测试的号码没有生成“预期转换”**** 中的值，则测试失败。

10. （可选）在“预期 PSTN 用法”**** 列表中，可以根据指定的拨号计划和语音策略选择在运行测试用例时预期使用的公用电话交换网 (PSTN) 用法记录。如果使用不同的 PSTN 用法记录，则测试失败。

11. （可选）在“预期路由”**** 列表中，可以根据指定的拨号计划和语音策略选择在运行测试用例时预期使用的语音路由。如果使用不同的语音路由，则测试失败。

12. （可选）单击“运行”**** 以运行测试用例。结果将显示在页面的右侧面板中。

13. 单击“确定”****。

14. 单击“提交”****，然后单击“全部提交”****。
    
    <div>
    

    > [!NOTE]  
    > 只要您创建语音路由测试用例，就必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。 有关详细信息，请参阅操作文档中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A> 。

    
    </div>
    
    如果在测试中使用的拨号计划规范化以加号 (开头的电话号码（例如，+ 12065551219) ），则该计划可能会导致语音路由测试失败。  (拨号计划和语音路由将正常运行;事实上，Test-CsDialPlan 将会成功。 但是，语音路由测试可能会失败。 ) 在测试语音路由时必须记住这一点。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中导出语音路由测试用例](lync-server-2013-export-voice-routing-test-cases.md)  
[在 Lync Server 2013 中导入语音路由测试用例](lync-server-2013-import-voice-routing-test-cases.md)  


[在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)  
[在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

