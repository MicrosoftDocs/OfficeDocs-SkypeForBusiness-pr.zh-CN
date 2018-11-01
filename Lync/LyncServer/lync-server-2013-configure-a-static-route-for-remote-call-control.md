---
title: Lync Server 2013：为远程呼叫控制配置静态路由
TOCTitle: 为远程呼叫控制配置静态路由
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615051(v=OCS.15)
ms:contentKeyID: 49314773
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为远程呼叫控制配置静态路由

 

_**上一次修改主题：** 2012-09-22_

远程呼叫控制要求每个 Lync Server 池都配置一条从该池到连接到专用交换机 (PBX) 的 SIP/CSTA 网关的路径。该路径要求每个池中的每个网关都具有一个静态路由，池会将与对 PBX 的呼叫相关联的 SIP 呼叫控制消息代理到该路由。如果为远程呼叫控制配置全局静态路由，则每个未在池级别配置静态路由的池都会使用该全局静态路由。

## 为远程呼叫控制配置静态路由

1.  以 RTCUniversalServerAdmins 组成员或基于角色的访问控制 (RBAC) 角色成员的身份登录安装了 Lync Server 命令行管理程序，且已为其分配 **New-CsStaticRoute** cmdlet 的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  要创建静态路由，并将其置于变量 $TLSRoute 或 $TCPRoute 中，请执行以下操作之一：
    
    > [!TIP]
    > 要匹配某个域的子域，可在 MatchUri 参数中指定通配符值。例如， <strong>*.contoso.net</strong> 。该值与以后缀 <strong>contoso.net</strong> 结尾的任何域匹配。
    
      - 对于传输层安全性 (TLS) 连接，请在命令提示符处键入以下内容：
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        
        例如：
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        
        如果 UseDefaultCertificate 设置为 False，则必须指定 TLSCertIssuer 和 TLSCertSerialNumber 参数。这些参数分别指示发布静态路由中使用的证书的证书颁发机构 (CA) 名称和 TLS 证书的序列号。有关这些参数的详细信息，请在命令提示符处键入以下命令以查看 Lync Server 命令行管理程序帮助：
        
            Get-Help New-CsStaticRoute -Full
    
      - 对于传输控制协议 (TCP) 连接，请在命令提示符处键入以下内容：
        
        > [!NOTE]  
		> 如果指定完全限定域名 (FQDN)，则必须首先配置域名系统 (DNS) A 记录。
        
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        
        例如：
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        
        以下是静态路由可选参数的默认值：
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        强烈建议不要更改这些默认值。但是，如果必须更改任一参数，请在命令提示符处键入以下命令以查看 Lync Server 命令行管理程序帮助：
        
            Get-Help New-CsStaticRoute -Full

4.  要将新创建的静态路由保留在 中央管理存储中，请根据需要运行以下各项之一：
    
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}

       &nbsp;
    
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}

## 另请参阅

#### 任务

[在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序项](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)

