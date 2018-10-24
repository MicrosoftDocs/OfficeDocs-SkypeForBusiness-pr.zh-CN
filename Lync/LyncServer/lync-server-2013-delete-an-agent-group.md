---
title: 删除代理组
TOCTitle: 删除代理组
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182597(v=OCS.15)
ms:contentKeyID: 49314479
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除代理组

 

_**上一次修改主题：** 2012-11-01_

使用以下过程之一删除代理组。

## 使用 Lync Server 控制面板删除代理组

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“响应组”，然后单击“组”。

4.  在“响应组”页上的搜索字段中，键入要删除的代理组的全部或部分名称。

5.  在生成的列表中，单击要删除的组，再单击“编辑”，然后单击“删除”。

6.  单击“确定”。

## 使用 cmdlet 删除代理组

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令行中运行：
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    例如：
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

## 另请参阅

#### 任务

[在 Lync Server 2013 中创建或修改代理组](lync-server-2013-create-or-modify-an-agent-group.md)  

#### 其他资源

[Remove-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsRgsAgentGroup)

