---
title: 在 Skype for Business Server 2015 中安装规划工具
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: 之前开始设计和规划您 Skype 业务服务器 2015年基础结构通过 Skype 业务服务器 2015年规划工具，您必须首先安装规划工具。 规划工具不需要将其部署到工作站或服务器是域或基础结构的一部分打算用来为业务服务器 2015年安装 Skype。 该规划工具附带的自述文件详细说明了有关安装和使用此工具的重要信息。 一些自述文件中的信息为清楚起见在这里重复。
ms.openlocfilehash: 1c5c56031890aaff035e237e2ff7ab6d89d6ba2b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中安装规划工具
 
之前开始设计和规划您 Skype 业务服务器 2015年基础结构通过 Skype 业务服务器 2015年规划工具，您必须首先安装规划工具。 规划工具不需要将其部署到工作站或服务器是域或基础结构的一部分打算用来为业务服务器 2015年安装 Skype。 该规划工具附带的自述文件详细说明了有关安装和使用此工具的重要信息。 一些自述文件中的信息为清楚起见在这里重复。
  
> [!IMPORTANT]
> 规划工具需要具有管理员权利和权限的工具是要安装的计算机上的用户可以安装。 
  
安装和操作规划工具的受支持的操作系统包括：
  
- Windows 10 
    
- Windows 8
    
- Windows 8.1
    
- Windows Server 2012
    
- Windows Server 2012 R2
    
- Windows 7 32 位版本
    
- Windows 7，使用 Windows on Win32 (WOW) 的 64 位版本
    
- Windows Server 2008 R2，使用 WOW
    
此外，规划工具需要 Microsoft.net 4.5。
  
预安装要求都满足后，您可以安装规划工具。
  
## 

### <a name="to-install-the-planning-tool"></a>安装规划工具

1. 以 Administrators 组成员的身份登录本地计算机。
    
2. 使用 Windows 资源管理器或命令窗口，找到规划工具安装文件的下载到其中的目录。
    
3. 找到 SkypeForBusinessPlanningTool.msi。在 Windows 资源管理器中双击该文件。在命令窗口中，键入文件的名称，然后按 **Enter** 运行该文件。
    
4. 在“**Skype for Business Server 2015 规划工具安装向导**”的“欢迎”页上，单击“**下一步**”。
    
5. 查看“**最终用户许可协议**”，如果选择接受许可协议中的使用条款，则选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。
    
6. 选择安装规划工具文件的位置。默认位置是 C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool。如果要更改安装位置，请单击“**更改**”。在“**更改目标文件夹**”上，浏览或键入要安装这些文件的位置，单击“**确定**”，然后单击“**下一步**”。
    
7. 安装程序现在就可以安装规划工具。 单击“安装”****开始安装过程。
    
8. 将开始安装，并将显示进度。成功完成安装后，单击“**完成**”。
    
9. 规划工具可供使用。
    
## <a name="optional-software"></a>Optional Software
<a name="Optional_Software"> </a>

旨在将导出到 Microsoft Excel，Microsoft Visio 业务服务器 2015年计划工具 Skype。 虽然这些应用程序并不需要的规划工具的操作，他们不要部署与您的设计文档添加重要的价值。
  
### <a name="microsoft-excel"></a>Microsoft Excel

将设计导出到 Microsoft Excel 时会创建一个报告，该报告在电子表格中显示 7 个选项卡：
  
- 摘要-显示在站点配置的信息包括用户数、 产能设置和服务器的配置文件信息。
    
- 硬件配置文件-推荐的硬件配置拓扑，包括 CPU、 内存、 磁盘和网络接口中指定的服务器上显示一份报告。 还包括服务器组件的数量和推荐规格。 此外，还按站点定义了每台服务器，以按站点提供服务器要求的完整描述。
    
- 端口要求-域名系统负载平衡 （DNS 磅） 和硬件负载平衡器 (HLB) 中显示所有已启用的端口和关联的报告。 应使用此报告规划防火墙以及 DNS LB 和 HLB 配置。
    
- 摘要报告-显示一般需要设置边缘服务器网络设置的摘要。
    
- 证书报告-显示一个使用者名称和主题备用名称所需的边缘服务器运行所需的证书。
    
- 防火墙报告-显示为内部和外部接口的源和目标端口和 IP 地址。
    
- DNS 报告-显示完全限定的域名 (FQDN) 和 IP/VIP 地址所需的每个 DNS 条目，您可以创建。
    
### <a name="microsoft-visio"></a>Microsoft Visio

将设计导出到 Microsoft Visio 会创建在配置的拓扑和基础结构的文档中使用的图。您可以编辑和重新排列导入的图以满足文档需求。典型的 Visio 图包括：
  
> [!NOTE]
> 如果您的设计是足够大，需要多三个前端服务器，则将为前端池，前端服务器，运行 SQL Server、 IP 地址和 Fqdn 的计算机创建附加的页面。 
  
- 全局拓扑-业务服务器 2015年站点配置 Skype 的关系图。
    
- 站点名称选项卡 — 显示站点配置拓扑与边缘服务器、 防火墙、 公共交换电话网络 (PSTN) 的网关和内部服务器部署。 内部部署包括配置的服务器和池，包括前端池，基于 SQL Server 的服务器，Active Directory 域服务，董事 Exchange 统一消息 (UM) 服务器和 Exchange 邮箱服务器，Office Web 应用程序服务器，中介服务器和持久聊天服务器。
    
- 边缘在网络图中的关系图详细记录具有关联的 IP 地址和 Fqdn 的边缘服务器配置。 还包括 DNS 负载平衡和硬件负载平衡器。 此外，控制器和前端服务器或前端池，以显示关联的 DNS 磅或 HLB （规划工具支持 IPv4 和 IPv6 地址） 分配的 IP 地址和 FQDN。
    
## <a name="see-also"></a>另请参阅
<a name="Optional_Software"> </a>

#### 

[安装规划工具](http://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)

