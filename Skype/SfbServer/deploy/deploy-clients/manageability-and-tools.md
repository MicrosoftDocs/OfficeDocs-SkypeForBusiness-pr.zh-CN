---
title: Skype 会议室系统可管理性和工具
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 阅读本主题，了解适用于 Skype 会议室系统的管理工具。
ms.openlocfilehash: c9289d3fffa78dd7ffd94fa17784c1b06c2278b1
ms.sourcegitcommit: fa55f9e3690fcca36b530bd13a9eeaa44120b87c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "37547255"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype 会议室系统可管理性和工具
 
阅读本主题，了解适用于 Skype 会议室系统的管理工具。
  
## <a name="administrative-portal"></a>管理门户

对于 Skype for business 服务器内部部署，你可以使用 Skype 会议室系统管理门户主动管理和监控你的组织内的 Skype 会议室系统部署。
  
有关详细信息，请参阅以下文章：
  
- [在 Skype for Business 服务器中部署 SRS v1 管理 Web 门户](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange 清单

- 确认已设置自动发现并且内部 DNS A/CNAME 记录可用于 autodiscover.domain.com。
    
- Ping 自动发现（例如，Ping Autodiscover.contoso.com）。
    
- 使用 Microsoft Connectivity Analyzer 工具测试你的自动发现服务。 选择第一个测试 "我无法用 Office Outlook 登录"。
    
- 如果会议室已有资源邮箱，请为 Skype 会议室系统扩展此帐户（页面底部的示例脚本）。
    
## <a name="skype-for-business-checklist"></a>Skype for Business 清单

- 运行以下工具：
    
  - Skype for Business 最佳做法分析器     
  - Skype for Business 运行状况分析工具（Excel）    
  - Skype for Business 连接分析器 32-位或64位
    
- 查看[适用于 Office 365 的有用的新疑难解答和分析工具](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)。 确认你有 Skype for business 池和 Office Web Apps 服务器，并且可以使用 Skype for Business 客户端共享 PowerPoint 幻灯片。
    
- 如果会议室已有资源邮箱，请为 Skype for business 启用它。
    
- 如果需要，请为会议室系统请求 DID（电话号码）并在 Active Directory 工具中更新“常规电话”字段。
    
## <a name="network"></a>网络

- 确保您有 Skype 会议室系统的有线网络连接。
    
- 阅读 Skype for business 的网络规划指南。
    
- 从 Skype for business 合作伙伴请求 Skype for Business 网络评估。
    
- 阅读查看 Skype for Business 运行状况分析工具（Excel）中捕获的性能数据。
    
- 运行网络分析工具。
    
- 运行预呼叫诊断工具。
    
## <a name="skype-room-system-security"></a>Skype 会议室系统安全

Skype 会议室系统是一种嵌入式系统，可在 Windows 部署中使用 Skype for Business 安全模型、权限管理和管理工具（如 SCOM）完全集成。 功能包括：
  
- 写入筛选器，可防止磁盘在用户模式下写入 
    
- 应用锁定器，可防止未经授权的应用运行。在用户模式下，所有 USB 端口都被禁用。
    
  - 没有标准应用或查看器驻留在 Skype 会议室系统硬件上。 所有内容都是通过 HTTP 或 RDP 协议呈现的。
    
  - 家用电脑运行 Windows Embedded Standard 7 操作系统。所有硬件（包括设备）都由 OEM 合作伙伴提供。
    
  - 选择性地将域加入到 Active Directory 域服务 (AD DS)，实现本地安全帐户管理和控制。
    
- 您也可以使用 Skype for Business 管理中心管理本地管理员帐户。
    
- Skype 会议室系统通过标准的 Microsoft 更新流程进行更新。
    
- Skype 会议室系统通过 Skype for Business 进行连接。
    
  - Skype for business 对所有通信模式使用端到端加密和授权
    
  - Skype 会议室系统支持 Skype for business 安全和合规性标准。 有关详细信息，请参阅[Skype For Business 服务器中的安全规划](../../plan-your-deployment/security/security.md)。
    
## <a name="license"></a>许可证

验证你是否可以使用 KMS 激活软件。 如果是这样，你可能需要检查或向其添加 Skype for Business 客户端 KMS 密钥。 如果你没有使用 KMS，请请求 Skype for business 客户端 MAK 的批量许可密钥。
  
## <a name="license-keys"></a>许可证密钥

Skype 会议室系统在后台运行 Skype for Business 桌面客户端。 如果 Skype 会议室系统是域成员，它将发现你的 KMS。 （如果它具有批量许可 KMS 密钥，它将自动激活）。 ）批量许可也提供 MAK，当你输入时，它将显示 xxxxx-xxxxx-xxxxx-xxxxx。 （你需要 Internet 访问才能使用 MAK 而不是 KMS 激活。 ）有关详细信息，请参阅“Office 2013 的批量激活”。
  
- 若要输入 MAK 密钥，请转到 OEM \>设置 SRS 授权工具。 单击“检查状态”。 当状态显示 "产品未激活" 时，请输入密钥。
    
- 如果在激活期间收到错误，表明 "软件授权服务报告产品密钥无效"，请验证：
    
  - 正确输入密钥。
    
  - 您输入的是 Skype for business MAK 密钥，而不是另一个密钥。
    
  - 系统具有 Internet 访问。
    
- 你可以通过电话激活，但是必须首先已尝试使用 SRS 许可工具激活。 要通过电话激活，请启动测试会议（而不是测试呼叫，因为测试呼叫时间太短）。 在 Office 激活向导中，选择 "电话激活"、"呼叫 Microsoft"、"键入长号码" 和 "输入响应"。
    
## <a name="certificate-authority"></a>证书颁发机构

确认用于颁发 Office Web Apps Server 2013 证书的证书颁发机构在证书吊销列表中包括 HTTP 路径。
  
如果使用 Skype for business 服务器，请将证书文件（.crt）导入 Skype 会议室系统。 可轻松地从 CA 服务器的 CertEnroll 共享中或者在任何加入域的电脑的“受信任的根”文件夹中获得。
  
## <a name="certificates"></a>证书

验证你的证书颁发机构是否具有证书吊销列表的 http 路径。如果没有，请更新你的 CA 以包括该路径。
  
在 "系统设置\> " 证书管理器中的 Skype 会议室系统的管理员设置中安装证书。 你需要你的内部证书的企业根 CA。
  
获取所需证书的一种方法是发现颁发你的证书的 CA。 对于 Skype for business 服务器，在 Skype for business 上的 PC 上，单击\> " \>设置工具拨入会议设置"。 这将打开由颁发内部证书的 CA 保护的网页。 单击浏览器地址栏上的锁图标以显示安全报告。 单击“查看证书”并检查“CRL 分布点”属性。 第二个 CN 参数应为 CA 的服务器名称。 现在打开该地址\\ \< CA 服务器名称\>的 Windows 资源管理器 \CertEnroll。 请将两个 .crl 文件和 .crt 文件复制到 U 盘，并将其放在智能白板的左侧。
  
将 .crt 文件导入 "受信任的聊天室证书颁发机构" 文件夹中的 Skype 房间系统。
  
将 .crl 文件导入到 "中级证书颁发机构" 文件夹下的 Skype 会议室系统中。 （您需要将 "证书管理器" 中的文件扩展名筛选器更改为 "crl" 才能看到这些文件）。
  
注意： Office Web Apps 2013 服务器可能与 Skype for Business 共享相同的 CA。 如果不是，那么你将无法在会议中共享 PowerPoint 演示文稿。 请与 IT 核实，并按上面所述从 CA 网络共享 CertEnroll 获取 CRT 和 CRL 文件。 
  
域成员身份可以简化一些内容，因为你可以将 Skype 会议室系统视为 Windows 系统，并且它可以针对某些证书方面依赖 Active Directory。 但是，最好是手动管理它。
  

