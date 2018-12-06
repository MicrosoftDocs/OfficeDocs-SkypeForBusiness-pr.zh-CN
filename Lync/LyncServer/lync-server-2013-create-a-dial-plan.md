---
title: Lync Server 2013：创建拨号计划
TOCTitle: 创建拨号计划
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398909(v=OCS.15)
ms:contentKeyID: 49314335
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建拨号计划

 

_**上一次修改主题：** 2013-10-24_

要创建新的拨号计划，请执行以下过程中的步骤。如果要编辑拨号计划，请参阅 [在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)。

## 创建拨号计划

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”，然后单击“拨号计划”。

4.  在“拨号计划”页上，单击“新建”，然后为拨号计划选择作用域：
    
      - “站点拨号计划”将应用于整个站点，分配给用户拨号计划的用户或组除外。如果选择“Site”作为拨号计划的作用域，则必须从“选择站点”对话框中选择站点。如果已经为站点创建了拨号计划，则该站点不会显示在“选择站点”对话框中。
    
      - “池拨号计划”可以应用于公用电话交换网 (PSTN) 网关或注册器。如果选择“池”作为拨号计划的作用域，则从“选择服务”对话框中选择 PSTN 网关或注册器。如果已经为服务（PSTN 网关或注册器）创建了拨号计划，则该服务不会显示在列表中。
    
      - “用户拨号计划”可以应用于指定的用户或组。
    
    > [!NOTE]  
    > 选择拨号计划作用域后，就无法更改。
    


5.  如果要创建用户拨号计划，请在“新建拨号计划”对话框的“名称”字段中输入描述性名称。保存此名称后，就无法更改。
    
    > [!NOTE]  
    > 对于站点拨号计划，“名称”字段会使用站点名称预先填充，且不能更改。<br />
    对于池拨号计划，“名称”字段会使用 PSTN 网关或注册器名称预先填充，且不能更改。
    


6.  “简单名称”字段会使用与“名称”字段中显示的相同名称预先填充。您可以选择编辑该字段来指定描述性更强的名称，以反映应用该拨号计划的站点、服务或用户。
    
    > [!IMPORTANT]  
    > 此“简单名称”必须在 Lync Server 部署中的所有拨号计划中是唯一的。该名称不能超过 256 个 Unicode 字符，每个 Unicode 字符可以是字母或数字字符、连字符 (-)、句点 (.) 或下划线 (_)。<br />
    > <strong>不支持的</strong>字符包括空格和 RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt) 中定义的保留字符。“简单名称”中<strong>不支持的</strong>保留字符包括：<br />
    > &quot;;&quot; &quot;/&quot; &quot;?&quot; &quot;:&quot; &quot;@&quot; &quot;&amp;&quot; &quot;=&quot; &quot;+&quot; &quot;$&quot; &quot;,&quot;



7.  （可选）在“说明”字段中，您可以键入有关拨号计划的其他描述性信息。

8.  （可选）如果要将此拨号计划用作电话拨入式访问号码的区域，请指定“电话拨入式会议区域”。如果不希望将此拨号计划用于电话拨入式访问号码，请将此字段留空。
    
    > [!NOTE]  
    > 电话拨入式会议区域需要将电话拨入式会议访问号码与一个或多个拨号计划相关联。
    


9.  （可选）在“外部访问前缀”字段中，指定一个值，该值仅在用户需要拨打一个或多个附加的前导数字（例如 9）以拨通外线时使用。键入的前缀值不得超过 4 个字符（\#、\* 和 0-9）。
    
    > [!NOTE]  
    > 如果指定了外部访问前缀，则不需要创建新的规范化规则来满足前缀。
    


10. 按如下所示为拨号计划关联并配置规范化规则：
    
      - 要从企业语音部署中提供的所有规范化规则列表中选择一个或多个规则，请单击“选择”。在“选择规范化规则”中，突出显示要与拨号计划关联的规则，然后单击“确定”。
    
      - 要定义新的规范化规则并将其与拨号计划相关联，请单击“新建”。有关定义新规则的详细信息，请参阅[在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)。
    
      - 要编辑已经与拨号计划关联的规范化规则，请突出显示相应的规则名称，然后单击“显示详细信息”。有关编辑规则的详细信息，请参阅[在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)。
    
      - 要复制现有规范化规则以作为定义新规则的起点，请突出显示相应的规则名称，单击“复制”，然后单击“粘贴”。有关编辑所复制规则的详细信息，请参阅[在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)。
    
      - 要从拨号计划中删除某个规范化规则，请突出显示相应的规则名称，然后单击“删除”。
    
    > [!NOTE]  
    > 每个拨号计划都必须至少有一个关联的规范化规则。有关如何确定拨号计划所需的全部规范化规则的信息，请参阅规划文档中的 <a href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的拨号计划和规范化规则</a>。
    


11. 验证拨号计划的规范化规则是否已按正确顺序排列。要更改规则在列表中的位置，请突出显示相应的规则名称，然后单击向上箭头或向下箭头。
    
    > [!IMPORTANT]  
    > Lync Server 按照从上到下的顺序遍历规范化规则列表，并使用第一个与拨打号码相匹配的规则。如果要配置拨号计划以使拨打号码可以匹配多个规范化规则，请确保限制较严格的规则排在限制较宽松的规则上方。<br />
    > 默认“全部保留”规范化规则 <strong>^(\d{11})$</strong> 匹配任意 11 位号码。例如，如果添加与以 1425 开头的 11 位号码相匹配的规范化规则，则请确保“全部保留”排在更加严格的 <strong>^(1425\d{7})$</strong> 规则的下面。


12. （可选）输入一个号码来测试拨号计划，然后单击“执行”。测试结果会显示在“输入要测试的号码”下。
    
    > [!NOTE]  
    > 您可以保存尚未通过测试的拨号计划，并在稍后对其进行重新配置。有关详细信息，请参阅 <a href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</a>。
    


13. 单击“确定”。

14. 在“拨号计划”页上，单击“提交”，然后单击“全部提交”。
    
    > [!NOTE]  
    > 任何时候创建拨号计划，都必须运行“全部提交”命令以发布配置更改。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">在 Lync Server 2013 中发布对语音路由配置所做的待处理更改</a>。
    


## 另请参阅

#### 任务

[在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)  
[在 Lync Server 2013 中发布对语音路由配置所做的待处理更改](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### 其他资源

[在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)

