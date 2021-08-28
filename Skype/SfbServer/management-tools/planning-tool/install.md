---
title: 在 2015 年 Skype for Business Server安装规划工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: 在使用 Skype for Business Server 2015 规划工具开始设计和规划 Skype for Business Server 2015 基础结构之前，必须先安装规划工具。 规划工具无需部署到工作站或服务器，该工作站或服务器是计划安装 2015 年 Skype for Business Server 的一部分。 规划工具随附的自述文件详细介绍了有关安装和使用该工具的重要信息。 为明确起见，此处复述了自述文件中的某些信息。
ms.openlocfilehash: 2cfa5e67d567c108d46db1bc52b5426971aa8ca8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616508"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>在 2015 年 Skype for Business Server安装规划工具

在使用 Skype for Business Server 2015 规划工具开始设计和规划 Skype for Business Server 2015 基础结构之前，必须先安装规划工具。 规划工具无需部署到工作站或服务器，该工作站或服务器是计划安装 2015 年 Skype for Business Server 的一部分。 规划工具随附的自述文件详细介绍了有关安装和使用该工具的重要信息。 为明确起见，此处复述了自述文件中的某些信息。

> [!IMPORTANT]
> 规划工具要求具有管理员权限的用户在要安装该工具的计算机上进行安装。

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

满足预安装要求后，可以安装规划工具。



## <a name="to-install-the-planning-tool"></a>安装规划工具

1. 以以下组的成员登录到本地管理员组。

2. 使用Windows资源管理器或命令窗口，找到下载规划工具安装文件的目录。

3. 找到SkypeForBusinessPlanningTool.msi。 在Windows资源管理器"中，双击该文件。 在命令窗口中，键入文件的名称，然后按 **Enter** 运行该文件。

4. 在 **2015 Skype for Business Server"** 规划工具安装向导"的"欢迎"页上，单击"下一 **步"。**

5. 查看 **“最终用户许可协议”**，如果选择接受许可协议中的使用条款，则选择 **“我接受许可协议中的条款”**，然后单击 **“下一步”**。

6. 选择安装规划工具文件的位置。 默认位置为 C：\Program Files (x86) \Skype for Business Server 2015\Planning Tool。 如果要更改安装位置，请单击 **“更改”**。 在 **“更改目标文件夹”** 上，浏览或键入要安装这些文件的位置，单击 **“确定”**，然后单击 **“下一步”**。

7. 安装程序现在已准备好安装规划工具。 单击 **“安装”** 开始安装过程。

8. 将开始安装，并将显示进度。成功完成安装后，单击 **“完成”**。

9. 规划工具可供使用。

## <a name="optional-software"></a>可选软件
<a name="Optional_Software"> </a>

The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio. 虽然这些应用程序不是运行规划工具所需的，但是它们为您的设计的部署和文档增加了重要价值。

### <a name="microsoft-excel"></a>Microsoft Excel

将设计导出到Microsoft Excel可创建一个在电子表格中显示七个选项卡的报表：

- 摘要 - 显示有关站点配置的信息，包括用户计数、容量设置和服务器配置文件信息。

- 硬件配置文件 - 显示拓扑中指定的服务器的建议硬件配置的报告，包括 CPU、内存、磁盘和网络接口。 还包括服务器组件的数量和推荐规范。 此外，每个服务器都由网站定义，以便按网站提供服务器要求的完整表示形式。

- 端口要求 - 显示所有已启用的端口的报告，以及域名系统负载平衡 (DNS LB) 和硬件负载平衡器与 HLB (的) 。 应使用此报告规划防火墙以及 DNS LB 和 HLB 配置。

- 摘要报告 - 显示设置边缘服务器网络所需的设置的常规摘要。

- 证书报告 - 显示使边缘服务器运行所需的证书所需的主题名称和主题备用名称。

- 防火墙报告 - 显示外部接口和内部接口的源端口和目标端口以及 IP 地址。

- DNS 报告 - 显示您创建的每个 DNS (所需的 FQDN) IP/VIP 地址的完全限定域名。

### <a name="microsoft-visio"></a>Microsoft Visio

将设计导出到 Microsoft Visio会创建一个图表，用于所配置拓扑和基础结构的文档目的。 可以编辑和重新排列导入的图表以满足文档需求。 典型的Visio包括：

> [!NOTE]
> 如果您的设计足够大，需要三台以上前端服务器，将为前端池、前端服务器、运行 SQL Server 的计算机、IP 地址和 FQDN 创建一个附加页面。

- 全局拓扑 - 2015 Skype for Business Server配置图。

- "站点名称"选项卡 - 显示具有边缘服务器、防火墙、公用电话交换网 (PSTN) 网关和内部服务器部署的站点配置拓扑。 内部部署包含已配置的服务器和池，包括前端池、基于 SQL Server 的服务器、Active Directory 域服务、控制器、Exchange 统一消息 (UM) 服务器、Exchange 邮箱服务器、Office Web Apps 服务器、中介服务器和持久聊天服务器。

- 边缘网络图 - 详细说明具有关联 IP 地址和 FQDN 的边缘服务器配置的图表。 还包括 DNS 负载平衡和硬件负载平衡器。 此外，还显示控制器和前端服务器或前端池，以及关联的 DNS LB 或 HLB 以及分配的 IP 地址 (规划工具支持 IPv4 和 IPv6 地址) 和 FQDN。

## <a name="see-also"></a>另请参阅
<a name="Optional_Software"> </a>

[安装规划工具](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)