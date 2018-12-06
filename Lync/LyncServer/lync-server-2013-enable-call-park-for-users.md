---
title: Lync Server 2013：为用户启用呼叫寄存
TOCTitle: 为用户启用呼叫寄存
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398753(v=OCS.15)
ms:contentKeyID: 49313619
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为用户启用呼叫寄存

 

_**上一次修改主题：** 2012-09-11_

用户在语音策略中启用 呼叫寄存后，才能寄存呼叫或取回寄存的呼叫。

> [!NOTE]  
> 默认情况下，对所有用户禁用 呼叫寄存。



可以在全局作用域、站点作用域或用户作用域启用 呼叫寄存。用户作用域优先于站点作用域，而站点作用域又优先于全局作用域。如果有多个语音策略，请检查所有要启用 呼叫寄存的策略，而不只是全局策略。

## 使用 Lync Server 控制面板为用户启用 呼叫寄存

1.  以 **RTCUniversalServerAdmins** 组成员或者 **CsVoiceAdministrator** 、 **CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”。

4.  单击“语音策略”选项卡。

5.  双击现有语音策略以打开“编辑语音策略”对话框。

6.  在“呼叫功能”下，选择“启用呼叫寄存”。

7.  单击“确定”保存语音策略。

## 使用 Cmdlet 为用户启用 呼叫寄存

1.  以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 管理角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    例如，为默认全局语音策略启用 呼叫寄存：
    
        Set-CsVoicePolicy -EnableCallPark $true

## 另请参阅

#### 任务

[在 Lync Server 2013 中创建语音策略和配置 PSTN 用法记录](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

