---
title: 在 Skype for Business Server 2015 中安装规划工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: 使用 Skype for Business Server 2015 计划工具开始设计和规划 Skype for business Server 2015 基础结构之前，必须首先安装规划工具。 规划工具不需要部署到属于你计划安装 Skype for Business Server 2015 的域或基础结构的一部分的工作站或服务器。 规划工具附带的自述文件详细介绍了有关安装和使用该工具的重要信息。 Some of the information in the Readme file is duplicated here for clarity.
ms.openlocfilehash: 29cadae219faadb68a8a027de11309efc8e3f10b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816381"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中安装规划工具

使用 Skype for Business Server 2015 计划工具开始设计和规划 Skype for business Server 2015 基础结构之前，必须首先安装规划工具。 规划工具不需要部署到属于你计划安装 Skype for Business Server 2015 的域或基础结构的一部分的工作站或服务器。 规划工具附带的自述文件详细介绍了有关安装和使用该工具的重要信息。 Some of the information in the Readme file is duplicated here for clarity.

> [!IMPORTANT]
> 规划工具要求在安装该工具的计算机上具有管理员权限和权限的用户进行安装。

规划工具的安装和操作支持的操作系统包括：

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7 32 位版本

- Windows 7，使用 Windows on Win32 (WOW) 的 64 位版本

- Windows Server 2008 R2，使用 WOW

此外，规划工具需要 Microsoft .NET Framework 4.5。

满足预安装要求后，即可安装规划工具。



## <a name="to-install-the-planning-tool"></a>安装规划工具

1. 以 Administrators 组成员的身份登录本地计算机。

2. 使用 Windows 资源管理器或命令窗口，找到您下载规划工具安装文件的目录。

3. 找到 SkypeForBusinessPlanningTool.msi。在 Windows 资源管理器中双击该文件。在命令窗口中，键入文件的名称，然后按 **Enter** 运行该文件。

4. 在“**Skype for Business Server 2015 规划工具安装向导**”的“欢迎”页上，单击“**下一步**”。

5. 查看“**最终用户许可协议**”，如果选择接受许可协议中的使用条款，则选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。

6. 选择安装规划工具文件的位置。默认位置是 C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool。如果要更改安装位置，请单击“**更改**”。在“**更改目标文件夹**”上，浏览或键入要安装这些文件的位置，单击“**确定**”，然后单击“**下一步**”。

7. 安装程序现在已准备好安装规划工具。 单击“安装”**** 开始安装过程。

8. 将开始安装，并将显示进度。 成功完成安装后，单击“**完成**”。

9. 规划工具可供使用。

## <a name="optional-software"></a>可选软件
<a name="Optional_Software"> </a>

Skype for Business Server 2015 规划工具旨在导出到 Microsoft Excel 和 Microsoft Visio。 虽然这些应用程序不是规划工具运行所必需的，但它们确实为设计的部署和文档增加了重要价值。

### <a name="microsoft-excel"></a>Microsoft Excel

将设计导出到 Microsoft Excel 时会创建一个报告，该报告在电子表格中显示 7 个选项卡：

- 摘要-显示有关网站配置的信息，包括用户计数、容量设置和服务器配置文件信息。

- 硬件配置文件-显示针对拓扑中指定的服务器的推荐硬件配置（包括 CPU、内存、磁盘和网络接口）的报告。 还包括服务器组件的数量和推荐规格。 此外，还按站点定义了每台服务器，以按站点提供服务器要求的完整描述。

- 端口要求-显示已启用的所有端口以及与域名系统负载平衡（DNS LB）和硬件负载平衡器（HLB）的关联的报告。 应使用此报告规划防火墙以及 DNS LB 和 HLB 配置。

- 摘要报告-显示设置边缘服务器网络所需设置的一般摘要。

- 证书报告-显示用于获取运行边缘服务器所需证书的主题名称和主题备用名称。

- 防火墙报告-显示外部接口和内部接口的源和目标端口以及 IP 地址。

- DNS 报告-显示你创建的每个 DNS 条目所需的完全限定的域名（FQDN）和 IP/VIP 地址。

### <a name="microsoft-visio"></a>Microsoft Visio

将设计导出到 Microsoft Visio 会创建在配置的拓扑和基础结构的文档中使用的图。您可以编辑和重新排列导入的图以满足文档需求。典型的 Visio 图包括：

> [!NOTE]
> 如果你的设计足够大，需要超过三个前端服务器，将为前端池、前端服务器、运行 SQL Server 的计算机、IP 地址和 Fqdn 创建一个额外页面。

- 已配置 Skype for business Server 2015 网站的全局拓扑图。

- "网站名称" 选项卡-显示 "边缘服务器"、"防火墙"、"公共交换电话网络" （PSTN）和内部服务器部署的站点配置拓扑。 内部部署包括配置的服务器和池，包括前端池、基于 SQL Server 的服务器、Active Directory 域服务、控制器、Exchange 统一消息（UM）服务器、Exchange 邮箱服务器、Office Web Apps 服务器中介服务器和持久聊天服务器。

- 边缘网络图-详细介绍边缘服务器配置以及关联的 IP 地址和 Fqdn 的图表。 还包括 DNS 负载平衡和硬件负载平衡器。 此外，将显示 Director 和前端服务器或前端池，其中关联的 DNS LB 或 HLB 以及分配的 IP 地址（计划工具支持 IPv4 和 IPv6 地址）和 FQDN。

## <a name="see-also"></a>另请参阅
<a name="Optional_Software"> </a>

[Installing the Planning Tool](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
