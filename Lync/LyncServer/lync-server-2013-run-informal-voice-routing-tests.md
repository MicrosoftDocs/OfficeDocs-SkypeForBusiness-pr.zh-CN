---
title: 在 Lync Server 2013 中运行非正式语音路由测试
TOCTitle: 在 Lync Server 2013 中运行非正式语音路由测试
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399049(v=OCS.15)
ms:contentKeyID: 49314618
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中运行非正式语音路由测试

 

_**上一次修改主题：** 2012-08-07_

在创建实际测试用例之前，可以使用“创建语音路由测试用例信息”对话框运行非正式的测试。对测试结果感到满意后，可以通过相应的选项将其保存为正式测试用例。

## 运行非正式语音路由测试

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”，然后单击“测试语音路由”。

4.  在“测试语音路由”页上，单击“创建语音路由测试用例信息”。

5.  在“拨打的号码”字段中，键入要用于此测试的电话号码。将对该号码进行规范化处理，并显示在“结果”窗格的“规范化号码”字段中。

6.  在“拨号计划”列表中，选择要用于测试已拨号码的拨号计划。默认为全局拨号计划。
    
    运行测试时，该拨号计划中第一个匹配已拨号码的规范化规则将显示在“结果”窗格的“规范化规则”字段中。

7.  在“语音策略”列表中，选择要用于测试已拨号码的语音策略。默认为全局语音策略。
    
    运行测试时，该语音策略中第一条匹配的 PSTN 用法记录将显示在“结果”窗格的“第一个 PSTN 用法”字段中。另外，与此 PSTN 用法记录关联的第一个匹配的语音路由将显示在“第一个路由”字段中。

8.  （可选）如果要根据分配给特定用户的语音策略测试已拨号码，请选中“从用户填充”复选框。
    
    1.  单击“浏览”以显示“选择企业语音用户”对话框。
    
    2.  单击“查找”以显示已启用企业语音的用户列表。
    
    3.  双击要将为其分配的语音策略用于该测试的用户名。现在“策略”字段中填充了分配给所选用户的语音策略。
    
    运行测试时，该语音策略中第一条匹配的公用电话交换网 (PSTN) 用法记录将显示在“结果”窗格的“第一个 PSTN 用法”字段中。另外，与此 PSTN 用法记录关联的第一个匹配的语音路由将显示在“第一个路由”字段中。

9.  单击“运行”以运行测试用例。结果显示在对话框的右侧面板中。

10. （可选）如果要将该测试配置保存为正式测试用例，单击“另存为”。
    
    1.  在“保存语音路由测试用例信息”对话框的“名称”字段中，为测试用例键入唯一的名称。
        
        此名称在企业语音部署中的所有语音路由测试用例中必须是唯一的。名称最多包含 32 个字符，可以包含任何数字字符，但反斜杠 (\\)、圆点 (.) 或下划线 (\_) 除外。
    
    2.  请注意，“保存语音路由测试用例信息”对话框中的其余字段都是只读字段，并且预填充非正式测试配置和结果。确认这是要为测试用例保存的配置。
        
        > [!NOTE]  
		> 测试结果中的值用于预填充“保存语音路由测试用例信息”对话框中的字段，如下所示：
        > <ul>
        > <li><p>“预期转换”使用“规范化号码”字段中的值进行预填充。</p></li>
        > <li><p>“预期路由”使用“第一个路由”字段中的值进行预填充。</p></li>
        > <li><p>“预期 PSTN 用法记录”使用“第一个 PSTN 用法”字段中的值进行预填充。</p></li>
        > </ul>
        > 如果在测试运行期间未找到上述任何值的匹配内容，“保存语音路由测试用例信息”对话框中的对应字段将为空。
        
    
    3.  单击“确定”保存测试用例，或单击“取消”返回“查看语音路由测试用例信息”对话框以在保存前进一步完善测试。

11. 单击“提交”，然后单击“全部提交”。
    
    > [!NOTE]  
	> 任何时候创建语音路由测试用例，都必须运行“全部提交”命令以发布测试用例。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">在 Lync Server 2013 中发布对语音路由配置所做的待处理更改</a>。
    


## 另请参阅

#### 任务

[在 Lync Server 2013 中创建语音路由测试用例](lync-server-2013-create-a-voice-routing-test-case.md)  
[在 Lync Server 2013 中运行语音路由测试用例](lync-server-2013-run-voice-routing-test-cases.md)  
[在 Lync Server 2013 中导出语音路由测试用例](lync-server-2013-export-voice-routing-test-cases.md)  
[在 Lync Server 2013 中导入语音路由测试用例](lync-server-2013-import-voice-routing-test-cases.md)  

#### 其他资源

[在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)  
[在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

