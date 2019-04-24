---
title: Skype 会议室系统可管理性和工具
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 阅读本主题，了解适用于 Skype 会议室系统的管理工具。
ms.openlocfilehash: 9be385030ad09e73608b461c5a0c05cea70987c0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219400"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype 会议室系统可管理性和工具
 
阅读本主题，了解适用于 Skype 会议室系统的管理工具。
  
## <a name="administrative-portal"></a>管理门户

对于业务服务器的本地部署的 Skype，您可以使用 Skype 会议室系统管理门户主动管理和监视组织内的 Skype 会议室系统部署。
  
请参阅以下文章，获取更多详细信息：
  
- [为业务服务器部署中 Skype SR v1 管理 Web 门户](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

Skype 会议室系统可以监控通过 System Center Operations Manager (SCOM) 通过下载[Skype 会议室系统管理包](https://www.microsoft.com/download/details.aspx?id=42320)和 SCOM 服务器上安装它。 您可以使用 SCOM 设置通知、 监视 Skype 会议室系统的运行状况、 生成正常运行时间报告以及更多。 Skype 会议室系统附带的可配置为指向 SCOM 服务器的预安装监控代理。 请参阅 Skype 会议室系统制造商提供的安装指南了解如何配置 Skype 会议室系统上的监控代理。
  
## <a name="exchange-checklist"></a>Exchange 清单

- 确认已设置自动发现并且内部 DNS A/CNAME 记录可用于 autodiscover.domain.com。
    
- Ping 自动发现（例如，Ping Autodiscover.contoso.com）。
    
- 使用 Microsoft Connectivity Analyzer 工具测试你的自动发现服务。 选择第一个测试，"我不能登录与 Office Outlook。"
    
- 如果已资源邮箱会议室，扩展此帐户的 Skype 会议室系统 （页面底部的示例脚本）。
    
## <a name="skype-for-business-checklist"></a>Skype 的业务清单

- 运行以下工具：
    
  - 业务最佳做法分析器的 Skype     
  - Skype 业务运行状况分析工具 (Excel)    
  - Skype 用于 Business Connectivity Analyzer 32 位或 64 位
    
- 查看[有用的新疑难解答和分析工具，用于 Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)。 确认您具有业务池和 Office Web Apps server Skype 并可以共享 PowerPoint 系列时使用 for Business 客户端的 Skype。
    
- 如果已资源邮箱会议室，启用它 for Business 的 Skype。
    
- 如果需要，请为会议室系统请求 DID（电话号码）并在 Active Directory 工具中更新“常规电话”字段。
    
## <a name="network"></a>网络

- 请确保 Skype 会议室系统具有有线的网络连接。
    
- 阅读 for Business 的规划指南 Skype 网络。
    
- 从业务合作伙伴 Skype 请求业务网络评估 Skype。
    
- 通读 Skype 中捕获的业务运行状况分析工具 (Excel) 的性能数据。
    
- 运行网络分析工具。
    
- 运行预呼叫诊断工具。
    
## <a name="skype-room-system-security"></a>Skype 会议室 System 安全

Skype 会议室系统是嵌入的系统，可以完全集成在 Windows 部署中，使用 Skype 业务安全模型、 权限管理和管理工具，如 SCOM。 功能包括：
  
- 写入筛选器，可防止磁盘在用户模式下写入 
    
- 应用锁定器，可防止未经授权的应用运行。在用户模式下，所有 USB 端口都被禁用。
    
  - 没有标准的应用程序或查看者驻留在 Skype 会议室系统硬件上。 所有内容都是通过 HTTP 或 RDP 协议呈现的。
    
  - 家用电脑运行 Windows Embedded Standard 7 操作系统。所有硬件（包括设备）都由 OEM 合作伙伴提供。
    
  - 选择性地将域加入到 Active Directory 域服务 (AD DS)，实现本地安全帐户管理和控制。
    
- 您还可以管理业务管理中心的使用 Skype 的本地管理员帐户。
    
- Skype 会议室系统是通过标准 Microsoft 更新过程进行了更新。
    
- Skype 会议室系统连接和 Skype 的业务。
    
  - Skype for Business 用于所有通信模式的端到端加密和授权
    
  - Skype 会议室系统支持业务安全性和遵从性标准 Skype。 有关详细信息，请参阅[规划 Skype 的业务 Server 中的安全性](../../plan-your-deployment/security/security.md)。
    
## <a name="license"></a>许可证

验证你是否可以使用 KMS 激活软件。 如果是这样，您可能需要检查或向其添加业务客户端 KMS 密钥 Skype。 如果您不使用 KMS，则请求批量许可密钥的业务客户端 MAK Skype。
  
## <a name="license-keys"></a>许可证密钥

Skype 会议室系统在后台运行业务桌面客户端 Skype。 如果 Skype 会议室系统是域成员，它将发现您的 KMS。 （和批量授权 KMS 密钥，如果将自动激活）。 ）批量许可也提供 MAK，当你输入时，它将显示 xxxxx-xxxxx-xxxxx-xxxxx。 （你需要 Internet 访问才能使用 MAK 而不是 KMS 激活。 ）有关详细信息，请参阅“Office 2013 的批量激活”。
  
- 若要输入 MAK 密钥，请转到 OEM 设置\>SR 许可工具。 单击“检查状态”。 当该状态将显示"产品未激活"时，输入密钥。
    
- 如果在激活过程中出现一条错误消息，"软件许可服务报告的产品密钥无效，"然后验证：
    
  - 正确输入密钥。
    
  - 您输入 Skype 业务 MAK 密钥和不另一个键。
    
  - 系统具有 Internet 访问。
    
- 你可以通过电话激活，但是必须首先已尝试使用 SRS 许可工具激活。 要通过电话激活，请启动测试会议（而不是测试呼叫，因为测试呼叫时间太短）。 在 Office 激活向导中，选择电话激活、 呼叫 Microsoft、 键入长的数字，和输入响应。
    
## <a name="certificate-authority"></a>证书颁发机构

确认用于颁发 Office Web Apps Server 2013 证书的证书颁发机构在证书吊销列表中包括 HTTP 路径。
  
如果对业务服务器使用 Skype 到 Skype 会议室系统导入证书文件 (.crt)。 可轻松地从 CA 服务器的 CertEnroll 共享中或者在任何加入域的电脑的“受信任的根”文件夹中获得。
  
## <a name="certificates"></a>证书

验证你的证书颁发机构是否具有证书吊销列表的 http 路径。如果没有，请更新你的 CA 以包括该路径。
  
在系统设置下的 Skype 会议室系统管理员安装中安装证书\>证书管理器。 你需要你的内部证书的企业根 CA。
  
获取所需证书的一种方法是发现颁发你的证书的 CA。 单击设置的企业服务器，在 Skype for Business，PC 上的 Skype\>工具\>电话拨入式会议设置。 这将打开网页保护颁发内部证书的 CA。 单击浏览器地址栏上的锁图标以显示安全报告。 单击“查看证书”并检查“CRL 分布点”属性。 第二个 CN 参数应为 CA 的服务器名称。 现在该地址打开 Windows 资源管理器\\ \< CA 服务器名\>\CertEnroll。 请将两个 .crl 文件和 .crt 文件复制到 U 盘，并将其放在智能白板的左侧。
  
导入受信任的会议室证书颁发机构文件夹下 Skype 会议室系统.crt 文件。
  
导入中间证书颁发机构文件夹下 Skype 会议室系统上的.crl 文件。 （您需要将证书管理器中的文件扩展名筛选器更改为.crl 以查看文件）。
  
注意： Office Web Apps 2013 服务器可以共享同一个 CA 为 for Business 的 Skype。 如果不是，那么你将无法在会议中共享 PowerPoint 演示文稿。 请与 IT 核实，并按上面所述从 CA 网络共享 CertEnroll 获取 CRT 和 CRL 文件。 
  
域成员身份可以简化的事情，因为视为 Windows 系统 Skype 会议室系统，它可以依赖 Active Directory 的一些方面证书。 但是，最好是手动管理它。
  

