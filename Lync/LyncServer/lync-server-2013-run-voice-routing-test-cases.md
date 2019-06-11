---
title: 'Lync Server 2013: 运行语音路由测试案例'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cded8f3bf44388103ccf5a33507973817de45ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>在 Lync Server 2013 中运行语音路由测试案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-24_

你可以在你的语音路由测试案例套件中运行所有测试用例, 也可以运行一个或多个选定的测试用例。

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>运行所有语音路由测试案例

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**语音路由**", 然后单击 "**测试语音路由**"。

4.  在 "**测试语音路由**" 页面上, 单击 "**操作**", 然后单击 "**全部运行**"。
    
    每个测试用例的 "通过" 或 "失败" 状态显示在 "**通过/失败**" 列中。 如果测试用例尚未运行, 则 "**通过/失败**" 列中将显示 "N/a"。

5.  可选若要查看每个测试用例的详细结果, 请双击测试用例名称。 结果将显示在**编辑测试用例**页面右侧的着色区域中:
    
    1.  **测试结果:** 测试用例运行的整体传递或失败状态。
    
    2.  **规范化规则:** 为此测试用例选择的拨号计划中的第一个规范化规则与已拨打的号码相匹配 ("**要测试的号码**" 字段中的值)。
    
    3.  **规范化数字:** 规范化规则翻译后拨叫的号码的值。
    
    4.  **第一 PSTN 使用:** 为此测试用例选择的、与所拨号码匹配的语音策略中的第一个公共交换电话网络 (PSTN) 使用记录。
    
    5.  **第一条路线:** 第一条在第一条 PSTN 使用记录中与所拨号码相匹配的第一个语音路线。
        
        <div>
        

        > [!NOTE]  
        > "<STRONG>预期 PSTN 使用记录</STRONG>" 和 "<STRONG>预期路由</STRONG>" 字段在语音路由测试案例配置中是可选的。 如果测试用例未指定这些值, 则测试结果中的对应字段将为空。

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>运行一个或多个所选的语音路由测试案例

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**语音路由**", 然后单击 "**测试语音路由**"。

4.  在 "**测试语音路由**" 页面上, 单击要运行的测试用例的名称。

5.  在 "**操作**" 菜单上, 单击 "**运行所选**"。
    
    每个测试用例的 "通过" 或 "失败" 状态显示在 "**通过/失败**" 列中。 如果测试用例尚未运行, 则 "**通过/失败**" 列中将显示 "N/a"。

6.  可选若要查看每个测试用例的详细结果, 请双击测试用例名称。 结果将显示在**编辑测试用例**页面右侧的着色区域中:
    
    1.  **测试结果:** 测试用例运行的整体传递或失败状态。
    
    2.  **规范化规则:** 为此测试用例选择的拨号计划中的第一个规范化规则与已拨打的号码相匹配 ("**要测试的号码**" 字段中的值)。
    
    3.  **规范化数字:** 规范化规则翻译后拨叫的号码的值。
    
    4.  **第一 PSTN 使用:** 为此测试用例选择的、与所拨号码匹配的语音策略中的第一条 PSTN 使用记录。
    
    5.  **第一条路线:** 第一条在第一条 PSTN 使用记录中与所拨号码相匹配的第一个语音路线。
        
        <div>
        

        > [!NOTE]  
        > "<STRONG>预期 PSTN 使用记录</STRONG>" 和 "<STRONG>预期路由</STRONG>" 字段在语音路由测试案例配置中是可选的。 如果测试用例未指定这些值, 则测试结果中的对应字段将为空。

        
        </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)  
[在 Lync Server 2013 中运行语音路由测试](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

