---
title: Lync Server 2013：运行语音路由测试用例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df0a5ea6da9fad7f6a7e242bb522c493962fc603
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>在 Lync Server 2013 中运行语音路由测试用例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-24_

您可以运行语音路由测试用例套件中的所有测试用例，也可以运行一个或多个选定的测试用例。

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>运行所有语音路由测试用例

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“语音路由”****，然后单击“测试语音路由”****。

4.  在“测试语音路由”**** 页上，单击“操作”****，然后单击“运行所有”****。
    
    “通过/失败”**** 列中会显示每个测试用例的通过状态或失败状态。如果测试用例尚未运行，则“通过/失败”**** 列中会显示 N/A。

5.  （可选）要查看每个测试用例的详细结果，请双击该测试用例的名称。结果会显示在“编辑测试用例”**** 页右侧的阴影区域中：
    
    1.  **测试结果：** 测试用例运行的整体 pass 或 fail 状态。
    
    2.  **规范化规则：** 为此测试用例选择的拨号计划中的第一个规范化规则与所拨打的号码相匹配（"**要测试的数字**" 字段中的值）。
    
    3.  **正常化的数字：** 规范化规则翻译后拨叫的号码的值。
    
    4.  **第一个 PSTN 用法：** 为此测试用例选择的语音策略中的第一个公用电话交换网（PSTN）用法记录与所拨打的号码匹配。
    
    5.  **第一个路由：** 第一个与所拨打的号码相匹配的 PSTN 用法记录中的第一个语音路由。
        
        <div>
        

        > [!NOTE]  
        > 在语音路由测试用例配置中，“预期 PSTN 用法记录”<STRONG></STRONG>和“预期路由”<STRONG></STRONG>字段是可选的。如果测试用例不指定这些值，则测试结果中对应的字段为空。

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>运行一个或多个所选语音路由测试用例

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“语音路由”****，然后单击“测试语音路由”****。

4.  在“测试语音路由”**** 页上，单击要运行的测试用例的名称。

5.  在“操作”**** 菜单上，单击“运行所选项”****。
    
    “通过/失败”**** 列中会显示每个测试用例的通过状态或失败状态。如果测试用例尚未运行，则“通过/失败”**** 列中会显示 N/A。

6.  （可选）要查看每个测试用例的详细结果，请双击该测试用例的名称。结果会显示在“编辑测试用例”**** 页右侧的阴影区域中：
    
    1.  **测试结果：** 测试用例运行的整体 pass 或 fail 状态。
    
    2.  **规范化规则：** 为此测试用例选择的拨号计划中的第一个规范化规则与所拨打的号码相匹配（"**要测试的数字**" 字段中的值）。
    
    3.  **正常化的数字：** 规范化规则翻译后拨叫的号码的值。
    
    4.  **第一个 PSTN 用法：** 为此测试用例选择的语音策略中的第一个 PSTN 用法记录与所拨打的号码相匹配。
    
    5.  **第一个路由：** 第一个与所拨打的号码相匹配的 PSTN 用法记录中的第一个语音路由。
        
        <div>
        

        > [!NOTE]  
        > 在语音路由测试用例配置中，“预期 PSTN 用法记录”<STRONG></STRONG>和“预期路由”<STRONG></STRONG>字段是可选的。如果测试用例不指定这些值，则测试结果中对应的字段为空。

        
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

