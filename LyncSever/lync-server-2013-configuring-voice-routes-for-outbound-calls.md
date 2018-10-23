---
title: Lync Server 2013：配置出站呼叫的语音路由
TOCTitle: 配置出站呼叫的语音路由
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425890(v=OCS.15)
ms:contentKeyID: 49312566
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置出站呼叫的语音路由

 

_**上一次修改主题：** 2012-11-01_

Lync Server 2013 语音路由将目标电话号码与一个或多个公用电话交换网 (PSTN) 网关或 SIP 中继以及一个或多个 PSTN 用法记录相关联。

**使用 Lync Server 控制面板 查看语音路由**

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  单击“语音路由”。

3.  单击“路由”。

4.  双击语音路由以查看语音路由列表中的其他属性，或选择路由并单击“编辑”。然后单击“显示详细信息”。
    
    > [!NOTE]  
    > 一次只能查看一个路由的详细信息。
    


**使用 Windows PowerShell 查看语音路由**

  - 启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。 语音路由可以使用 Windows PowerShell 和 **Get-CsVoiceRoute** cmdlet 查看。此 cmdlet 可以从 Lync Server 2013 命令行管理程序 或 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。
    
    若要查看有关您所有语音路由的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsVoiceRoute
    
    这将返回与以下类似的信息：
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

> [!NOTE]  
> 有关详细信息，请参阅规划文档中的 <a href="lync-server-2013-voice-routes.md">Lync Server 2013 中的语音路由</a>。



## 本部分内容

  - [在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)

  - [在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中管理语音路由](lync-server-2013-managing-voice-routing.md)

