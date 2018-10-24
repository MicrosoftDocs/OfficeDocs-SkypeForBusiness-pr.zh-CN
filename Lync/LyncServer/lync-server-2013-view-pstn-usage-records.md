---
title: Lync Server 2013：查看 PSTN 用法记录
TOCTitle: 查看 PSTN 用法记录
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398458(v=OCS.15)
ms:contentKeyID: 49313076
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中查看 PSTN 用法记录

 

_**上一次修改主题：** 2013-02-22_

公用电话交换网 (PSTN) 用法记录指定组织中各个用户或用户组所能发出的呼叫类别（如内部、本地或长途）。有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的 PSTN 用法记录](lync-server-2013-pstn-usage-records.md)。

## 使用 Lync Server 控制面板 查看 PSTN 用法记录

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”，然后单击“PSTN 用法”。

4.  在“PSTN 用法”页上，突出显示要查看的 PSTN 用法记录，单击“编辑”，然后单击“显示详细信息”。
    
    > [!NOTE]
    > 所选 PSTN 用法记录的只读页面会显示关联的路由和关联的语音策略。


## 使用 Windows PowerShell cmdlet 查看 PSTN 用法信息

还可使用 Windows PowerShell 和 **Get-CsPstnUsage** cmdlet 查看 PSTN 用法。可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 使用 Windows PowerShell cmdlet 查看 PSTN 用法信息

  - 若要查看有关所有 PSTN 用法的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsPstnUsage
    
    此命令会返回类似下列信息：
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

有关详细信息，请参阅 [Get-CsPstnUsage](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPstnUsage)。

## 另请参阅

#### 任务

[在 Lync Server 2013 中创建语音策略和配置 PSTN 用法记录](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

