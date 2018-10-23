---
title: Lync Server 2013：为分支站点定义 PSTN 网关
TOCTitle: 为分支站点定义 PSTN 网关
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398689(v=OCS.15)
ms:contentKeyID: 49313490
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为分支站点定义 PSTN 网关

 

_**上一次修改主题：** 2012-09-21_

请在中央站点执行此过程，中央站点至少包含一个 前端池或 Standard Edition Server。

> [!IMPORTANT]  
> 执行该过程之前，必须满足以下条件：
> <ul>
> <li><p>必须在中央站点安装 Lync Server 2013通信软件。</p></li>
> <li><p>必须在中央站点部署 中介服务器。</p></li>
> </ul>

## 定义 PSTN 网关

1.  依次单击“开始”、“所有程序”、“Microsoft Lync Server”，然后单击“Lync Server 拓扑生成器”。

2.  在控制台树中展开中央站点，展开“分支机构站点”，再展开要为其定义公用电话交换网 (PSTN) 网关的分支站点的名称，然后展开“共享组件”。

3.  右键单击“PSTN 网关”，然后单击“新建 IP/PSTN 网关”。

4.  在“定义新的 IP/PSTN 网关”对话框中，单击“网关 FQDN 或 IP 地址”，然后键入要在分支站点部署的网关的完全限定域名 (FQDN) 或 IP 地址。

5.  单击“IP/PSTN 网关的侦听端口”，然后接受默认值。

6.  在“SIP 传输协议”列表中，单击网关使用的传输协议，然后单击“确定”。
    
    > [!NOTE]  
    > 出于安全考虑，强烈建议使用支持传输层安全性 (TLS) 的 PSTN 网关。
    


> [!TIP]
> 使用 cmdlet <strong>Set-CsPstnGateway</strong> 修改 PSTN 网关的属性。有关详细信息，请参阅 Lync Server 命令行管理程序帮助中的 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</a>。


执行下一步以实现分支站点恢复能力： [在 Lync Server 2013 中为用户配置分支站点恢复能力](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

## 另请参阅

#### 概念

[Lync Server 2013 中的 PSTN 网关部署选项](lync-server-2013-pstn-gateway-deployment-options.md)

