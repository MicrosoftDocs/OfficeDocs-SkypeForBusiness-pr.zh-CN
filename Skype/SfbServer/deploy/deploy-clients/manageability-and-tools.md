---
title: Skype 会议室系统可管理性和工具
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 阅读本主题，了解适用于 Skype 会议室系统的管理工具。
ms.openlocfilehash: c18c8a1e8f4580551dc809d3a8cedbf6f6a3fbfa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype 会议室系统可管理性和工具
 
阅读本主题，了解适用于 Skype 会议室系统的管理工具。
  
## <a name="administrative-portal"></a>管理门户

为 Skype 业务服务器内部部署，可以使用 Skype 的空间系统管理门户来主动管理和监视 Skype 的空间系统部署您的组织中。
  
有关更多详细信息，请参阅以下文章：
  
- [Lync Server 2013 的 Lync 室系统管理 Web 门户部署](http://technet.microsoft.com/library/ecba5b36-632e-40b9-9c2e-ab825baf7a46.aspx)
    
- [Lync 室系统管理 Web 门户的配置 Lync Server 2013 环境](http://technet.microsoft.com/library/1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2.aspx)
    
- [在 Lync Server 2013 安装 Lync 室系统管理 Web 门户](http://technet.microsoft.com/library/dd19e368-c338-4e21-a40d-6439d46a9748.aspx)
    
- [在 Lync Server 2013 使用 Lync 室系统管理 Web 门户](http://technet.microsoft.com/library/c387b2a3-3e42-4642-af72-88126ed2820f.aspx)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

Skype 的空间系统可以通过下载[Skype 的空间系统管理包](https://www.microsoft.com/en-us/download/details.aspx?id=42320)并将其安装在 SCOM 服务器上监视系统中心操作管理器 (SCOM) 通过。 SCOM 可用于设置警报、 监控其运行状况的 Skype 的空间系统，生成正常运行时间报告，以及更多。 Skype 的空间系统带有可配置为指向 SCOM 服务器预安装监视 agent。 请参阅 Skype 的空间系统制造商提供的安装指南了解如何配置上 Skype 的空间系统的监视代理。
  
## <a name="exchange-checklist"></a>Exchange 清单

- 确认已设置自动发现并且内部 DNS A/CNAME 记录可用于 autodiscover.domain.com。
    
- Ping 自动发现（例如，Ping Autodiscover.contoso.com）。
    
- 使用 Microsoft Connectivity Analyzer 工具测试你的自动发现服务。 选择第一个测试中，"我不能登录使用 Outlook"。
    
- 如果会议室已经对 Skype 的空间系统 （示例脚本在页面的底部） 扩展此帐户的资源邮箱。
    
## <a name="skype-for-business-checklist"></a>Skype 业务检查表

- 运行以下工具：
    
  - Skype 的商业最佳实践分析工具 
    
  - Skype 业务运行状况分析工具 (Excel) 
    
  - Skype 业务连接分析器 32 位或 64 位
    
- 查看[有用新故障诊断和分析工具，用于 Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)。 确认有 Skype 业务池和 Office Web 应用程序服务器，并且可以共享的业务客户端使用 Skype PowerPoint 幻灯片。
    
- 会议室已有资源邮箱，如果 Skype 业务为启用。
    
- 如果需要，请为会议室系统请求 DID（电话号码）并在 Active Directory 工具中更新“常规电话”字段。
    
## <a name="network"></a>网络

- 确保您具有有线的网络连接的 Skype 的空间系统。
    
- 阅读规划业务指南 Skype 的网络。
    
- 请求对商业伙伴 Skype 业务网络评估 Skype。
    
- 读取性能数据捕获在 Skype 业务运行状况分析工具 (Excel)。
    
- 运行网络分析工具。
    
- 运行预呼叫诊断工具。
    
## <a name="skype-room-system-security"></a>Skype 的空间系统的安全性

Skype 的空间系统是嵌入式的系统可以完全集成在 Windows 部署中，使用 Skype 业务安全模型、 权限管理和管理工具，例如 SCOM。 功能包括：
  
- 写入筛选器，可防止磁盘在用户模式下写入 
    
- 应用锁定器，可防止未经授权的应用运行。在用户模式下，所有 USB 端口都被禁用。
    
  - 没有标准的应用程序或查看器驻留在 Skype 的空间系统硬件上。 所有内容都是通过 HTTP 或 RDP 协议呈现的。
    
  - 家用电脑运行 Windows Embedded Standard 7 操作系统。所有硬件（包括设备）都由 OEM 合作伙伴提供。
    
  - 选择性地将域加入到 Active Directory 域服务 (AD DS)，实现本地安全帐户管理和控制。
    
- 您还可以管理业务管理中心使用 Skype 的本地管理员帐户。
    
- Skype 的空间系统将更新通过标准的 Microsoft 更新过程。
    
- Skype 的空间系统用 Skype 业务连接。
    
  - Skype 业务为用于所有通信模式的端到端加密和授权
    
  - Skype 的空间系统支持 Skype 业务安全和法规遵从性标准。 有关详细信息，请参阅“规划 Lync Server 2013 的安全性”。
    
## <a name="license"></a>许可证

验证你是否可以使用 KMS 激活软件。 如果是这样，您可能需要检查或向其中添加业务客户端 KMS 密钥为 Skype。 如果您不使用 KMS，然后请求批量业务客户端 MAK 的 Skype 的许可密钥。
  
## <a name="license-keys"></a>许可证密钥

Skype 的空间系统运行在后台业务桌面客户端的 Skype。 如果 Skype 的空间系统是域成员，它将会发现您的 KMS。 （并且，如果具有批量许可 KMS Lync 密钥，则将自动激活。 ）批量许可也提供 MAK，当你输入时，它将显示 xxxxx-xxxxx-xxxxx-xxxxx。 （你需要 Internet 访问才能使用 MAK 而不是 KMS 激活。 ）有关详细信息，请参阅“Office 2013 的批量激活”。
  
- 要输入 MAK 密钥，请转到 OEM 设置\>SRS 授权工具。 单击“检查状态”。 当该状态显示"产品未激活"时，请输入密钥。
    
- 如果在激活过程中收到错误，指出:"' 软件授权服务报告的产品密钥无效，"然后确认：
    
  - 正确输入密钥。
    
  - Skype 输入业务 MAK 密钥并不是另一个密钥。
    
  - 系统具有 Internet 访问。
    
- 你可以通过电话激活，但是必须首先已尝试使用 SRS 许可工具激活。 要通过电话激活，请启动测试会议（而不是测试呼叫，因为测试呼叫时间太短）。 在 Office 激活向导中，选择电话激活致电 Microsoft、 键入的长号，输入的响应。
    
## <a name="certificate-authority"></a>证书颁发机构

确认用于颁发 Office Web Apps Server 2013 证书的证书颁发机构在证书吊销列表中包括 HTTP 路径。
  
如果使用 Skype 业务服务器到 Skype 的空间系统导入证书文件 (.crt)。 可轻松地从 CA 服务器的 CertEnroll 共享中或者在任何加入域的电脑的“受信任的根”文件夹中获得。
  
## <a name="certificates"></a>证书

验证你的证书颁发机构是否具有证书吊销列表的 http 路径。如果没有，请更新你的 CA 以包括该路径。
  
在系统设置中的 Skype 的空间系统管理设置安装证书\>证书管理器。 你需要你的内部证书的企业根 CA。
  
获取所需证书的一种方法是发现颁发你的证书的 CA。 单击设置为企业服务器，Skype 的业务，在电脑上的 Skype\>工具\>会议设置拨入。 此时将打开一个受颁发内部 Lync 证书的 CA 保护的网页。 单击浏览器地址栏上的锁图标以显示安全报告。 单击“查看证书”并检查“CRL 分布点”属性。 第二个 CN 参数应为 CA 的服务器名称。 现在，Windows 资源管理器打开该地址\\\<的 CA 服务器名称\>\CertEnroll。 请将两个 .crl 文件和 .crt 文件复制到 U 盘，并将其放在智能白板的左侧。
  
将.crt 文件导入到受信任房间证书颁发机构文件夹下 Skype 室系统。
  
在中间证书颁发机构文件夹下，Skype 的空间系统为.crl 文件导入。 （您需要将证书管理器中的文件扩展名筛选器更改为.crl 查看这些文件）。
  
注意：Office Web Apps 2013 服务器可能与 Lync 共用同一个 CA。如果不是，那么你将无法在会议中共享 PowerPoint 演示文稿。请与 IT 核实，并按上面所述从 CA 网络共享 CertEnroll 获取 CRT 和 CRL 文件。 
  
因为作为 Windows 系统，可以将 Skype 的空间系统，它可以依赖 Active Directory 证书方面的某些域成员身份可以简化一些。 但是，最好是手动管理它。
  

