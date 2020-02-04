---
title: Lync Server 2013：运行非正式的语音路由测试
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f916de228545a560c94bc45ea0a774ccc538c60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>在 Lync Server 2013 中运行非正式的语音路由测试

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-08-07_

在创建实际测试用例之前，可以使用 "**创建语音路由测试事例信息**" 对话框来运行非正式测试。 如果对测试结果感到满意，则可以选择将其另存为正式测试用例。

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>运行非正式的语音路由测试

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**语音路由**"，然后单击 "**测试语音路由**"。

4.  在 "**测试语音路由**" 页面上，单击 "**创建语音路由测试案例信息**"。

5.  在 "已**拨号码**" 字段中，键入要用于此测试的电话号码。 此数字将规范化并显示在 "**结果**" 窗格的 "**正常化的数字**" 字段中。

6.  在 "**拨号计划**" 列表中，选择用于测试所拨号码的拨号计划。 默认值为全局拨号计划。
    
    运行测试时，此拨号计划中与已拨号码匹配的第一个规范化规则将显示在 "**结果**" 窗格的 "**规范化规则**" 字段中。

7.  在 "**语音策略**" 列表中，选择用于测试所拨号码的语音策略。 默认值为全局语音策略。
    
    运行测试时，此语音策略中第一个匹配的 PSTN 使用记录将显示在 "**结果**" 窗格的**第一个 PSTN 使用**字段中。 此外，与此 PSTN 使用记录关联的第一个匹配的语音路由将显示在**第一个路由**字段中。

8.  可选如果要针对分配给特定用户的语音策略测试所拨号码，请选中 "**根据用户填充**" 复选框。
    
    1.  单击 "**浏览**" 以显示 "**选择企业语音用户**" 对话框。
    
    2.  单击 "**查找**" 以显示已启用企业语音的用户的列表。
    
    3.  双击要用于此测试的已分配语音策略的用户名称。 此时，"**策略**" 字段将使用分配给所选用户的语音策略进行填充。
    
    运行测试时，此语音策略中的第一个匹配公共交换电话网络（PSTN）使用记录将显示在 "**结果**" 窗格的**第一个 PSTN 使用**字段中。 此外，与此 PSTN 使用记录关联的第一个匹配的语音路由将显示在**第一个路由**字段中。

9.  单击 "**运行**" 以运行测试用例。 结果将显示在对话框的右侧面板中。

10. 可选单击 "**另存为**"，如果要将此测试配置另存为正式测试用例。
    
    1.  在 "**保存语音路由测试用例信息**" 对话框的 "**名称**" 字段中，键入测试用例的唯一名称。
        
        该名称必须在企业语音部署中的所有语音路由测试案例中是唯一的。 它的长度最多为32个字符，并且可以包含任何字母数字字符，除了反斜杠（\\）、句号（.）或下划线（\_）。
    
    2.  请注意，"**保存语音路由测试事例信息**" 对话框中的 "剩余" 字段是只读的，并从非正式测试配置*和*结果中预填充。 验证这是否是要为测试用例保存的配置。
        
        <div>
        

        > [!NOTE]  
        > 来自测试结果的值用于在 "<STRONG>保存语音路由测试事例信息</STRONG>" 对话框中预填充字段，如下所示： 
        > <UL>
        > <LI>
        > <P><STRONG>所需翻译</STRONG>已预填充为 "<STRONG>规范化数字</STRONG>" 字段中的值。</P>
        > <LI>
        > <P><STRONG>预期的路线</STRONG>已预填充<STRONG>第一条路线</STRONG>字段中的值。</P>
        > <LI>
        > <P><STRONG>预期的 pstn 使用记录</STRONG>已预填充了<STRONG>第一个 pstn 使用</STRONG>字段中的值。</P></LI></UL>如果在测试运行期间找不到任何这些值的匹配项，则 "<STRONG>保存语音路由测试事例信息</STRONG>" 对话框中的相应字段为空。

        
        </div>
    
    3.  单击 **"确定"** 保存测试用例，或单击 "**取消**" 以返回到 "**查看语音路由测试事例信息**" 对话框，以便在保存之前进一步开发测试。

11. 单击“提交”****，然后单击“全部提交”****。
    
    <div>
    

    > [!NOTE]  
    > 创建语音路由测试用例时，必须运行 "<STRONG>全部提交</STRONG>" 命令以发布测试用例。 有关详细信息，请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建语音路由测试用例](lync-server-2013-create-a-voice-routing-test-case.md)  
[在 Lync Server 2013 中运行语音路由测试案例](lync-server-2013-run-voice-routing-test-cases.md)  
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

