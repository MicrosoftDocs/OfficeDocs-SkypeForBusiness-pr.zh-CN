---
title: Lync Server 2013：查看 PSTN 用法记录
description: Lync Server 2013：查看 PSTN 用法记录。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924ea74a4bb19b36da91bf97f51fbf4af54835a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579618"
---
# <a name="view-pstn-usage-records-in-lync-server-2013"></a>在 Lync Server 2013 中查看 PSTN 用法记录

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

公共交换电话网络 (PSTN) 使用记录指定一类呼叫 (，例如内部、本地或远距离) ，可以由组织中的各种用户或用户组进行。 有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的 PSTN 用法记录](lync-server-2013-pstn-usage-records.md) 。

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板查看 PSTN 用法记录

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 " **语音路由** "，然后单击 " **PSTN 用法**"。

4.  在 " **PSTN 使用情况** " 页上，突出显示要查看的 pstn 用法记录，单击 " **编辑** "，然后单击 " **显示详细信息**"。
    
    <div>
    

    > [!NOTE]  
    > 选定 PSTN 用法记录的只读页面显示关联的路由和关联的语音策略。

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看 PSTN 用法信息

您还可以使用 Windows PowerShell 和 **CsPstnUsage** CMDLET 查看 PSTN 用法。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 查看 PSTN 用法信息

  - 若要查看有关您的所有 PSTN 用法的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsPstnUsage
    
    此命令会返回类似下列信息：
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

有关详细信息，请参阅 [CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建语音策略和配置 PSTN 用法记录](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

