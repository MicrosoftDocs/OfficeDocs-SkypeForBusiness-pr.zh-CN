---
title: 创建或修改会议配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6906331e8a0b2cf67c8d4c0404caf2816f441ea0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改会议配置设置的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

您可以使用 "会议配置" 页上的设置来定义会议加入体验的各种特征。 默认情况下，全局设置定义加入体验。 还可以创建站点级别和池级别的与会设置。 如果创建池级别的设置，则这些设置将应用于由该池托管的所有会议。 如果未创建池级别的设置，则应用站点级别的设置（如果存在）。 如果未定义站点级别的设置，则全局设置将应用于所有会议。

<div>

## <a name="to-create-new-meeting-join-settings"></a>创建新的与会设置

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 **“会议”**，然后单击 **“会议配置”**。

4.  在 **“会议配置”** 页上，单击 **“新建”**，然后执行下列操作之一：
    
      - 要创建站点级别的策略，请单击 **“站点配置”**。在 **“选择站点”** 搜索字段中，键入要为其定义与会设置的站点的全部或部分名称。在结果站点列表中，单击所需的站点，然后单击 **“确定”**。
    
      - 要创建池级别的策略，请单击 **“池配置”**。在 **“选择服务”** 搜索字段中，键入要为其定义与会设置的池服务的全部或部分名称。在结果服务列表中，单击所需的池，然后单击 **“确定”**。

5.  要路由从公用电话交换网 (PSTN) 通过会议厅拨入的参与者，请清除 **“PSTN 呼叫者绕过会议厅”** 复选框。默认情况下，从 PSTN 拨入的参与者可直接参加会议。

6.  要配置会议的演示者，请在 **“指定为演示者”** 中执行下列操作之一：
    
      - 要禁止组织者以外的任何人成为演示者，请单击 **“无”**。
    
      - 要只允许组织成员参与者成为演示者，请单击 **“公司”**。这是默认设置。
    
      - 要允许任何参与者成为演示者，请单击 **“所有人”**。

7.  要让组织者在安排会议时选择会议类型，请清除 **“默认分配的会议类型”** 复选框。默认情况下，会自动分配会议类型。

8.  要阻止自动允许匿名（未经身份验证）用户参加会议，请清除 **“默认允许匿名用户”** 复选框。默认情况下，自动允许匿名用户参加会议。

9.  若要自定义发送给参与者的会议邀请，请执行以下操作。 请注意，Url 和自定义页脚文本的最大长度为1KB。 除 "**帮助 URL**" 外，如果不指定自定义项的值，则不会将其包含在会议中。 如果不包含自定义帮助 URL，则会在邀请中显示 Lync 的默认帮助 URL。
    
      - 若要自定义会议邀请中显示的徽标，请在 "**徽标 URL**" 中输入徽标的位置。
        
        <div>
        

        > [!NOTE]
        > 徽标必须是大小为 188 x 30 像素的 GIF 或 JPG 图像。

        
        </div>
    
      - 若要自定义会议邀请中显示的帮助文本，请在 "**帮助 URL**" 中输入帮助文本的位置。
    
      - 若要自定义会议邀请中显示的法律文本，请在 "**合法文本 URL**" 中输入法律文本的位置。
    
      - 若要自定义会议邀请中显示的页脚文本，请在 "**自定义页脚文本**" 中，输入文本。

10. 单击“提交”****。

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>修改现有会议配置集合

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 **“会议”**，然后单击 **“会议配置”**。

4.  在会议配置列表中，单击要更改的配置，单击 "**编辑**"，然后单击 "**显示详细信息**"。

5.  在 "**编辑会议配置**" 中，修改任何配置设置（无法修改的配置名称除外）。

6.  单击“提交”****。

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建新的会议配置设置

可以使用 Windows PowerShell 和 Get-csmeetingconfiguration cmdlet 创建会议配置设置（仅限在网站范围内）。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>创建使用默认值的会议配置设置

  - 此命令将为 Redmond 站点创建一组新的会议配置设置：
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    由于前面的命令中未指定任何参数（必需的 Identity 参数），因此新的会议配置设置将对其所有属性使用默认值。

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>在创建会议配置设置时更改属性值

  - 要创建使用不同属性值的设置，只需包含相应的参数和参数值。 例如，若要创建会议配置设置的集合，默认情况下，默认情况下，允许每个人都将会议作为演示者使用类似如下的命令：
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>创建会议配置设置时更改多个属性值

  - 可以通过包含多个参数来修改多个属性值。 例如，此命令 admits 每个人作为演示者加入会议，同时还强制 PSTN 用户在大厅中等待，直到他们正式获准参加会议：
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

有关详细信息，请参阅[get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

