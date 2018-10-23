---
title: Lync Server 2013：使用“构建规范化规则”创建或修改规范化规则
TOCTitle: 使用“构建规范化规则”创建或修改规范化规则
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399036(v=OCS.15)
ms:contentKeyID: 49314586
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中使用“构建规范化规则”创建或修改规范化规则

 

_**上一次修改主题：** 2012-11-01_

如果要在 Lync Server 控制面板中创建和修改规范化规则，请执完成以下步骤。或者，如果要手动创建或修改规范化规则，请参阅 [在 Lync Server 2013 中手动创建或修改规范化规则](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)。

## 使用“建立规范化规则”定义规则

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  （可选）执行 [在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)中的前 11 个步骤或 [在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)中的前 10 个步骤。

4.  在“新建规范化规则”或“编辑规范化规则”的“名称”中，键入描述要进行规范化的号码模式的名称（例如， **5DigitExtension** ）。

5.  （可选）在“描述”中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。

6.  在“建立规范化规则”的以下字段中输入值：
    
      - **起始数字** （可选）指定要使模式与之匹配的拨打号码的前导数字。例如，如果要使模式与以 425 开头的拨打号码匹配，则键入 **425** 。
    
      - **长度** 指定匹配模式中的数字位数，并选择希望模式匹配的拨打号码是必须具有此准确长度、至少具有此长度还是可以具有任何长度。
    
      - **要删除的数字** （可选）指定要从希望模式与之匹配的拨打号码中删除的起始数字的位数。
    
      - **要添加的数字** （可选）指定要添加到希望模式与之匹配的拨打号码中的数字。
    
    这些字段中输入的值将反映在“要匹配的模式”和“转换规则”中。例如，如果将“起始数字”留空，在“长度”字段中键入 **7** 并选择“完全匹配”，然后在“要删除的数字”中指定 **0** ，则在“要匹配的模式”中生成的正则表达式如下所示：
    
    **^(\\d{7})$**

7.  在“转换规则”中，指定转换后的 E.164 电话号码格式的模式，如下所示：
    
      - 代表匹配模式中指定的号码位数的值。例如，如果匹配模式是 **^(\\d{7})$** ，则转换规则中的 **$1** 代表 7 位拨打号码。
    
      - （可选）在“要添加的数字”字段中键入值，指定要附加到转换后的号码前面的数字（例如 **+1425** ）。
    
    例如，如果“要匹配的模式”包含 **^(\\d{7})$** 作为拨打号码的模式，且“转换规则”包含 **+1425$1** 作为 E.164 电话号码的模式，则该规则会将 5550100 规范化为 +14255550100。

8.  （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”。

9.  （可选）输入一个号码以测试规范化规则，然后单击“执行”。测试结果会显示在“输入要测试的号码”下。
    
    > [!NOTE]  
    > 您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。有关详细信息，请参阅 <a href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</a>。
    


10. 单击“确定”保存规范化规则。

11. 单击“确定”保存拨号计划。

12. 在“拨号计划”页上，单击“提交”，然后单击“全部提交”。
    
    > [!NOTE]  
    > 无论何时创建或更改规范化规则，都必须运行“全部提交”命令以发布配置更改。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">在 Lync Server 2013 中发布对语音路由配置所做的待处理更改</a>。
    


## 另请参阅

#### 任务

[在 Lync Server 2013 中手动创建或修改规范化规则](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)  
[在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)  
[在 Lync Server 2013 中发布对语音路由配置所做的待处理更改](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### 其他资源

[在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)

