---
title: Lync Server 2013：修改拨号计划
TOCTitle: 修改拨号计划
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412797(v=OCS.15)
ms:contentKeyID: 49313896
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中修改拨号计划

 

_**上一次修改主题：** 2012-11-01_

要修改现有拨号计划，请执行以下过程中的步骤。如果要创建新拨号计划，请参阅 [在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。

## 修改拨号计划

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”，然后单击“拨号计划”。

4.  在“拨号计划”页上，双击某个拨号计划名称。
    
    > [!NOTE]  
    > 拨号计划的作用域和名称是在创建该拨号计划时设置的，且不能更改。
    


5.  （可选）在“编辑拨号计划”中，编辑“简单名称”字段，该字段会预填充“名称”字段中显示的相同名称，以指定反映应用该拨号计划的站点、服务或用户的更具描述性的名称。
    
    > [!IMPORTANT]  
    > 此“简单名称”必须在 Lync Server 2013 部署中的所有拨号计划中是唯一的。该名称不能超过 256 个 Unicode 字符，每个 Unicode 字符可以是字母或数字字符、连字符 (-)、句点 (.)、加号 (+) 或下划线 (_)。<br />
    > “简单名称”字段中不允许使用空格。


6.  （可选）在“说明”字段中，键入有关拨号计划的描述性信息。

7.  （可选）如果要将此拨号计划用作电话拨入式访问号码的区域，请指定“电话拨入式会议区域”。如果不希望将此拨号计划用于电话拨入式访问号码，请将此字段留空。
    
    > [!NOTE]  
    > 电话拨入式会议区域需要将电话拨入式会议访问号码与一个或多个拨号计划相关联。
    


8.  （可选）在“外部访问前缀”字段中，指定一个值，该值仅在用户需要拨打一个或多个附加的前导数字（例如 9）以拨通外线时使用。键入的前缀值不得超过 4 个字符（即 \#、\* 和 0-9）。
    
    > [!NOTE]  
    > 如果指定了外部访问前缀，则不需要创建新的规范化规则来满足前缀。
    


9.  为拨号计划关联并配置规范化规则：
    
      - 要从 企业语音部署中提供的所有规范化规则列表中选择一个或多个规则，请单击“选择”。在“选择规范化规则”对话框中，突出显示要与拨号计划关联的规则，然后单击“确定”。
    
      - 要定义新的规范化规则并将其与拨号计划相关联，请单击“新建”。有关定义新规则的详细信息，请参阅[在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)。
    
      - 要编辑已经与拨号计划关联的规范化规则，请突出显示相应的规则名称，然后单击“显示详细信息”。有关编辑规则的详细信息，请参阅[在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)。
    
      - 要复制现有规范化规则以作为定义新规则的起点，请突出显示相应的规则名称，单击“复制”，然后单击“粘贴”。有关编辑所复制规则的详细信息，请参阅[在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)。
    
      - 要从拨号计划中删除某个规范化规则，请突出显示相应的规则名称，然后单击“删除”。
    
    > [!NOTE]  
    > 每个拨号计划都必须至少有一个关联的规范化规则。有关如何确定拨号计划所需的全部规范化规则的详细信息，请参阅规划文档中的 <a href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的拨号计划和规范化规则</a>。
    


10. 验证拨号计划的规范化规则是否已按正确顺序排列。要更改规则在列表中的位置，请突出显示相应的规则名称，然后单击向上箭头或向下箭头。
    
    > [!IMPORTANT]  
    > Lync Server 按照从上到下的顺序遍历规范化规则列表，并使用第一个与拨打号码相匹配的规则。如果要配置拨号计划以使拨打号码可以匹配多个规范化规则，请确保限制较严格的规则排在限制较宽松的规则上方。<br />
    > 默认“Keep All”规范化规则 <strong>^(\d{11})$</strong> 匹配任意 11 位号码。例如，如果添加与以 1425 开头的 11 位号码相匹配的规范化规则，请确保“Keep All”排在更加严格的 <strong>^(1425\d{7})$</strong> 规则的下面。


11. （可选）输入一个号码来测试拨号计划，然后单击“执行”。测试结果会显示在“输入要测试的号码”下。
    
    > [!NOTE]  
    > 您可以保存尚未通过测试的拨号计划，并在稍后对其进行重新配置。有关详细信息，请参阅 <a href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</a>。
    


12. 单击“确定”。

13. 在“拨号计划”页上，单击“提交”，然后单击“全部提交”。
    
    > [!NOTE]  
    > 任何时候创建或修改拨号计划，都必须运行“全部提交”命令以发布配置更改。有关详细信息，请参阅操作文档中的 <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">在 Lync Server 2013 中发布对语音路由配置所做的待处理更改</a>。
    


## 另请参阅

#### 任务

[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)  
[在 Lync Server 2013 中发布对语音路由配置所做的待处理更改](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### 其他资源

[在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)

