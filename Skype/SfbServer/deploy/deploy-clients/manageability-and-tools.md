---
title: Skype会议室系统可管理性和工具
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 阅读本主题，了解会议室Skype管理工具。
ms.openlocfilehash: 92fe780565728c457d6853e0210ec7981386ca0b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592876"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype会议室系统可管理性和工具
 
阅读本主题，了解会议室Skype管理工具。
  
## <a name="administrative-portal"></a>管理门户

对于Skype for Business Server部署，可以使用 Skype Room System 管理门户主动管理和监视Skype会议室系统部署。
  
有关详细信息，请参阅以下文章：
  
- [在部署 SRS v1 管理 Web 门户Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange清单

- 确认已设置自动发现，并且内部 DNS A/CNAME 记录可用于 autodiscover.domain.com。
    
- Ping 自动发现 (例如 Ping Autodiscover.contoso.com) 。
    
- 使用 Microsoft Connectivity Analyzer 工具测试自动发现服务。 选择第一个测试"我无法通过 Office Outlook 登录"。
    
- 如果会议室已有资源邮箱，请为会议室系统Skype扩展此帐户 (页面底部的示例脚本) 。
    
## <a name="skype-for-business-checklist"></a>Skype for Business清单

- 运行以下工具：
    
  - Skype for Business最佳做法分析器     
  - Skype for Business运行状况分析工具 (Excel)     
  - Skype for Business连接分析器 32 位或 64 位
    
- Review [Useful new troubleshooting and analysis tools for Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365). 确认您具有 Skype for Business 池和 Office Web Apps 服务器，并可以使用 PowerPoint 客户端共享Skype for Business平台。
    
- 如果会议室已有资源邮箱，请为会议室启用Skype for Business。
    
- 如果需要，请求为 (系统) DID 会议室电话号码，并更新 Active Directory 工具中的"常规电话"字段。
    
## <a name="network"></a>网络

- 确保你具有用于会议室系统的有线Skype网络连接。
    
- 请参阅网络规划指南Skype for Business。
    
- 从Skype for Business合作伙伴请求Skype for Business网络评估。
    
- 读取在 Skype for Business Health Analysis Tool 工具中捕获 (Excel) 。
    
- 运行网络分析工具。
    
- 运行预调用诊断工具。
    
## <a name="skype-room-system-security"></a>Skype会议室系统安全性

Skype会议室系统是一个嵌入系统，可以使用 Windows 安全模型、权限管理和 SCOM 等管理工具Skype for Business部署中完全集成。 这些功能包括： 
  
- 防止在用户模式下写入磁盘的写入筛选器 
    
- 应用保险箱，可防止未经授权的应用运行。 在用户模式下禁用所有 USB 端口。
    
  - 没有标准应用或查看器驻留在Skype系统硬件上。 所有内容都通过 HTTP 或 RDP 协议呈现。
    
  - 该设备电脑运行 Windows Embedded Standard 7 操作系统。 所有硬件（包括设备）都由 OEM 合作伙伴提供。
    
  - AD DS (Active Directory 域服务的可选域) ，从而实现本地安全帐户管理和控制。
    
- 您还可以使用管理中心管理本地Skype for Business帐户。
    
- Skype会议室系统通过标准 Microsoft 更新过程进行更新。
    
- Skype会议室系统与Skype for Business。
    
  - Skype for Business所有通信模式使用端到端加密和授权
    
  - Skype会议室系统Skype for Business安全性和合规性标准。 有关详细信息[，请参阅在 Skype For Business Server](../../plan-your-deployment/security/security.md)中规划安全性。
    
## <a name="license"></a>许可证

验证是否使用KMS激活软件。 如果是这样，你可能需要检查或添加Skype for Business客户端KMS密钥。 如果不使用客户端KMS，请为客户端 MAK 请求Skype for Business密钥。
  
## <a name="license-keys"></a>许可证密钥

Skype会议室系统在后台Skype for Business桌面客户端。 如果Skype系统是域成员，它将发现你的KMS。  (并且如果具有批量许可密钥KMS它将自动激活) 。 批量许可还提供 MAK，在显示 xxxxx-xxxxx-xxxxx-xxxxx 时输入此 MAK。  (需要 Internet 访问权限才能使用 MAK 激活，但不能KMS) 。 有关详细信息，请参阅 Volume activation of Office 2013。
  
- 若要输入 MAK 密钥，请转到 OEM 设置 \> SRS 许可工具。 单击“检查状态”。 当状态显示"产品未激活"时，输入密钥。
    
- 如果在激活期间收到一个错误，指出"软件许可服务报告产品密钥无效"，请验证：
    
  - 键输入正确。
    
  - 您输入了Skype for Business MAK 密钥，而不是另一个密钥。
    
  - 系统可以访问 Internet。
    
- 可以通过电话激活，但必须先尝试使用 SRS 许可工具激活。 若要通过电话激活，请启动测试 (而不是测试呼叫，因为测试) 。 在"Office激活向导"中，选择"电话激活"，致电 Microsoft，键入长号，然后输入响应。
    
## <a name="certificate-authority"></a>证书颁发机构

确认用于颁发 Web Apps Server 2013 Office证书的证书颁发机构在证书吊销列表属性中包含 HTTP 路径。
  
如果使用 (.crt) ，Skype证书文件导入Skype for Business Server。 它很容易从 CA 服务器的 CertEnroll 共享，或在任何加入域的电脑的受信任的根文件夹中获取。
  
## <a name="certificates"></a>证书

验证证书颁发机构是否具有证书吊销列表的 http 路径。 如果没有，请更新 CA 以包含一个 CA。
  
在 System Skype Certificate Manager 下的 设置 会议室系统的管理员设置中安装 \> 证书。 内部证书Enterprise根 CA。
  
获取所需的证书的一种方式是发现颁发证书的 CA。 For Skype for Business Server， on a PC in Skype for Business， click 设置 \> Tools \> Dial-in Conference 设置. 这将打开由颁发内部证书的 CA 保护的网页。 单击浏览器地址栏上的"锁定"图标以显示安全报告。 单击"查看证书"并检查 CRL 分发点属性。 第二个 CN 参数应为 CA 的服务器名称。 现在打开Windows \\ \< CA Server Name \> \CertEnroll 的浏览器。 将两个 .crl 文件和 .crt 文件复制到闪存驱动器，并放在 SMART 板的左侧。
  
将 .crt 文件导入到Skype"会议室证书颁发机构"文件夹下的会议室系统。
  
在"中间证书颁发机构"Skype下导入会议室系统上的 .crl 文件。  (你需要将证书管理器中的文件扩展名筛选器更改为 .crl 以查看) 。
  
注意：Office Web Apps 2013 服务器可能与 Skype for Business 共享同一 CA。 如果没有，你将无法在PowerPoint共享会议。 与 IT 核实，从 CA 网络共享 CertEnroll 获取 CRT 和 CRL 文件，如上所述。 
  
域成员身份可以简化一些操作，因为您可以将 Skype Room System 视为一个 Windows 系统，并且它可以依赖 Active Directory 获得某些证书方面。 但是，最好手动管理它。
