---
title: Skype 会议室系统的可管理性和工具
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 阅读本主题，了解 Skype 会议室系统的管理工具。
ms.openlocfilehash: 81adbb93c71abc201d9099d86e8414a524d85dff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093546"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype 会议室系统的可管理性和工具
 
阅读本主题，了解 Skype 会议室系统的管理工具。
  
## <a name="administrative-portal"></a>管理门户

对于 Skype for Business Server 本地部署，可以使用 Skype 会议室系统管理门户在组织中主动管理和监视 Skype 会议室系统部署。
  
有关详细信息，请参阅以下文章：
  
- [在 Skype for Business Server 中部署 SRS v1 管理 Web 门户](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange 清单

- 确认已设置自动发现，并且内部 DNS A/CNAME 记录可用于 autodiscover.domain.com。
    
- Ping 自动发现 (例如 Ping Autodiscover.contoso.com) 。
    
- 使用 Microsoft Connectivity Analyzer 工具测试自动发现服务。 选择第一个测试"I can't log on with Office Outlook"。
    
- 如果会议室已有资源邮箱，请扩展 Skype 会议室系统帐户 (页面底部的示例脚本) 。
    
## <a name="skype-for-business-checklist"></a>Skype for Business 清单

- 运行以下工具：
    
  - Skype for Business 最佳做法分析器     
  - Excel (Skype for Business 运行状况分析工具)     
  - Skype for 业务连接 Analyzer 32 位或 64 位
    
- Review [Useful new troubleshooting and analysis tools for Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365). 确认你有 Skype for Business 池和 Office Web Apps 服务器，并且可以使用 Skype for Business 客户端共享 PowerPoint 平台。
    
- 如果会议室已有资源邮箱，请为 Skype for Business 启用该邮箱。
    
- 如果需要，请求为会议室 (DID) 电话号码，并更新 Active Directory 工具中的"常规电话"字段。
    
## <a name="network"></a>网络

- 请确保 Skype 会议室系统具有有线网络连接。
    
- 阅读 Skype for Business 网络规划指南。
    
- 从 Skype for Business 合作伙伴请求 Skype for Business 网络评估。
    
- 阅读 Excel) 中的 Skype for Business 运行状况分析工具中捕获 (数据。
    
- 运行网络分析工具。
    
- 运行预调用诊断工具。
    
## <a name="skype-room-system-security"></a>Skype 会议室系统安全性

Skype 会议室系统是一个嵌入系统，可以使用 Skype for Business 安全模型、权限管理和 SCOM 等管理工具完全集成在 Windows 部署中。 这些功能包括： 
  
- 防止在用户模式下写入磁盘的写入筛选器 
    
- 应用保险箱，可防止未经授权的应用运行。 在用户模式下禁用所有 USB 端口。
    
  - Skype 会议室系统硬件上没有标准应用或查看器。 所有内容都通过 HTTP 或 RDP 协议呈现。
    
  - 电脑运行 Windows Embedded Standard 7 操作系统。 所有硬件（包括设备）都由 OEM 合作伙伴提供。
    
  - AD DS (Active Directory 域服务的可选域) ，从而实现本地安全帐户管理和控制。
    
- 您还可以使用 Skype for Business 管理中心管理本地管理员帐户。
    
- Skype 会议室系统通过标准 Microsoft 更新过程进行更新。
    
- Skype 会议室系统与 Skype for Business 连接。
    
  - Skype for Business 将端到端加密和授权用于所有通信模式
    
  - Skype 会议室系统支持 Skype for Business 安全性和合规性标准。 有关详细信息[，请参阅 Plan for security in Skype For Business Server。](../../plan-your-deployment/security/security.md)
    
## <a name="license"></a>许可证

验证是否使用 KMS 激活软件。 如果是这样，你可能需要检查或添加 Skype for Business 客户端 KMS 密钥。 如果不使用 KMS，请为 Skype for Business 客户端 MAK 请求批量许可密钥。
  
## <a name="license-keys"></a>许可证密钥

Skype 会议室系统在后台运行 Skype for Business 桌面客户端。 如果 Skype 会议室系统是域成员，它将发现你的 KMS。  (并且如果具有批量许可 KMS 密钥，它将在系统) 。 批量许可还提供 MAK，在显示 xxxxx-xxxxx-xxxxx-xxxxx 时输入此 MAK。  (需要 Internet 访问权限才能使用 MAK（而不是 KMS) ）。 有关详细信息，请参阅 Volume activation of Office 2013。
  
- 若要输入 MAK 密钥，请转到 OEM 设置 \> SRS 许可工具。 单击“检查状态”。 当状态显示"产品未激活"时，输入密钥。
    
- 如果在激活期间收到一个错误，指出"软件许可服务报告产品密钥无效"，请验证：
    
  - 键输入正确。
    
  - 你输入了 Skype for Business MAK 密钥，而不是另一个密钥。
    
  - 系统可以访问 Internet。
    
- 可以通过电话激活，但必须先尝试使用 SRS 许可工具激活。 若要通过电话激活，请启动测试 (而不是测试呼叫，因为测试) 。 在"Office 激活向导"中，选择"电话激活"，致电 Microsoft，键入长号，然后输入响应。
    
## <a name="certificate-authority"></a>证书颁发机构

确认用于颁发 Office Web Apps Server 2013 证书的证书颁发机构在证书吊销列表属性中包含 HTTP 路径。
  
如果使用 Skype for Business Server， (.crt) 文件导入 Skype 会议室系统。 它很容易从 CA 服务器的 CertEnroll 共享，或在任何加入域的电脑的受信任的根文件夹中获取。
  
## <a name="certificates"></a>证书

验证证书颁发机构是否具有证书吊销列表的 http 路径。 如果没有，请更新 CA 以包含一个 CA。
  
在"系统设置证书管理器"下的 Skype 会议室系统的管理员设置 \> 中安装证书。 内部证书需要企业根 CA。
  
获取所需的证书的一种方式是发现颁发证书的 CA。 对于 Skype for Business Server，在 Skype for Business 中的电脑上，单击"设置 \> ""工具 \> ""电话拨入式会议设置"。 这将打开由颁发内部证书的 CA 保护的网页。 单击浏览器地址栏上的"锁定"图标以显示安全报告。 单击"查看证书"并检查 CRL 分发点属性。 第二个 CN 参数应为 CA 的服务器名称。 现在打开该地址 \\ \< CA Server Name \> \CertEnroll 的 Windows 资源管理器。 将两个 .crl 文件和 .crt 文件复制到闪存驱动器，并放在 SMART 板的左侧。
  
将 .crt 文件导入到"受信任的会议室证书颁发机构"文件夹下的 Skype 会议室系统。
  
在 Skype 会议室系统中的中间证书颁发机构文件夹下导入 .crl 文件。  (你需要将证书管理器中的文件扩展名筛选器更改为 .crl，以查看) 。
  
注意：Office Web Apps 2013 服务器可能与 Skype for Business 共享同一 CA。 如果没有，你将无法在会议中共享 PowerPoint。 与 IT 核实，从 CA 网络共享 CertEnroll 获取 CRT 和 CRL 文件，如上所述。 
  
域成员身份可以简化一些操作，因为你可以将 Skype 会议室系统视为 Windows 系统，并且它可以依赖 Active Directory 来了解某些证书方面。 但是，最好手动管理它。
