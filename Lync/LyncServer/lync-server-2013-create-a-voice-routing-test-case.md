---
title: Lync Server 2013：创建语音路由测试用例
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
ms.openlocfilehash: c706064cbe7319d3cb485b0bb1ecf6d34902edde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>在 Lync Server 2013 中创建语音路由测试用例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>创建测试用例

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**语音路由**"，然后单击 "**测试语音路由**"。

4.  在 "**测试语音路由**" 页面上，单击 "**新建**" 以创建新的测试用例。

5.  在 "**名称**" 中，为测试用例键入一个唯一名称。
    
    该名称必须在企业语音部署中的所有语音路由测试案例中是唯一的。 它的长度最多为32个字符，并且可以包含任何字母数字字符，除了反斜杠（\\）、句号（.）或下划线（\_）。

6.  在 "**要测试的已拨号码**" 中，键入要用于测试为此测试用例指定的路由配置的已拨号码。 根据拨号计划、路由和语音策略，此数字将标准化并显示为输出。

7.  在 "**拨号计划**" 列表中，选择运行测试时要使用的拨号计划。 默认值为全局拨号计划。

8.  在 "**语音策略**" 列表中，选择运行测试时要使用的语音策略。 默认值为全局语音策略。

9.  在 "**预期翻译**" 中，按照你希望在翻译后查看的格式键入电话号码。 这是在所选拨号计划中匹配的第一个规范化规则之后，你正在测试的电话号码的值。 当你运行测试用例时，如果你测试的数字未导致**预期转换**中的值，则测试失败。

10. 可选在 "**预期的 PSTN 使用情况**" 列表中，你可以选择你希望在运行测试用例时使用的公共交换电话网络（PSTN）使用记录（基于指定的拨号计划和语音策略）。 如果使用不同的 PSTN 使用记录，测试将失败。

11. 可选在 "**预期的路由**" 列表中，你可以根据指定的拨号计划和语音策略选择你希望在运行测试用例时使用的语音路线。 如果使用不同的语音路由，测试将失败。

12. 可选单击 "**运行**" 以运行测试用例。 结果将显示在页面的右侧面板中。

13. 单击“**确定**”。

14. 单击“提交”****，然后单击“全部提交”****。
    
    <div>
    

    > [!NOTE]  
    > 创建语音路由测试用例时，必须运行 "<STRONG>全部提交</STRONG>" 命令以发布配置更改。 有关详细信息，请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。

    
    </div>
    
    如果测试中使用的拨号计划规范化以加号（例如 + 12065551219）开头的电话号码，则该计划可能会导致语音路由测试失败。 （拨号计划和语音路由将正常工作; 事实上，CsDialPlan 将成功。 但是，语音路由测试可能失败。）当测试语音路线时，请注意这一点。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中导出语音路由测试用例](lync-server-2013-export-voice-routing-test-cases.md)  
[在 Lync Server 2013 中导入语音路由测试用例](lync-server-2013-import-voice-routing-test-cases.md)  


[在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)  
[在 Lync Server 2013 中配置语音策略、PSTN 使用记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

