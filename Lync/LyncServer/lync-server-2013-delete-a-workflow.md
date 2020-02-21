---
title: Lync Server 2013：删除工作流
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1f3265591b1beb7180864b8e3a613989dfca397
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>在 Lync Server 2013 中删除工作流

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

使用下列过程之一删除工作流。

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>使用 Lync Server 控制面板删除工作流

1.  以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“响应组”****，然后单击“工作流”****。

4.  在“工作流”**** 页上，单击“创建或编辑工作流”****。

5.  在“选择服务”**** 搜索字段中，键入承载要删除的工作流的 **ApplicationServer** 服务的部分或全部名称。

6.  在服务列表中，单击所需的服务，然后单击 **“确定”**。
    
    <div>
    

    > [!NOTE]  
    > 将打开 "响应组配置工具" 网页。 您还可以通过连接到<STRONG>&lt;https://webPoolFqdn&gt;/RgsConfig</STRONG>直接从 Web 浏览器打开响应组配置工具网页。

    
    </div>

7.  在“管理现有工作流”**** 下，找到要删除的工作流，然后在“操作”**** 下，单击“删除”****。

8.  单击“是”****。

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>使用 Windows PowerShell 删除工作流

1.  以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在命令行中运行：
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    例如：
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

