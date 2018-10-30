---
title: 修改未显式支持或限制的客户端的默认操作
TOCTitle: 修改未显式支持或限制的客户端的默认操作
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520994(v=OCS.15)
ms:contentKeyID: 49312877
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 修改未显式支持或限制的客户端的默认操作

 

_**上一次修改主题：** 2013-02-23_

除了指定希望在 Lync Server 2013 环境中支持的客户端版本之外，还可以指定尚未定义版本策略的客户端的默认操作。这样可以限制在 Lync Server 环境中使用的客户端版本，从而帮助您控制与支持多个客户端版本相关的成本。

## 修改未显式支持或限制的客户端的默认操作

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“客户端版本配置”。

4.  在“客户端版本配置”页上，双击列表中的“全局”配置。

5.  在“编辑客户端版本配置”对话框中，验证是否已选中“启用版本控制”复选框，然后在“默认操作”下选择下列操作之一：
    
      - **允许** 如果客户端版本不匹配“客户端版本策略”列表中的任何筛选器，则允许客户端登录。
    
      - **阻止** 如果客户端版本不匹配“客户端版本策略”列表中的任何筛选器，则阻止客户端登录。
    
      - **使用 URL 阻止** 如果客户端版本不匹配“客户端版本策略”列表中的任何筛选器，则阻止客户端登录，并提供包含用于下载新版本客户端的 URL 的错误消息。
    
      - **使用 URL 允许** 如果客户端版本不匹配“客户端版本策略”列表中的任何筛选器，则允许客户端登录，并提供包含用于下载新版本客户端的 URL 的错误消息。

6.  如果选择“使用 URL 阻止”，则在“URL”框中键入将包含在错误消息中的客户端下载 URL。

7.  单击“提交”。

## 禁用客户端版本控制

  - 要禁用版本控制以允许所有版本的客户端登录，请清除“启用版本控制”复选框，然后单击“提交”。

## 使用 Lync Server PowerShell cmdlet 修改默认操作

用户尝试使用不受客户端版本策略显式支持或限制的客户端登录时将执行的默认操作也可通过使用 Windows PowerShell 命令行接口 和 **Set-CsClientVersionPolicy** cmdlet 管理。此 cmdet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 配置默认操作以阻止访问

  - 以下命令可将 Redmond 站点的默认操作设置为“阻止”。这将阻止针对没有客户端版本配置规则的任何客户端的注册。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

## 配置默认操作以允许访问

  - 在此示例中，Redmond 站点的默认操作将设置为“允许”。这将允许针对没有客户端版本配置规则的任何客户端的注册。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

有关详细信息，请参阅 [Set-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet 的帮助主题。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中管理设备、电话和客户端应用程序](lync-server-2013-managing-devices-phones-and-client-applications.md)

