---
title: Lync Server 2013：为 Lync 用户启用远程呼叫控制
TOCTitle: 为 Lync 用户启用远程呼叫控制
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615048(v=OCS.15)
ms:contentKeyID: 49314730
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为 Lync 用户启用远程呼叫控制

 

_**上一次修改主题：** 2016-12-08_

您可以使用基于服务器的带内设置策略配置 Lync 用户，以进行远程呼叫控制。您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序命令行接口管理带内设置的相关设置。这些工具可替代早期版本中用于管理“组策略”设置的 Windows Management Instrumentation (WMI) 管理单元。

如果要允许用户在 Lync 中配置其自己的远程呼叫控制设置，则可以在不指定“线路服务器 URI”和“线路 URI”值的情况下，在服务器上配置用户的远程呼叫控制设置。请确保为用户提供正确的“线路服务器 URI”和“线路 URI”值，以及配置这些设置的说明。有关在 Lync Server 中手动配置远程呼叫控制的过程，请参阅“设置电话选项和号码”，网址为 <http://go.microsoft.com/fwlink/p/?linkid=210132>，位于 Microsoft Office 网站的 Lync 客户端文档中。

如果已具有 Communications Server 2007 R2 或 Communications Server 2007 部署，则在并行迁移过程中， Communicator 2007 R2 和 Communicator 2007 客户端将继续使用“组策略”。但是，如果要将策略设置保留到 Lync 客户端，需要配置等效的 Lync Server 带内设置。

> [!NOTE]  
> 要为用户启用远程呼叫控制，则需要同时为用户提供“线路 URI”和“线路服务器 URI”。如 <a href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013 中远程呼叫控制的部署任务</a>中所述，需要确保使用这些设置的网关所要求的语法。<br />
请确保“线路服务器 URI”中的域与您为网关配置静态路由时在 MatchUri 参数中指定的目标域相同。<br />
“线路 URI”以 E.164 格式指定分配给用户的电话号码，带有“TEL:”前缀（例如，tel:+14255550150）。如果要配置分机号，则格式为 tel:+14255550150;ext=111。如果您之前已配置用户的“线路 URI”，且未更改其值，则在为用户启用远程呼叫控制时，不需要指定“线路 URI”。



## 使用命令行管理程序为启用了 Lync 的用户启用远程呼叫控制

1.  以 RTCUniversalServerAdmins 组成员或以已为其分配 **Set-CsUser** cmdlet 的基于角色的访问控制角色身份登录安装 Lync Server 命令行管理程序计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  要使用 **Set-CsUser** cmdlet 为已启用 Lync 的现有用户配置远程呼叫控制，请执行以下操作：
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    例如：
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

## 使用 Lync Server 控制面板为用户配置远程呼叫控制

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”。

4.  在“搜索用户”框中，键入所需用户帐户的全部（或第一部分）显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI)，然后单击“查找”。

5.  在表中，单击要修改的用户帐户。

6.  在“编辑”菜单上，单击“修改”。

7.  在“电话”中，执行下列操作之一：
    
      - 要启用远程呼叫控制，以使用户可以从 Lync 2013 控制其专用交换机 (PBX) 电话，从而进行 PC 到 PC 音频呼叫和 PC 到电话呼叫，请单击“远程呼叫控制”。在“线路 URI”中，指定用户的电话号码。在“线路服务器 URI”中，指定 SIP/CSTA 网关的 SIP URI。
    
      - 要启用远程呼叫控制，但禁用 PC 到 PC 音频呼叫，仅使用户可以从 Lync 2013 控制其 PBX 电话以进行 PC 到电话呼叫，请单击“仅远程呼叫控制”。在“线路 URI”中，指定用户的电话号码。在“线路服务器 URI”中，指定 SIP/CSTA 网关的 SIP URI。

8.  完成后，单击“提交”。

