---
title: Lync Server 2013：在 Microsoft Exchange 上配置统一消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4a97a97d96f91b0433c65b7eb3e352dcf47c7d5
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>在 Microsoft Exchange for Lync Server 2013 上配置统一消息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-24_

本主题介绍如何在 Microsoft Exchange Server 上配置 Exchange 统一消息（UM），以便与企业语音配合使用。

<div>


> [!NOTE]  
> 本主题中的 cmdlet 示例提供 exchange 2007 版本的 Exchange 命令行管理程序的语法。 如果您运行的是 Exchange 2010 或 Exchange 2013，请参阅参考的相应文档。



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>配置运行 Exchange Server UM 的服务器

1.  为您的每个企业语音位置配置文件创建 UM 会话初始协议（SIP）统一资源标识符（URI）的拨号计划。 如果你选择使用 Exchange 管理控制台，请使用安全设置 "安全设置" **（首选）** 创建新的拨号计划。
    
    <div>
    

    > [!WARNING]  
    > 如果将 "安全设置" 值设置为 " <STRONG>Sip 安全</STRONG>" 以仅要求 sip 通信加密，如之前建议的，请注意，如果前端池配置为要求加密，则拨号计划中的此安全设置不是足够的，这意味着池要求对 SIP 和 RTP 流量加密。 当拨号计划和池安全设置不兼容时，从前端池中调用 Exchange UM 的所有呼叫都将失败，从而导致错误，表明您的 "安全设置不兼容"。

    
    </div>
    
    如果您使用的是 Exchange 命令行管理程序，请键入：
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    有关详细信息，请参阅：
    
      - 有关 Office 通信服务器2007，请参阅 "如何创建统一消息 SIP URI 拨号计划" [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632)和 "新-UMDialplan： Exchange 2007 帮助"。 [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)
    
      - 对于 Exchange 2010，请参阅 "创建 UM 拨号计划" [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674)和 "新-UMDialplan： Exchange 2010 帮助"。 [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)
    
      - 有关 Exchange 2013，请参阅的[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)"统一消息"。
    
    <div>
    

    > [!NOTE]  
    > 选择的安全级别是<STRONG>SIPSecured</STRONG> <STRONG>还是安全级别取决于</STRONG>是否为媒体加密激活或停用安全实时传输协议（SRTP）。 对于 Lync Server 2010 与 Exchange UM 的集成，这应对应于 Lync Server 媒体配置中的加密级别。 可通过运行<STRONG>CsMediaConfiguration</STRONG> Cmdlet 查看 Lync Server 媒体配置。 有关详细信息，请参阅 Lync Server Management Shell 文档中的 CsMediaConfiguration。<BR>有关选择相应的 VoIP 安全设置的详细信息，请参阅<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">集成本地统一消息和 Lync Server 2013 的部署过程</A>。

    
    </div>

2.  运行以下 cmdlet 以获取每个 UM 拨号计划的完全限定的域名（FQDN）：
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    有关详细信息，请参阅：
    
      - 有关 Exchange 2007，请参阅 "UMDialplan： Exchange 2007 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)。
    
      - 有关 Exchange 2010，请参阅 "UMDialplan： Exchange 2010 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)。
    
      - 有关 Exchange 2013，请参阅的[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)"统一消息"。

3.  记录每个 UM 拨号计划的拨号计划名称。 根据你的 Exchange Server 版本，你可能需要先使用每个拨号计划名称的 FQDN 作为每个 UM 拨号计划的相应 Lync 服务器拨号计划的名称，以便拨入计划名称匹配。
    
    <div>
    

    > [!NOTE]  
    > 只有当 UM 拨号计划在<EM>早</EM>于 EXCHANGE 2010 SP1 的 exchange 版本上运行时，Lync Server 拨号计划名称才必须匹配 um 拨号计划名称。

    
    </div>

4.  将拨号计划添加到运行 Exchange UM 的服务器，如下所示：
    
      - 如果您选择使用 Exchange 管理控制台，则可以从服务器的属性表中添加拨号计划。 有关特定说明，请参阅 Exchange Server 产品文档。
        
        对于 Exchange 2007，请参阅 "如何将统一消息服务器添加到拨号计划" [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)。
        
        对于 Exchange 2010，请参阅 "查看或配置 UM 服务器的属性" [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)。
        
        有关 Exchange 2013，请参阅的[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)"统一消息"。
    
      - 如果您使用的是 Exchange 命令行管理程序，请为您的每个 Exchange UM 服务器运行以下命令：
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > 在执行以下步骤之前，请确保所有企业语音用户均已配置了 Exchange Server 邮箱。<BR>有关 Exchange 2007，请参阅中的 Exchange Server 2007 TechNet <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>库。<BR>有关 Exchange 2010，请参阅中的 Exchange Server 2010 TechNet <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>库。<BR>为在步骤1中创建的每个拨号计划指定邮箱策略时，请选择默认策略或已创建的策略。

    
    </div>

5.  导航到\<exchange 安装目录\>\\脚本，然后如果在单个林中部署了 exchange，请键入：
    ```console
    exchucutil.ps1
    ```
    或者，如果 Exchange 是在多个目录林中部署的，请键入：
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    其中，林 FQDN 指定了在其中部署 Lync 服务器的林。
    
    如果您有一个或多个与多个 IP 网关相关联的 UM 拨号计划，请继续执行步骤6。 如果您的拨号计划仅与单个 IP 网关相关联，请跳过步骤6。
    
    <div>
    

    > [!IMPORTANT]  
    > 请确保在运行 exchucutil<EM>后</EM>重新启动<STRONG>Lync Server 前端</STRONG>服务（rtcsrv）。 否则，Lync Server 将不会检测拓扑中的统一消息。

    
    </div>

6.  使用 Exchange 命令行管理程序或 Exchange 管理控制台，禁用除了一个与每个拨号计划关联的 IP 网关之外的所有其他 IP 网关的出站呼叫。
    
    <div>
    

    > [!NOTE]  
    > 必须执行此步骤，以确保由运行 Exchange Server 统一消息的服务器对外部用户的出站调用（例如，在使用手机方案的情况下）可靠地遍历企业防火墙。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 选择允许传出呼叫的 UM IP 网关时，选择可能处理最多流量的 UM IP 网关。 不允许传出流量通过连接到 Lync Server 控制器池的 IP 网关。 还要避免在另一个中心站点或分支站点中使用池。 你可以使用以下任一方法阻止传出呼叫通过 IP 网关传递：

    
    </div>
    
      - 如果使用 Exchange 命令行管理程序，请通过运行以下命令禁用每个 IP 网关：
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        对于 Exchange 2007，请参阅 "Set-UMIPGateway： Exchange 2007 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)。
        
        对于 Exchange 2010，请参阅 "Set-UMIPGateway： Exchange 2010 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)。
    
      - 如果您使用的是 Exchange 管理控制台，请清除 "**允许通过此 IP 网关拨出呼叫**" 复选框。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果你的 UM SIP URI 拨号计划仅与单个 IP 网关相关联，请不要通过此网关禁止传出呼叫。

    
    </div>

7.  为每个 Lync Server 拨号计划创建 UM 自动助理。
    
    <div>
    

    > [!IMPORTANT]  
    > 不要在自动助理的名称中包含任何空格。

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    有关详细信息，请参阅：
    
      - 有关 Exchange 2007，请参阅 "New-UMAutoAttendant： Exchange 2007 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)。
    
      - 有关 Exchange 2010，请参阅 "New-UMAutoAttendant： Exchange 2010 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)。
    
    在已启用 "适用于企业语音的 Lync Server 用户" 并了解其 SIP Uri 之后，应为每个用户执行以下步骤。

8.  将 Exchange UM 用户（每个用户都配置有 Exchange 邮箱的用户）与 UM 拨号计划相关联，并为每个用户创建 SIP URI。
    
    <div>
    

    > [!NOTE]  
    > 以下示例中的<STRONG>SIPResourceIdentifier</STRONG>必须是 Lync 服务器用户的 SIP 地址。

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    有关详细信息，请参阅：
    
      - 对于 Exchange 2007，请参阅 "Enable-UMMailbox： Exchange 2007 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)。
    
      - 对于 Exchange 2010，请参阅 "Enable-UMMailbox： Exchange 2010 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

