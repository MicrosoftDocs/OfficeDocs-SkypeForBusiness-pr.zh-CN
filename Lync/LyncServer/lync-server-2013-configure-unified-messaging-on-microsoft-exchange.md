---
title: 在 Microsoft Exchange 中为 Lync Server 2013 配置统一消息
TOCTitle: 在 Microsoft Exchange 中为 Lync Server 2013 配置统一消息
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398129(v=OCS.15)
ms:contentKeyID: 49311897
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Microsoft Exchange 中为 Lync Server 2013 配置统一消息

 

_**上一次修改主题：** 2016-12-08_

本主题介绍如何配置 Microsoft Exchange Server 上的 Exchange 统一消息 (UM) 以便与企业语音一起使用。

> [!NOTE]  
> 本主题中的 cmdlet 示例提供 Exchange 2007 版本的 Exchange 命令行管理程序的语法。如果运行的是 Exchange 2010 或 Exchange 2013，请参阅引用的相应文档。



## 配置运行 Exchange Server UM 的服务器

1.  为每个企业语音位置配置文件创建 UM 会话初始协议 (SIP) 统一资源标识符 (URI) 拨号计划。如果选择使用 Exchange 管理控制台，则创建一个具有安全设置 **Secured（首选）**的新拨号计划。
    
    > [!WARNING]
    > 如果将安全设置值设置为 <strong>SIP Secured</strong> 来要求仅加密 SIP 流量（如之前所建议），请注意，如果前端池配置为要求加密（表明该池要求对 SIP 和 RTP 流量都进行加密），则拨号计划上的该安全设置是不够的。当拨号计划和池安全设置不兼容时，前端池对 Exchange UM 的所有呼叫都将失败，从而导致一个错误，指示您具有“不兼容的安全设置”。
    
    如果使用 Exchange 命令行管理程序，则键入：
    
        New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    
    有关详细信息，请参阅：
    
      - 对于 Office Communications Server 2007，请参阅“如何创建统一消息 SIP URI 拨号计划”（网址为 [http://go.microsoft.com/fwlink/?linkid=268632\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268632%26clcid=0x804)）和“New-UMDialplan：Exchange 2007 帮助”（网址为 [http://go.microsoft.com/fwlink/?linkid=268666\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268666%26clcid=0x804)）。
    
      - 对于 Exchange 2010，请参阅“创建 UM 拨号计划”（网址为 [http://go.microsoft.com/fwlink/?linkid=268674\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268674%26clcid=0x804)）和“New-UMDialplan：Exchange 2010 帮助”（网址为 [http://go.microsoft.com/fwlink/?linkid=268680\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268680%26clcid=0x804)）。
    
      - 对于 Exchange 2013，请参阅“统一消息”，网址为 [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x804)。
    
    > [!NOTE]  
    > 选择 <strong>SIPSecured</strong> 还是 <strong>Secured</strong> 安全级别，取决于对媒体加密是激活还是停用了安全实时传输协议 (SRTP)。为使 Lync Server 2010 与 Exchange UM 集成，这应与 Lync Server 媒体配置中的加密级别相对应。可以通过运行 <strong>Get-CsMediaConfiguration</strong> cmdlet 查看 Lync Server 媒体配置。有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 Get-CsMediaConfiguration。<br />
    有关选择适当的 VoIP 安全设置的详细信息，请参阅<a href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">集成本地统一消息与 Lync Server 2013 的部署过程</a>。
    


2.  运行以下 cmdlet 获取每个 UM 拨号计划的完全限定的域名 (FQDN)：
    
    ``` 
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    有关详细信息，请参阅：
    
      - 对于 Exchange 2007，请参阅“Get-UMDialplan：Exchange 2007 帮助”，网址为 [http://go.microsoft.com/fwlink/?linkid=268678\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268678%26clcid=0x804)。
    
      - 对于 Exchange 2010，请参阅“Get-UMDialplan：Exchange 2010 帮助”，网址为 [http://go.microsoft.com/fwlink/?linkid=268679\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268679%26clcid=0x804)。
    
      - 对于 Exchange 2013，请参阅“统一消息”，网址为 [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x804)。

3.  记录每个 UM 拨号计划的拨号计划名称。您之后可能需要将每个拨号计划名称的 FQDN 用作每个 UM 拨号计划对应 Lync Server 拨号计划的名称，以便确保拨号计划名称匹配，具体情况取决于您使用的 Exchange Server 版本。
    
    > [!NOTE]  
    > 仅当 UM 拨号计划在早于 Exchange 2010 SP1 的 Exchange 版本上运行时，Lync Server 拨号计划的名称才必须与 UM 拨号计划的名称相匹配。
    


4.  将拨号计划添加到运行 Exchange UM 的服务器，如下所述：
    
      - 如果选择使用 Exchange 管理控制台，则可以通过服务器的属性页添加拨号计划。有关具体说明，请参阅 Exchange Server 产品文档。
        
        对于 Exchange 2007，请参阅“如何将统一消息服务器添加到拨号计划中”，网址为 [http://go.microsoft.com/fwlink/?linkid=268681\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268681%26clcid=0x804)。
        
        对于 Exchange 2010，请参阅“查看或配置 UM 服务器的属性”，网址为 [http://go.microsoft.com/fwlink/?linkid=268682\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268682%26clcid=0x804)。
        
        对于 Exchange 2013，请参阅“统一消息”，网址为 [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x804)。
    
      - 如果使用 Exchange 命令行管理程序，请为每台 Exchange UM 服务器运行以下内容：
        
            $ums=get-umserver; 
            $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
            $ums[0].DialPlans +=$dp.Identity; 
            set-umserver -instance $ums[0]
    
    > [!NOTE]  
    > 执行以下步骤之前，请确保已为所有企业语音用户配置了 Exchange Server 邮箱。<br />
    对于 Exchange 2007，请访问 Exchange Server 2007 TechNet 库，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=268685%26clcid=0x804" class="uri">http://go.microsoft.com/fwlink/?linkid=268685&amp;clcid=0x804</a>。<br />
    对于 Exchange 2010，请访问 Exchange Server 2010 TechNet 库，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=268686%26clcid=0x804" class="uri">http://go.microsoft.com/fwlink/?linkid=268686&amp;clcid=0x804</a>。<br />
    为在步骤 1 中创建的每个拨号计划指定邮箱策略时，既可以选择默认策略，也可以选择已创建的策略。
    


5.  导航到 \<*Exchange 安装目录*\>\\Scripts，然后，如果 Exchange 部署在一个林中，则键入：
    
        exchucutil.ps1
    
    否则，如果 Exchange 部署在多个林中，则键入：
    
        exchucutil.ps1 -Forest:"<forest FQDN>"
    
    其中，*forest FQDN* 指定在其中部署 Lync Server 的林。
    
    如果具有与多个 IP 网关关联的一个或多个 UM 拨号计划，则继续步骤 6。如果每个拨号计划仅与单个 IP 网关关联，则跳过步骤 6。
    
    > [!IMPORTANT]  
    > 运行 exchucutil.ps1 后，请确保重新启动“Lync Server 前端”服务 (rtcsrv.exe)。否则，Lync Server 将无法在拓扑中检测统一消息。


6.  通过使用 Exchange 命令行管理程序或 Exchange 管理控制台，禁用所有 IP 网关的出站呼叫（与每个拨号计划关联的 IP 网关除外）。
    
    > [!NOTE]  
    > 要确保由运行 Exchange Server 统一消息的服务器到外部用户的出站呼叫（例如在电话上播放的方案就是这种情况）可靠地穿越企业防火墙，此步骤必不可少。
    
    
    > [!IMPORTANT]  
    > 当选择允许传出呼叫通过的 UM IP 网关时，请选择有希望处理最多流量的 UM IP 网关。请勿允许传出流量通过与 Lync Server 控制器池连接的 IP 网关。此外，避免池位于其他中央站点或分支站点中。可以使用以下任意一种方法阻止传出呼叫通过 IP 网关传递：
    
      - 如果使用的是 Exchange 命令行管理程序，则可通过运行以下命令来禁用每个 IP 网关：
        
            Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        
        对于 Exchange 2007，请参阅“Set-UMIPGateway：Exchange 2007 帮助”，网址为 [http://go.microsoft.com/fwlink/?linkid=268687\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268687%26clcid=0x804)
        
        对于 Exchange 2010，请参阅“Set-UMIPGateway：Exchange 2010 帮助”，网址为 [http://go.microsoft.com/fwlink/?linkid=268688\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268688%26clcid=0x804)。
    
      - 如果使用 Exchange 管理控制台，请清除“允许通过此 IP 网关的传出呼叫”复选框。
    
    > [!IMPORTANT]  
    > 如果您的 UM SIP URI 拨号计划仅与单个 IP 网关关联，则不禁止传出呼叫通过此网关。


7.  为每个 Lync Server 拨号计划创建一个 UM 自动助理。
    
    > [!IMPORTANT]  
    > 请勿在自动助理的名称中包含任何空格。
    
        New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    
    有关详细信息，请参阅：
    
      - 对于 Exchange 2007，请参阅“New-UMAutoAttendant：Exchange 2007 帮助”，网址为 [http://go.microsoft.com/fwlink/?linkid=268689\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268689%26clcid=0x804)。
    
      - 对于 Exchange 2010，请参阅“New-UMAutoAttendant：Exchange 2010 帮助”，网址为 [http://go.microsoft.com/fwlink/?linkid=268690\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268690%26clcid=0x804)。
    
    为 Lync Server 用户启用企业语音并了解这些用户的 SIP URI 之后，应对每个用户执行下面的步骤。

8.  将 Exchange UM 用户（他们中的每一个应该都配置了 Exchange 邮箱）与 UM 拨号计划关联，并为每个用户创建一个 SIP URI。
    
    > [!NOTE]  
    > 以下示例中的 <strong>SIPResourceIdentifier</strong> 必须是 Lync Server 用户的 SIP 地址。
    
    
        enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    
    有关详细信息，请参阅：
    
      - 对于 Exchange 2007，请参阅“Enable-UMMailbox：Exchange 2007 帮助”，网址为 [http://go.microsoft.com/fwlink/?linkid=268691\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268691%26clcid=0x804)。
    
      - 对于 Exchange 2010，请参阅“Enable-UMMailbox：Exchange 2010 帮助”，网址为 [http://go.microsoft.com/fwlink/?linkid=268692\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268692%26clcid=0x804)。

