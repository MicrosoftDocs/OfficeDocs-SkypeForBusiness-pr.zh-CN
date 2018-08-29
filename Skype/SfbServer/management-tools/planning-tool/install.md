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
description: 之前开始设计和使用 Skype 业务 Server 2015 规划工具规划您 Skype 业务服务器 2015年基础结构，您必须首先安装规划工具。 规划工具不需要部署到的工作站或服务器的域或基础结构的一部分打算为业务服务器 2015年安装 Skype。 该规划工具附带的自述文件详细介绍有关安装和使用该工具的重要信息。 自述文件中的信息的一些为清楚起见此处重复。
ms.openlocfilehash: 2314a9ae548bea70bc13872714ae3215d7439eec
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244321"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中安装规划工具

之前开始设计和使用 Skype 业务 Server 2015 规划工具规划您 Skype 业务服务器 2015年基础结构，您必须首先安装规划工具。 规划工具不需要部署到的工作站或服务器的域或基础结构的一部分打算为业务服务器 2015年安装 Skype。 该规划工具附带的自述文件详细介绍有关安装和使用该工具的重要信息。 自述文件中的信息的一些为清楚起见此处重复。

> [!IMPORTANT]
> 规划工具需要安装在其上安装该工具的计算机上具有管理员权限的用户。

安装和操作的规划工具支持的操作系统包括：

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7 32 位版本

- Windows 7，使用 Windows on Win32 (WOW) 的 64 位版本

- Windows Server 2008 R2，使用 WOW

此外，规划工具需要 Microsoft.NET Framework 4.5。

满足安装前要求后，您可以安装规划工具。



## <a name="to-install-the-planning-tool"></a>安装规划工具

1. 以 Administrators 组成员的身份登录本地计算机。

2. 使用 Windows 资源管理器或命令窗口，找到您下载的规划工具安装文件的目录。

3. 找到 SkypeForBusinessPlanningTool.msi。在 Windows 资源管理器中双击该文件。在命令窗口中，键入文件的名称，然后按 **Enter** 运行该文件。

4. 在“**Skype for Business Server 2015 规划工具安装向导**”的“欢迎”页上，单击“**下一步**”。

5. 查看“**最终用户许可协议**”，如果选择接受许可协议中的使用条款，则选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。

6. 选择安装规划工具文件的位置。默认位置是 C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool。如果要更改安装位置，请单击“**更改**”。在“**更改目标文件夹**”上，浏览或键入要安装这些文件的位置，单击“**确定**”，然后单击“**下一步**”。

7. 安装程序现在已准备好安装规划工具。 单击“安装”**** 开始安装过程。

8. 将开始安装，并将显示进度。成功完成安装后，单击“**完成**”。

9. 规划工具可供使用。

## <a name="optional-software"></a>Optional Software
<a name="Optional_Software"> </a>

业务 Server 2015 规划工具的 Skype 旨在导出到 Microsoft Excel 中，Microsoft Visio。 不需要规划工具的操作这些应用程序时，大量值添加到部署和设计的文档。

### <a name="microsoft-excel"></a>Microsoft Excel

将设计导出到 Microsoft Excel 时会创建一个报告，该报告在电子表格中显示 7 个选项卡：

- 摘要-显示有关站点配置的信息，包括用户计数、 容量设置和服务器配置文件信息。

- 硬件配置文件-推荐的硬件配置的拓扑，其中包括 CPU、 内存、 磁盘和网络接口中指定的服务器上显示的报告。 还包括服务器组件的数量和推荐规格。 此外，还按站点定义了每台服务器，以按站点提供服务器要求的完整描述。

- 端口要求-向域名系统负载平衡 （DNS 磅） 和硬件负载平衡器 (HLB) 显示所有已启用的端口和关联的报告。 应使用此报告规划防火墙以及 DNS LB 和 HLB 配置。

- 摘要报告-显示所需设置边缘服务器网络的设置的常规摘要。

- 证书报告-显示的使用者名称和所需的获取运行的边缘服务器所需的证书的使用者替代名称。

- 防火墙报告-显示为外部和内部接口的源和目标端口和 IP 地址。

- DNS 报告-显示的完全限定的域名 (FQDN) 和 IP/VIP 地址所需的每个 DNS 条目您创建。

### <a name="microsoft-visio"></a>Microsoft Visio

将设计导出到 Microsoft Visio 会创建在配置的拓扑和基础结构的文档中使用的图。您可以编辑和重新排列导入的图以满足文档需求。典型的 Visio 图包括：

> [!NOTE]
> 如果您的设计足够大，需要三个以上前端服务器，对于前端池，前端服务器，运行 SQL Server、 IP 地址和 Fqdn 的计算机将创建的其他页。

- 全局拓扑-业务服务器 2015年网站配置 Skype 的关系图。

- 网站名称选项卡-显示站点配置拓扑与边缘服务器、 防火墙、 公共交换电话交换网 (PSTN) 网关，与内部服务器部署。 内部部署由包含配置的服务器和池包括前端池，基于 SQL Server 的服务器，Active Directory 域服务，控制器 Exchange 统一消息 (UM) 服务器、 Exchange 邮箱服务器 Office Web Apps 服务器，中介服务器和持久聊天服务器。

- 边缘网络图-图详述边缘服务器配置关联的 IP 地址和 Fqdn。 还包括 DNS 负载平衡和硬件负载平衡器。 此外，控制器和前端服务器或前端池，以显示关联的 DNS 磅或 HLB 和分配 （规划工具支持 IPv4 和 IPv6 地址） 的 IP 地址和 FQDN。

## <a name="see-also"></a>另请参阅
<a name="Optional_Software"> </a>

[安装规划工具](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)