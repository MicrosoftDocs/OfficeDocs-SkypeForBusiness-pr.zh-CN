---
title: Lync Server 2013：为远程呼叫控制配置受信任的应用程序项
TOCTitle: 为远程呼叫控制配置受信任的应用程序项
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558636(v=OCS.15)
ms:contentKeyID: 49312494
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序项

 

_**上一次修改主题：** 2015-11-02_

必须将 SIP/CSTA 网关配置为受信任应用程序， Lync Server 才能使用静态路由将呼叫路由到网关。

> [!IMPORTANT]  
> 如果要从 Lync Server 部署的早期版本中迁移用户，请确保在使用本主题中的过程之前删除为 SIP/CSTA 网关创建的所有现有受信任的应用程序项（以前称为授权主机条目）。有关详细信息，请参阅 <a href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">在 Lync Server 2013 中删除旧版授权主机（可选）</a>。


## 为 SIP/CSTA 网关配置受信任的应用程序项

1.  以 RTCUniversalServerAdmins 组成员或已为其分配 **New-CsTrustedApplicationPool** cmdlet 的基于角色的访问控制 (RBAC) 角色身份登录安装 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  要创建受信任的应用程序项，请执行下列操作之一：
    
      - 对于传输层安全性 (TLS) 连接，请在命令提示符处键入以下内容：
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        例如：
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - 对于传输控制协议 (TCP) 连接，请在命令提示符处键入以下内容：
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        例如：
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  要将受信任应用程序添加到池，请执行下列操作之一：
    
      - 对于 TLS 连接，请在命令提示符处键入以下内容：
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        例如：
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - 对于 TCP 连接，请在命令提示符处键入以下内容：
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        例如：
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  要实现对拓扑所做的已发布更改，请在命令提示符处键入以下内容：
    
        Enable-CsTopology

## 另请参阅

#### 任务

[在 Lync Server 2013 中为远程呼叫控制配置静态路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)

