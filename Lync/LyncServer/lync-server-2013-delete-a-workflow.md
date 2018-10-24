---
title: 删除工作流
TOCTitle: 删除工作流
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520944(v=OCS.15)
ms:contentKeyID: 49311857
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除工作流

 

_**上一次修改主题：** 2012-11-01_

使用下列过程之一删除工作流。

## 使用 Lync Server 控制面板删除工作流

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“响应组”，然后单击“工作流”。

4.  在“工作流”页上，单击“创建或编辑工作流”。

5.  在“选择服务”搜索字段中，键入承载要删除的工作流的 **ApplicationServer** 服务的部分或全部名称。

6.  在服务列表中，单击所需的服务，然后单击“确定”。
    
    > [!NOTE]  
    > 此时将打开“响应组配置工具”网页。还可以直接在 Web 浏览器中通过连接到 <strong>https://<em>&lt;webPoolFqdn&gt;</em>/RgsConfig</strong> 打开“响应组配置工具”网页。
    


7.  在“管理现有工作流”下，找到要删除的工作流，然后在“操作”下，单击“删除”。

8.  单击“是”。

## 使用 cmdlet 删除工作流

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令行中运行：
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    例如：
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

