---
title: 最佳做法分析器的概述
TOCTitle: 最佳做法分析器的概述
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg591349(v=OCS.15)
ms:contentKeyID: 49314200
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 最佳做法分析器的概述

 

_**上一次修改主题：** 2012-09-19_

您可以使用 Lync Server 2013 最佳做法分析器来识别和解决 Lync Server 2013 部署的问题。Lync Server 2013 最佳做法分析器从 Lync Server 2013 组件收集配置信息。

通过适当的网络访问，最佳做法分析器可以检查正在运行 Active Directory 域服务、Exchange Server 统一消息 (UM) 以及 Lync Server 2013 的服务器。您可以使用最佳做法分析器 Best Practices Analyzer 执行以下操作：

  - 主动执行检查，以验证是否按照建议的最佳做法设置配置。

  - 自动检测 Lync Server 2013 的必需更新。

  - 生成问题列表，例如不够理想的配置设置、不支持的选项、缺少更新或我们不建议的做法等问题。

  - 帮助您排除和修复具体问题。

最佳做法分析器提供以下功能：

  - 极低的安装先决条件。

  - 关于已报告问题的联机文档，包括疑难解答提示。

  - 可以保存供以后查看的配置信息。

  - 最先进的系统分析。

最佳做法分析器使用一组 XML 配置文件来确定从 Lync Server 2013 环境收集的信息。除了检查 Active Directory 域服务外，还检查 Windows Server 操作系统注册表以及 Windows Management Instrumentation (WMI) 中的设置等源。

最佳做法分析器将其收集的数据与 Lync Server 2013 部署设置和配置的一组预定义规则进行比较。

将收集的数据与预定义规则比较后，该工具会报告问题。对于其报告的每个问题，最佳做法分析器都会提供在扫描的 Lync Server 2013 环境中找到的相关信息以及建议配置。最佳做法分析器还提供有关具体问题详细信息的链接。

> [!NOTE]  
> Lync Server 2013 最佳做法分析器仅从 Lync Server 2013 组件收集配置信息。您可以使用该工具的早期版本扫描以前的环境。有关详细信息，请参阅<a href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">运行最佳做法分析器的要求</a>。


