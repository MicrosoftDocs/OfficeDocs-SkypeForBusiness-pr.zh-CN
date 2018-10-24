---
title: 在 Lync Server 2013 中创建或修改会议配置设置的集合
TOCTitle: 在 Lync Server 2013 中创建或修改会议配置设置的集合
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49888616
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或修改会议配置设置的集合

 

_**上一次修改主题：** 2013-02-23_

可以使用“会议配置”页上的设置来定义与会体验的各种特性。默认情况下，全局设置定义与会体验。还可以创建站点级别和池级别的与会设置。如果创建池级别的设置，则这些设置将应用于由该池托管的所有会议。如果未创建池级别的设置，则应用站点级别的设置（如果存在）。如果未定义站点级别的设置，则全局设置将应用于所有会议。

## 创建新的与会设置

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后单击“会议配置”。

4.  在“会议配置”页上，单击“新建”，然后执行以下操作之一：
    
      - 要创建站点级别的策略，请单击“站点配置”。在“选择站点”搜索字段中，键入要为其定义与会设置的站点的全部或部分名称。在结果站点列表中，单击所需的站点，然后单击“确定”。
    
      - 要创建池级别的策略，请单击“池配置”。在“选择服务”搜索字段中，键入要为其定义与会设置的池服务的全部或部分名称。在结果服务列表中，单击所需的池，然后单击“确定”。

5.  要路由从公用电话交换网 (PSTN) 通过会议厅拨入的参与者，请清除“PSTN 呼叫者绕过休息室”复选框。默认情况下，从 PSTN 拨入的参与者可直接参加会议。

6.  要配置会议的演示者，请在“指定为演示者”中执行下列操作之一：
    
      - 要禁止组织者以外的任何人成为演示者，请单击“无”。
    
      - 要只允许组织成员参与者成为演示者，请单击“公司”。这是默认设置。
    
      - 要允许任何参与者成为演示者，请单击“所有人”。

7.  要让组织者在安排会议时选择会议类型，请清除“默认分配的会议类型”复选框。默认情况下，会自动分配会议类型。

8.  要阻止自动允许匿名（未经身份验证）用户参加会议，请清除“默认允许匿名用户”复选框。默认情况下，自动允许匿名用户参加会议。

9.  要自定义发送给参与者的会议邀请，请执行以下操作。请注意，URL 和自定义页脚文本的最大长度为 1KB。除了“帮助 URL”外，如果不指定自定义的值，则它们不会包括在会议中。如果未包括自定义帮助 URL，将在邀请中显示 Lync 的默认帮助 URL。
    
      - 要自定义会议邀请中显示的徽标，请在“徽标 URL”中输入徽标的位置。
        
        > [!NOTE]  
		> 徽标必须是大小为 188 x 30 像素的 GIF 或 JPG 图像。
        
    
      - 要自定义会议邀请中显示的帮助文本，请在“帮助 URL”中输入帮助文本的位置。
    
      - 要自定义会议邀请中显示的法律文本，请在“法律文本 URL”中输入徽标的位置。
    
      - 要自定义会议邀请中显示的页脚文本，请在“自定义页脚文本”中输入文本。

10. 单击“提交”。

## 修改会议配置的现有集合

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后单击“会议配置”。

4.  在会议配置列表中，单击要更改的配置，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑会议配置”中，修改除配置名称外的任一配置设置，配置名称不能修改。

6.  单击“提交”。

## 使用 Windows PowerShell Cmdlet 创建新的会议配置设置

可以使用 Windows PowerShell 和 New-CsMeetingConfiguration cmdlet 创建会议配置设置（仅在网站范围）。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 创建使用默认值的会议配置设置

  - 以下命令为 Redmond 站点创建一组新的会议配置设置：
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的会议配置设置的所有属性将使用默认值。

## 在创建会议配置设置时更改属性值

  - 要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，要创建在默认情况下允许所有人以演示者身份加入会议的会议配置设置集合，请使用如下命令：
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

## 在创建会议配置设置时更改多个属性值

  - 可以通过包含多个参数来修改多个属性值。例如，以下命令允许所有人以演示者身份加入会议，同时强制 PSTN 用户在会议厅等待，直至他们被正式允许加入会议：
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

有关详细信息，请参阅 [New-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMeetingConfiguration) cmdlet 的帮助主题。

