---
title: 服务器的端口和协议要求
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 摘要： 实现 Skype 业务服务器之前查看端口使用情况注意事项。
ms.openlocfilehash: 612a6f98ff2517163e3e720d4272c05463250cd2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882283"
---
# <a name="port-and-protocol-requirements-for-servers"></a>服务器的端口和协议要求
 
**摘要：** 实现 Skype 业务服务器之前查看端口使用情况注意事项。
  
Skype 业务服务器要求的特定端口的外部和内部防火墙上打开。 此外，如果在您的组织中部署了 Internet 协议安全性 (IPsec)，则必须在用于传送音频、视频和全景视频的端口范围内禁用 IPSec。 
  
尽管这看似位令人望而生畏开始时，可以完成规划此繁重使用[Skype 业务服务器 2015年规划工具](https://go.microsoft.com/fwlink/p/?LinkID=282725)。 后已经历有关哪些功能您打算使用的向导的问题，为每个网站定义您可以查看防火墙报告在边缘管理报告，并使用列出那里来创建 yourfirewall 规则的信息。 您还可以制作调整的许多名称和 IP 地址用于详细信息，请参阅[查看防火墙报告](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report)。 需要记住的提醒您可以导出边缘管理报告 Excel 电子表格，并防火墙报告将一个文件中的工作表。 
  
通过查看协议工作负荷海报移开[Technical diagrams for Business Server 2015 Skype 的](../../technical-diagrams.md)文章链接，还可以在这些表关系图窗体中找到信息。
> [!NOTE]
> - 如果您在实施 Skype 业务 online (O365) 请参阅[Office 365 Url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)。 混合环境需要引用此主题以及[规划混合连接性](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。
> - 您可以有硬件或软件的防火墙，我们不需要特定的模型或版本。 重要的是哪些端口是白名单，因此防火墙将不会影响 Skype 正常业务服务器。
  
## <a name="port-and-protocol-details"></a>端口和协议详细信息

本节总结的端口和协议服务器、 负载平衡器和 Skype 中的客户端用于业务服务器部署。
  
> [!NOTE]
> Skype 业务服务器启动后，在 Windows 防火墙中打开所需的端口。 在大多数普通应用程序，应已经在运行 Windows 防火墙，但如果它不是使用 Skype 的业务服务器将正常如果没有它。 
  
有关边缘组件的防火墙配置的详细信息，请参阅[中的业务服务器 2015 Skype 的边缘服务器方案](../../plan-your-deployment/edge-server-deployments/scenarios.md)。 
  
下表依据每个内部服务器角色列出了需要打开的端口。 
  
**所需服务器端口（根据服务器角色）**

|服务器角色|服务名称|端口|协议|备注|
|:-----|:-----|:-----|:-----|:-----|
|所有服务器  |SQL 浏览器  |1434  |UDP  |SQL 浏览器用于中央管理存储数据库的本地副本。  |
|前端服务器  |Skype 业务 Server 前端服务  |5060  |TCP  |（可选）Standard Edition Server 和前端服务器用于静态路由到受信任服务，例如，远程呼叫控制服务器。  |
|前端服务器  |Skype 业务 Server 前端服务  |5061  | TCP (TLS) |Standard Edition Server 和前端池用于在服务器 (MTLS) 之间进行所有的内部 SIP 通信、在服务器和客户端 (TLS) 之间进行 SIP 通信，以及在前端服务器和中介服务器 (MTLS) 之间进行 SIP 通信。还用于与监控服务器进行通信。  |
| 前端服务器 |Skype 业务 Server 前端服务  |444  | HTTPS <br/> TCP  |用于会议状态中心 (管理会议状态的业务服务器组件 Skype) 与单个服务器之间的 HTTPS 通信。  <br/> 此端口也用于 Survivable Branch Appliance 和前端服务器之间的 TCP 通信。  |
|前端服务器  |Skype 业务 Server 前端服务  |135  |DCOM 和远程过程调用 (RPC)  |用于基于 DCOM 的操作，例如，移动用户、用户复制程序同步和通讯簿同步。  |
|前端服务器  |Skype 业务服务器 IM 会议服务  |5062  |TCP  |用于即时消息 (IM) 会议的传入 SIP 请求。  |
|前端服务器  |Skype 业务 Server Web 会议服务  |8057  |TCP (TLS)  |用于侦听来自客户端的持续性共享对象模型 (PSOM) 连接。  |
|前端服务器  |Skype 业务 Server Web 会议兼容性服务  |8058  |TCP (TLS)  |用于侦听来自 Live Meeting 客户端和早期版本的 Skype 业务服务器的持续性共享对象模型 (PSOM) 连接。  |
|前端服务器  |Skype 业务 Server 音频/视频会议服务  |5063  |TCP  |用于音频/视频 (A/V) 会议的传入 SIP 请求。  |
|前端服务器  |Skype 业务 Server 音频/视频会议服务  |57501-65535  |TCP/UDP  |用于视频会议的媒体端口范围。  |
|前端服务器  |Skype 业务服务器 Web 兼容性服务  |80  |HTTP  |用于未使用 HTTPS 时从前端服务器到 Web 场 FQDN（IIS Web 组件使用的 URL）的通信。  |
|前端服务器  |Skype 业务服务器 Web 兼容性服务  |443  |HTTPS  |用于从前端服务器到 Web 场 FQDN（IIS Web 组件使用的 URL）的通信。  |
|前端服务器  |Skype 业务服务器 Web 兼容性服务  |8080  |TCP 和 HTTP  |用于 Web 组件供外部访问。  |
|前端服务器  |Web 服务器组件  |端口 4443  |HTTPS  |HTTPS（从反向代理）和 HTTPS 前端池间通信，用于自动发现登录。  |
|前端服务器  |Web 服务器组件  |8060  |TCP (MTLS)  ||
|前端服务器  |Web 服务器组件  |8061  |TCP (MTLS)  ||
|前端服务器  |Mobility Service 组件  |5086  |TCP (MTLS)  |Mobility Service 内部过程所使用的 SIP 端口。  |
|前端服务器  |Mobility Service 组件  |5087  |TCP (MTLS)  |Mobility Service 内部过程所使用的 SIP 端口。  |
|前端服务器  |Mobility Service 组件  |443  |HTTPS  ||
|前端服务器  |Skype 业务 Server 会议助理服务 （电话拨入式会议）  |5064  |TCP  |用于电话拨入式会议的传入 SIP 请求。  |
|前端服务器  |Skype 业务 Server 会议助理服务 （电话拨入式会议）  |5072  |TCP  |使用 attendant （电话拨入式会议） 的传入 SIP 请求。  |
|也运行并置中介服务器的前端服务器  |Skype 业务 Server 中介服务  |5070  |TCP  |中介服务器用于从前端服务器到中介服务器的传入请求。  |
|也运行并置中介服务器的前端服务器  |Skype 业务 Server 中介服务  |5067  |TCP (TLS)  |用于从 PSTN 网关到中介服务器的传入 SIP 请求。  |
|也运行并置中介服务器的前端服务器  |Skype 业务 Server 中介服务  |5068  |TCP  |用于从 PSTN 网关到中介服务器的传入 SIP 请求。  |
|也运行并置中介服务器的前端服务器  |Skype 业务 Server 中介服务  |5081  |TCP  |用于从中介服务器到 PSTN 网关的传出 SIP 请求。  |
|也运行并置中介服务器的前端服务器  |Skype 业务 Server 中介服务  |5082  |TCP (TLS)  |用于从中介服务器到 PSTN 网关的传出 SIP 请求。  |
|前端服务器  |Skype 业务服务器应用程序共享服务  |5065  |TCP  |用于应用程序共享的传入 SIP 侦听请求。  |
|前端服务器  |Skype 业务服务器应用程序共享服务  |49152-65535  |TCP  |用于应用程序共享的媒体端口范围。  |
|前端服务器  |Skype 业务 Server 会议通知服务  |5073  |TCP  |用于传入 SIP 请求的业务 Server 会议通知服务 Skype (即，电话拨入式会议)。  |
|前端服务器  |Skype 业务 Server 呼叫寄存服务  |5075  |TCP  |用于呼叫寄存应用程序的传入 SIP 请求。  |
|前端服务器  |Skype 业务服务器音频测试服务  |5076  |TCP  |用于音频测试服务的传入 SIP 请求。  |
|前端服务器  |不适用  |5066  |TCP  |用于出站增强型 9-1-1 (E9-1-1) 网关。  |
|前端服务器  |Skype 业务 Server 响应组服务  |5071  |TCP  |用于响应组应用程序的传入 SIP 请求。  |
|前端服务器  |Skype 业务 Server 响应组服务  |8404  |TCP (MTLS)  |用于响应组应用程序的传入 SIP 请求。  |
|前端服务器  |Skype 业务 Server 带宽策略服务  |5080  |TCP  |用于通过带宽策略服务对 A/V 边缘 TURN 流量进行呼叫允许控制。  |
|前端服务器  |业务服务器文件共享服务器访问的的 Skype  |445   |SMB/TCP  | 用于检索通讯簿、 会议内容和文件共享服务器上存储的其他项。  |
|前端服务器  |Skype 业务 Server 带宽策略服务  |448  |TCP  |Skype 由呼叫允许控制的用于业务服务器带宽策略服务。  |
|前端服务器所在中央管理存储  | Skype 业务 Server 主复制程序代理服务 |445  |TCP  |用于从中央管理存储的配置数据推送到运行 Business Server Skype 的服务器。  |
|所有服务器  |SQL 浏览器  |1434  |UDP  |SQL 浏览器的本地副本的中央管理存储本地 SQL Server 实例中的数据  |
|所有内部服务器  |各种  |49152-57500  |TCP/UDP  |用于所有内部服务器上的音频会议的媒体端口范围。 使用终止音频的所有服务器: （对于业务 Server 会议助理服务的 Skype、 Skype 业务 Server 会议通知服务和业务 Server 音频/视频会议服务的 Skype），前端服务器和中介服务器。  |
|Office Web Apps Servers  ||443  ||由 Skype 业务服务器用于连接到 Office Web Apps Server。  |
|控制器  |Skype 业务 Server 前端服务  |5060  |TCP  |（可选）用于静态路由到受信任服务，例如，远程呼叫控制服务器。  |
|控制器  |Skype 业务 Server 前端服务  |444  |HTTPS  <br/> TCP  |前端与控制器之间的服务器间通信。 此外，客户端证书发布 （到前端服务器），或验证是否已发布的客户端证书。  |
|控制器  |Skype 业务服务器 Web 兼容性服务  |80  |TCP  |用于从控制器到 Web 场 FQDN（IIS Web 组件使用的 URL）的初始通信。在常规操作中，将使用端口 443 和协议类型 TCP 切换到 HTTPS 通信。  |
|控制器  |Skype 业务服务器 Web 兼容性服务  |443  |HTTPS  |用于从控制器到 Web 场 FQDN（IIS Web 组件使用的 URL）之间的通信。  |
|控制器  |Skype 业务 Server 前端服务  |5061  |TCP  |用于服务器之间的内部通信和客户端连接。  |
|中介服务器  |Skype 业务 Server 中介服务  |5070  |TCP  |中介服务器用于来自前端服务器的传入请求。  |
|中介服务器  |Skype 业务 Server 中介服务  |5067  |TCP (TLS)  |用于来自 PSTN 网关的传入 SIP 请求。  |
|中介服务器  |Skype 业务 Server 中介服务  |5068  |TCP  |用于来自 PSTN 网关的传入 SIP 请求。  |
|中介服务器  |Skype 业务 Server 中介服务  |5070  |TCP (MTLS)  |用于来自前端服务器的 SIP 请求。  |
|持久聊天前端服务器  |持久聊天 SIP  |5041  |TCP (MTLS)  ||
|持久聊天前端服务器  |持久聊天 Windows Communication Foundation (WCF)  |881  |TCP (TLS) 和 TCP (MTLS)  ||
|持久聊天前端服务器  |持久聊天文件传输服务  |443  |TCP (TLS)  ||
   
> [!NOTE]
> 某些远程呼叫控制方案需要前端服务器或控制器与 PBX 之间的 TCP 连接。 尽管 Skype 业务服务器不再使用 TCP 端口 5060，但远程呼叫控制的部署过程中创建的受信任的服务器配置，其中将 RCC 行服务器 FQDN 与前端服务器或控制器将用于连接到的 TCP 端口相关联PBX 系统。 有关详细信息，请参阅中的业务 Server Management Shell 文档 Skype 的**CsTrustedApplicationComputer** cmdlet。
  
对于仅使用硬件负载平衡（不是 DNS 负载平衡）的池，下表显示了需要打开硬件负载平衡器的端口。
  
**仅使用硬件负载平衡时的硬件负载平衡器端口**

|负载平衡器|端口|协议|
|:-----|:-----|:-----|
|前端服务器负载平衡器  |5061  |TCP (TLS)  |
|前端服务器负载平衡器  |444  |HTTPS  |
|前端服务器负载平衡器  |135  |DCOM 和远程过程调用 (RPC)  |
|前端服务器负载平衡器  |80  |HTTP  |
|前端服务器负载平衡器  |8080  |TCP-从前端服务器的根证书的客户端和设备检索-客户端和设备通过 NTLM 身份验证  |
|前端服务器负载平衡器  |443  |HTTPS  |
|前端服务器负载平衡器  |端口 4443  |HTTPS（来自反向代理）  |
|前端服务器负载平衡器  |5072  |TCP  |
|前端服务器负载平衡器  |5073  |TCP  |
|前端服务器负载平衡器  |5075  |TCP  |
|前端服务器负载平衡器  |5076  |TCP  |
|前端服务器负载平衡器  |5071  |TCP  |
|前端服务器负载平衡器  |5080  |TCP  |
|前端服务器负载平衡器  |448  |TCP  |
|中介服务器负载平衡器  |5070  |TCP  |
|前端服务器负载平衡器（如果池也运行中介服务器）  |5070  |TCP  |
|控制器负载平衡器  |443  |HTTPS  |
|控制器负载平衡器  |444  |HTTPS  |
|控制器负载平衡器  |5061  |TCP  |
|控制器负载平衡器  |端口 4443  |HTTPS（来自反向代理）  |
   
使用 DNS 负载平衡的前端池和控制器池还必须部署硬件负载平衡器。下表显示了需要在这些硬件负载平衡器上打开的端口。
  
**使用 DNS 负载平衡时的硬件负载平衡器端口**

|负载平衡器|端口|协议|
|:-----|:-----|:-----|
|前端服务器负载平衡器  |80  |HTTP  |
|前端服务器负载平衡器  |443  |HTTPS  |
|前端服务器负载平衡器  |8080  |TCP-从前端服务器的根证书的客户端和设备检索-客户端和设备通过 NTLM 身份验证  |
|前端服务器负载平衡器  |端口 4443  |HTTPS（来自反向代理）  |
|控制器负载平衡器  |443  |HTTPS  |
|控制器负载平衡器  |端口 4443  |HTTPS（来自反向代理）  |

**所需客户端端口**

|组件|端口|协议|备注|
|:-----|:-----|:-----|:-----|
|客户端  |67/68  |DHCP  |由 Skype 业务服务器来查找注册器 FQDN （也就是说，如果 DNS SRV 发生故障，且未配置手动设置）。  |
|客户端  |443  |TCP (TLS)  |用于外部用户访问的客户端到服务器 SIP 通信。  |
|客户端  |443  |TCP (PSOM/TLS)  |用于外部用户访问 Web 会议会话。  |
|客户端  |443  |TCP (STUN/MSTURN)  |用于外部用户访问 A/V 会话和媒体 (TCP)。  |
|客户端  |3478  |UDP (STUN/MSTURN)  |用于外部用户访问 A/V 会话和媒体 (UDP)。  |
|客户端  |5061  |TCP (MTLS)  |用于外部用户访问的客户端到服务器 SIP 通信。  |
|客户端  |6891-6901  |TCP  |使用 Skype 业务客户端和以前的客户端之间进行文件传输。  |
|客户端  |1024-65535\*  |TCP/UDP  |音频端口范围（最少需要 20 个端口）。  |
|客户端  |1024-65535\*  |TCP/UDP  |视频端口范围（最少需要 20 个端口）。  |
|客户端  |1024-65535\*  |TCP  |对等文件传输（对于会议文件传输，客户端使用 PSOM）。  |
|客户端  |1024-65535\*  |TCP  |应用程序共享。  |
|Aastra 6721ip 公用区域电话  <br/> Aastra 6725ip 桌面电话  <br/> HP 4110 IP Phone（公用区域电话）  <br/> HP 4120 IP Phone（桌面电话）  <br/> Polycom CX500 IP 公用区域电话  <br/> Polycom CX600 IP 桌面电话  <br/> Polycom CX700 IP 桌面电话  <br/> Polycom CX3000 IP 会议电话  |67/68  |DHCP  |列出的设备用于查找 Skype 业务服务器证书、 设置 FQDN 和注册器 FQDN。  |
   
\*若要配置为这些媒体类型的特定端口，请使用 CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled、 ClientMediaPort 和 ClientMediaPortRange parameters)。
  
> [!NOTE]
> 业务客户端的 Skype 的安装程序自动客户端计算机上创建所需的操作系统防火墙例外。 

> [!NOTE]
> 用于外部用户访问的端口所需的任何客户端必须顺序遍历组织的防火墙 （例如，任何外部通信或承载的其他组织的会议） 的方案。 
  
## <a name="ipsec-exceptions"></a>IPsec 例外

对于已经部署了 Internet 协议安全性 (IPsec)（请参阅 IETF RFC 4301-4309）的企业网络，必须在用于传送音频、视频和全景视频的端口范围内禁用 IPsec。提出此建议的动机是需要避免由于 IPsec 协商而在分配媒体端口时产生任何延迟。
  
下表介绍了建议采用的 IPsec 例外设置。 
  
**建议采用的 IPsec 例外**

|规则名称|源 IP|目标 IP|协议|源端口|目标端口|身份验证要求|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|A/V 边缘服务器内部入站  |任意  |A/V 边缘服务器内部  |UDP 和 TCP  |任何  |任何  |不进行身份验证  |
|A/V 边缘服务器外部入站  |任意  |A/V 边缘服务器外部  |UDP 和 TCP  |任何  |任何  |不进行身份验证  |
|A/V 边缘服务器内部出站  |A/V 边缘服务器内部  |任意  |UDP &amp; TCP  |任何  |任何  |不进行身份验证  |
|A/V 边缘服务器外部出站  |A/V 边缘服务器外部  |任意  |UDP 和 TCP  |任何  |任何  |不进行身份验证  |
|中介服务器入站  |任意  |中介  <br/> 服务器  |UDP 和 TCP  |任何  |任何  |不进行身份验证  |
|中介服务器出站  |中介  <br/> 服务器  |任意  |UDP 和 TCP  |任何  |任何  |不进行身份验证  |
|会议助理入站  |任意  |运行会议助理的前端服务器  |UDP 和 TCP  |任何  |任何  |不进行身份验证  |
|会议助理出站  |运行会议助理的前端服务器  |任意  |UDP 和 TCP  |任何  |任何  |不进行身份验证  |
|A/V 会议入站  |任意  |前端服务器  |UDP 和 TCP  |任何  |任何  |不进行身份验证  |
|A/V 会议出站  |前端服务器  |任意  |UDP 和 TCP  |任何  |任何  |不进行身份验证  |
|Exchange 入站  |任意  |Exchange 统一消息  |UDP 和 TCP  |任何  |任何  |不进行身份验证  |
|应用程序共享服务器入站  |任意  |应用程序共享服务器  |TCP  |任何  |任何  |不进行身份验证  |
|应用程序共享服务器出站  |应用程序共享服务器  |任意  |TCP  |任何  |任何  |不进行身份验证  |
|Exchange 出站  |Exchange 统一消息  |任意  |UDP 和 TCP  |任何  |任何  |不进行身份验证  |
|客户端  |任何  |任意  |UDP  |指定的媒体端口范围  |任意  |不进行身份验证  |
