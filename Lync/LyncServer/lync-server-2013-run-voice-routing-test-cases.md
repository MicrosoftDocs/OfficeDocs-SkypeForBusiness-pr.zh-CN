---
title: 在 Lync Server 2013 中运行语音路由测试用例
TOCTitle: 在 Lync Server 2013 中运行语音路由测试用例
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413068(v=OCS.15)
ms:contentKeyID: 49314837
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中运行语音路由测试用例

 

_**上一次修改主题：** 2013-02-24_

您可以在语音路由测试用例包中运行所有测试用例，也可以运行一个或多个所选测试用例。

## 运行所有语音路由测试用例

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”，然后单击“测试语音路由”。

4.  在“测试语音路由”页上，单击“操作”，然后单击“运行所有”。
    
    “通过/失败”列中会显示每个测试用例的通过状态或失败状态。如果测试用例尚未运行，则“通过/失败”列中会显示 N/A。

5.  （可选）要查看每个测试用例的详细结果，请双击该测试用例的名称。结果会显示在“编辑测试用例”页右侧的阴影区域中：
    
    1.  **测试结果：** 测试用例运行的整体通过或失败状态。
    
    2.  **规范化规则：** 拨号计划中选定用于匹配已拨号码（“要测试的号码”字段中的值）的测试用例的第一个规范化规则。
    
    3.  **规范化号码：** 已拨号码经规范化规则转换后的值。
    
    4.  **第一个公用电话交换网 (PSTN) 用法：** 语音策略中选定用于匹配已拨号码的测试用例的第一个 PSTN 用法记录。
    
    5.  **第一个路由：** 第一个 PSTN 用法记录中匹配已拨号码的第一个语音路由。
        
        > [!NOTE]  
		> 在语音路由测试用例配置中，“预期 PSTN 用法记录”和“预期路由”字段是可选的。如果测试用例不指定这些值，则测试结果中对应的字段为空。
        


## 运行一个或多个所选语音路由测试用例

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”，然后单击“测试语音路由”。

4.  在“测试语音路由”页上，单击要运行的测试用例的名称。

5.  在“操作”菜单上，单击“运行所选项”。
    
    “通过/失败”列中会显示每个测试用例的通过状态或失败状态。如果测试用例尚未运行，则“通过/失败”列中会显示 N/A。

6.  （可选）要查看每个测试用例的详细结果，请双击该测试用例的名称。结果会显示在“编辑测试用例”页右侧的阴影区域中：
    
    1.  **测试结果：** 测试用例运行的整体通过或失败状态。
    
    2.  **规范化规则：** 拨号计划中选定用于匹配已拨号码（“要测试的号码”字段中的值）的测试用例的第一个规范化规则。
    
    3.  **规范化号码：** 已拨号码经规范化规则转换后的值。
    
    4.  **第一个 PSTN 用法：** 语音策略中选定用于匹配已拨号码的测试用例的第一个 PSTN 用法记录。
    
    5.  **第一个路由：** 第一个 PSTN 用法记录中匹配已拨号码的第一个语音路由。
        
        > [!NOTE]  
		> 在语音路由测试用例配置中，“预期 PSTN 用法记录”和“预期路由”字段是可选的。如果测试用例不指定这些值，则测试结果中对应的字段为空。
        


## 另请参阅

#### 其他资源

[在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)  
[在 Lync Server 2013 中运行语音路由测试](lync-server-2013-running-voice-routing-tests.md)

