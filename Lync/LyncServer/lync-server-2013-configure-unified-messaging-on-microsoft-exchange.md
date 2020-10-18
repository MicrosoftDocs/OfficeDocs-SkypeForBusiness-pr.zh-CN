---
title: Lync Server 2013：在 Microsoft Exchange 上配置统一消息
description: Lync Server 2013：在 Microsoft Exchange 上配置统一消息。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8db43bbe50061a1a044bdd34b637ba86f626ca85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577518"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>在 Microsoft Exchange 上为 Lync Server 2013 配置统一消息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-24_

本主题介绍如何在 Microsoft Exchange Server 上配置 Exchange 统一消息 (UM) ，以便与企业语音配合使用。

<div>


> [!NOTE]  
> 本主题中的 cmdlet 示例提供了 Exchange 2007 版本的 Exchange 命令行管理程序的语法。 如果您运行的是 Exchange 2010 或 Exchange 2013，请参阅参考的相应文档。



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>配置运行 Exchange Server UM 的服务器

1.  为每个企业语音位置配置文件创建 UM 会话初始协议 (SIP) 统一资源标识符 (URI) 拨号计划。如果选择使用 Exchange 管理控制台，则创建一个具有安全设置 **Secured（首选）** 的新拨号计划。
    
    <div>
    

    > [!WARNING]  
    > 如果将安全设置值设置为 <STRONG>SIP Secured</STRONG> 来要求仅加密 SIP 流量（如之前所建议），请注意，如果前端池配置为要求加密（表明该池要求对 SIP 和 RTP 流量都进行加密），则拨号计划上的该安全设置是不够的。 当拨号计划和池安全设置不兼容时，来自前端池的对 Exchange UM 的所有呼叫都将失败，从而导致出现错误，指示您具有 "不兼容的安全设置"。

    
    </div>
    
    如果使用 Exchange 命令行管理程序，则键入：
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    有关详细信息，请参阅：
    
      - 有关 Office 通信服务器2007，请参阅 at 和 "UMDialplan： Exchange 2007 帮助" 中的 "如何创建统一消息 SIP URI 拨号计划" [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) 和 "新-： Exchange 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) 。
    
      - 有关 Exchange 2010，请参阅 at [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) 和 "UMDialplan： exchange 2010 帮助" 处的 "创建 UM 拨号计划" 和 "新-： Exchange 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) 。
    
      - 对于 Exchange 2013，请参阅中的 "统一消息" [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。
    
    <div>
    

    > [!NOTE]  
    > 选择 <STRONG>SIPSecured</STRONG> 还是 <STRONG>Secured</STRONG> 安全级别，取决于对媒体加密是激活还是停用了安全实时传输协议 (SRTP)。 对于与 Exchange UM 的 Lync Server 2010 集成，这应与 Lync Server 媒体配置中的加密级别相对应。 可以通过运行 <STRONG>set-csmediaconfiguration</STRONG> cmdlet 来查看 Lync Server 媒体配置。 有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 Get-CsMediaConfiguration。<BR>有关选择适当的 VoIP 安全设置的详细信息，请参阅 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">集成本地统一消息和 Lync Server 2013 的部署过程</A>。

    
    </div>

2.  运行以下 cmdlet 获取每个 UM 拨号计划的完全限定的域名 (FQDN)：
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    有关详细信息，请参阅：
    
      - 有关 Exchange 2007，请参阅位于处的 "UMDialplan： Exchange 2007 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) 。
    
      - 有关 Exchange 2010，请参阅位于处的 "UMDialplan： Exchange 2010 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) 。
    
      - 对于 Exchange 2013，请参阅中的 "统一消息" [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。

3.  记录每个 UM 拨号计划的拨号计划名称。 根据您的 Exchange Server 版本，您可能需要在以后将每个拨号计划名称的 FQDN 用作每个 UM 拨号计划对应的 Lync Server 拨号计划的名称，以便与拨号计划名称相匹配。
    
    <div>
    

    > [!NOTE]  
    > 只有在 UM 拨号计划运行在 exchange 2010 SP1 <EM>之前</EM> 的 exchange 版本上时，Lync Server 拨号计划名称才必须与 um 拨号计划名称相匹配。

    
    </div>

4.  将拨号计划添加到运行 Exchange UM 的服务器上，如下所示：
    
      - 如果选择使用 Exchange 管理控制台，则可以通过服务器的属性页添加拨号计划。有关具体说明，请参阅 Exchange Server 产品文档。
        
        有关 Exchange 2007，请参阅中的 "如何将统一消息服务器添加到拨号计划中" [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) 。
        
        有关 Exchange 2010，请参阅在上的 "查看或配置 UM 服务器的属性" [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) 。
        
        对于 Exchange 2013，请参阅中的 "统一消息" [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。
    
      - 如果使用 Exchange 命令行管理程序，请为每台 Exchange UM 服务器运行以下内容：
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > 执行以下步骤之前，请确保已为所有企业语音用户配置了 Exchange Server 邮箱。<BR>对于 Exchange 2007，请参阅上的 Exchange Server 2007 TechNet 库 <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> 。<BR>对于 Exchange 2010，请参阅上的 Exchange Server 2010 TechNet 库 <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> 。<BR>为在步骤 1 中创建的每个拨号计划指定邮箱策略时，既可以选择默认策略，也可以选择已创建的策略。

    
    </div>

5.  导航到 \<Exchange installation directory\> \\ "脚本"，然后如果在一个林中部署了 Exchange，请键入：
    ```console
    exchucutil.ps1
    ```
    否则，如果 Exchange 部署在多个林中，则键入：
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    其中，林 FQDN 指定要在其中部署 Lync Server 的林。
    
    如果具有与多个 IP 网关关联的一个或多个 UM 拨号计划，则继续步骤 6。如果每个拨号计划仅与单个 IP 网关关联，则跳过步骤 6。
    
    <div>
    

    > [!IMPORTANT]  
    > 运行 exchucutil.ps1 后<EM></EM>，请确保重新启动“Lync Server 前端”<STRONG></STRONG>服务 (rtcsrv.exe)。 否则，Lync Server 将不会在拓扑中检测到统一消息。

    
    </div>

6.  通过使用 Exchange 命令行管理程序或 Exchange 管理控制台，禁用所有 IP 网关的出站呼叫（与每个拨号计划关联的 IP 网关除外）。
    
    <div>
    

    > [!NOTE]  
    > 需要执行此步骤，以确保运行 Exchange Server 统一消息的服务器对外部用户进行的出站呼叫 (例如，在电话上播放的方案) 可靠地遍历公司防火墙。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 当选择允许传出呼叫通过的 UM IP 网关时，请选择有希望处理最多流量的 UM IP 网关。 不允许传出流量通过连接到 Lync Server 控制器池的 IP 网关。 此外，避免池位于其他中央站点或分支站点中。 可以使用以下任意一种方法阻止传出呼叫通过 IP 网关传递：

    
    </div>
    
      - 如果使用的是 Exchange 命令行管理程序，则可通过运行以下命令来禁用每个 IP 网关：
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        有关 Exchange 2007，请参阅位于处的 "UMIPGateway： Exchange 2007 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) 。
        
        有关 Exchange 2010，请参阅位于处的 "UMIPGateway： Exchange 2010 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) 。
    
      - 如果使用 Exchange 管理控制台，请清除 **“允许通过此 IP 网关的传出呼叫”** 复选框。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您的 UM SIP URI 拨号计划仅与单个 IP 网关关联，则不禁止传出呼叫通过此网关。

    
    </div>

7.  为每个 Lync Server 拨号计划创建一个 UM 自动助理。
    
    <div>
    

    > [!IMPORTANT]  
    > 请勿在自动助理的名称中包含任何空格。

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    有关详细信息，请参阅：
    
      - 有关 Exchange 2007，请参阅位于处的 "Get-umautoattendant： Exchange 2007 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) 。
    
      - 有关 Exchange 2010，请参阅位于处的 "Get-umautoattendant： Exchange 2010 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) 。
    
    为每个用户启用了适用于企业语音的 Lync Server 用户并了解其 SIP Uri 后，应执行以下步骤。

8.  将 Exchange UM 用户（他们中的每一个应该都配置了 Exchange 邮箱）与 UM 拨号计划关联，并为每个用户创建一个 SIP URI。
    
    <div>
    

    > [!NOTE]  
    > 以下示例中的 <STRONG>SIPResourceIdentifier</STRONG> 必须是 Lync Server 用户的 SIP 地址。

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    有关详细信息，请参阅：
    
      - 有关 Exchange 2007，请参阅位于上的 "Enable-Get-ummailbox： Exchange 2007 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) 。
    
      - 有关 Exchange 2010，请参阅位于上的 "Enable-Get-ummailbox： Exchange 2010 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

