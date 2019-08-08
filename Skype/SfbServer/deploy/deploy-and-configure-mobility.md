---
title: 为 Skype for Business 服务器部署和配置移动
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文将指导你完成配置现有 Skype for Business 服务器安装以使用移动服务的步骤, 使你的移动设备能够利用 Skype for Business Server 移动功能。
ms.openlocfilehash: 910e23e8aec18d36c3a7e4bda9e97828fb498802
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234571"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>为 Skype for Business 服务器部署和配置移动  
 
本文将指导你完成配置现有 Skype for Business 服务器安装以使用移动服务的步骤, 使你的移动设备能够利用 Skype for Business Server 移动功能。
  
如果已查看[skype for Business server 文章的移动性计划](../plan-your-deployment/mobility.md), 您应该准备好继续执行以下步骤, 以将移动性部署到 Skype For business 服务器环境中。 步骤如下所示（并且此表中包含权限列表）：
  
|**阶段**|**权限**|
|:-----|:-----|
|[创建 DNS 记录](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[修改证书](deploy-and-configure-mobility.md#ModCerts) <br/> |本地管理员  <br/> |
|[配置反向代理](deploy-and-configure-mobility.md#ConfigRP) <br/> |本地管理员  <br/> |
|[使用混合部署配置移动性的自动发现](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[测试移动功能部署](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[配置推送通知](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[配置移动策略](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
以下所有部分都包含假定你已阅读规划主题的步骤。如果有任何让你感到困惑的地方，请随时查阅此处的信息。

> [!NOTE]
> 在 Skype for Business Server 2019 中, MCX (移动服务) 对旧式移动客户端的支持不再可用。 所有当前 Skype for business 移动客户端都已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、状态和联系人。 具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
## <a name="create-dns-records"></a>创建 DNS 记录
<a name="CreateDNSRec"> </a>

您可能已将这些内容作为 Skype for Business 服务器环境的一部分, 但您需要创建以下记录才能使自动发现正常工作:
  
- 支持从组织网络内部进行连接的移动用户的内部 DNS 记录。
    
- 支持从组织网络外部进行连接的移动用户的外部（或公共）DNS 记录。
    
这些记录可以是 A（主机）名称或 CNAME 记录（你不必同时创建两者，我们这里只是将步骤都介绍一遍）。
  
### <a name="create-an-internal-dns-cname-record"></a>创建内部 DNS CNAME 记录

1. 以 **Domain Admins** 组成员或 **DnsAdmins** 组成员的身份登录网络中的 DNS 服务器。
    
2. 单击**开始**，选择**管理工具**（如果它不是“开始”菜单的选项，你可能需要对其进行**搜索**），然后单击 **DNS** 以打开 DNS 管理单元。
    
3. 在控制台窗口的左侧窗格中, 你需要转到 Skype for business 服务器前端服务器所在的域, 然后展开此处的**正向查找区域**。
    
4. 检查一下你是否具有以下记录：
    
   - 前端服务器 (标准或企业) 或前端池的任何主机 A 或 AAAA 记录。
    
   - 控制器或控制器池的任何主机 A 或 AAAA 记录 (您在部署中可能具有的可选配置)。
    
5. 记下此信息后，右键单击你的 SIP 域名，然后从菜单中选择**新建别名 (CNAME)**。
    
6. 在**别名**文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。
    
7. 在**完全限定的域名 (目标主机的 FQDN**中, 你需要键入或浏览到位于上述步骤4中标识的前端池 (或单个前端服务器, 或控制器池) 的内部 WEB 服务 FQDN。 输入后，单击“确定”。
    
8. 你将需要在 Skype for Business Server 环境支持的每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。
    
### <a name="create-an-external-dns-cname-record"></a>创建外部 DNS CNAME 记录

1. 这些步骤是常规步骤，因为我们无法知道你正在使用的是哪个公共 DNS 提供程序，但我们仍希望帮助你排忧解难。请使用能够创建新的 DNS 记录的帐户登录到你的公共 DNS 提供程序。
    
2. 在此时间点, Skype for business 服务器应该已存在一个 SIP 域。 请展开此 SIP 域的**正向查找区域**，否则请打开它。
    
3. 检查一下你是否具有以下记录：
    
   - 前端服务器 (标准或企业) 或前端池的任何主机 A 或 AAAA 记录。
    
   - 控制器或控制器池的任何主机 A 或 AAAA 记录 (您在部署中可能具有的可选配置)。
    
4. 拥有该信息后，应该能够选择用于**新建别名 (CNAME)** 的选项。
    
5. 现在，你应该能够输入**别名**，你需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。
    
6. 接下来, 应该有一个要在**目标主机的 FQDN**中输入的区域, 这将需要是你的前端池 (或单个前端服务器或控制器池) 的 fqdn, 在上述步骤3中标识。
    
7. 你可能需要保存在此处, 或者如果你需要在 Skype for Business Server 环境中的每个 SIP 域的正向查找区域中创建其他 CNAME 记录, 你应该执行此操作, 但在准备好后, 请保存你的工作。
    
### <a name="create-an-internal-dns-a-record"></a>创建内部 DNS A 记录

1. 以 **Domain Admins** 组成员或 **DnsAdmins** 组成员的身份登录网络中的 DNS 服务器。
    
2. 单击**开始**，选择**管理工具**（如果它不是“开始”菜单的选项，你可能需要对其进行**搜索**），然后单击 **DNS** 以打开 DNS 管理单元。
    
3. 在控制台窗口的左侧窗格中, 你需要转到 Skype for business 服务器前端服务器所在的域, 然后展开此处的**正向查找区域**。
    
4. 检查一下你是否具有以下记录：
    
   - 前端服务器 (标准或企业) 或前端池的任何主机 A 或 AAAA 记录。
    
   - 控制器或控制器池的任何主机 A 或 AAAA 记录 (您在部署中可能具有的可选配置)。
    
5. 记下此信息后，右键单击你的 SIP 域名，然后从菜单中选择**新建主机 (A 或 AAAA)**。
    
6. 在**名称**文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。
    
7. 在 " **IP 地址**" 文本框中, 键入您的前端池 (或单个前端服务器, 或控制器池或 director) 的内部 WEB 服务 IP 地址, 在上述步骤4中标识。
    
8. 完成此操作后，单击**添加主机**，然后单击**确定**。
    
9. 你需要在 Skype for Business Server 环境支持的每个 SIP 域的正向查找区域中创建新的自动发现或 AAAA 记录。 为此，请根据需要多次重复步骤 6-8。
    
10. 完成后，单击**完成**。
    
### <a name="create-an-external-dns-a-record"></a>创建外部 DNS A 记录

1. 这些步骤是常规步骤，因为我们无法知道你正在使用的是哪个公共 DNS 提供程序，但我们仍希望帮助你排忧解难。请使用能够创建新的 DNS 记录的帐户登录到你的公共 DNS 提供程序。
    
2. 在此时间点, Skype for business 服务器应该已存在一个 SIP 域。 请展开此 SIP 域的**正向查找区域**，否则请打开它。
    
3. 检查一下你是否具有以下记录：
    
   - 前端服务器 (标准或企业) 或前端池的任何主机 A 或 AAAA 记录。
    
   - 控制器或控制器池的任何主机 A 或 AAAA 记录 (您在部署中可能具有的可选配置)。
    
4. 拥有该信息后，应该能够选择用于创建**新主机 A 或 AAAA** 的选项。
    
5. 现在，你应该能够输入**名称**，你需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。
    
6. 接下来, 应在**Ip Addresss**中输入要输入的区域, 这将需要是你的前端池 (或单个前端服务器, 或控制器池或 director) 的 IP, 在上述步骤3中标识。
    
7. 你可能需要保存在此处, 或者如果你需要在每个 SIP 域的正向查找区域中为 Skype for business Server 环境创建额外的 A 或 AAAA 记录, 你应该执行此操作, 但一旦准备就绪, 请保存你的工作。
    
## <a name="modify-certificates"></a>修改证书
<a name="ModCerts"> </a>

如果您对证书的规划有疑问, 我们已经记录了我们[针对 Skype for Business 服务器的移动性计划](../plan-your-deployment/mobility.md)。 阅读该文章后，我们将引导你完成以下步骤：
  
- 是否需要新证书？
    
- 从你的证书颁发机构 (CA) 请求新证书。
    
- 使用 PowerShell 通过替换内容更新你的就地证书。
    
- 使用 Microsoft 管理控制台 (MMC) 中的 "证书" 管理单元检查证书。
    
### <a name="do-i-need-new-certificates"></a>是否需要新证书？

1. 首先，你可能需要检查哪些证书是就地证书，以及它们是否具有所需的条目。 若要执行此操作, 您需要使用本地管理员帐户登录 Skype for Business 服务器。 此帐户可能还需要对证书颁发机构 (CA) 具有权限才能执行下面的某些步骤。
    
2. 打开 Skype for Business 服务器管理外壳程序 (如果未将其固定到 "开始" 菜单或任务栏, 则可以使用 "搜索" 来查找它)。
    
3. 你必须了解在尝试添加更新证书之前已分配哪些证书。因此，在命令行中键入：
    
   ```
   Get-CsCertificate
   ```

4. 步骤 3 中的信息对你具有唯一性。你需要仔细检查，以确定你是否具有为所有内容分配的单个证书，或者是否具有为所需的不同组件分配的不同证书。**Use** 参数将告知你证书的使用方式，**Thumbprint** 参数将告知你所有证书都相同还是具有多个证书。
    
5. 如果你已在规划部分中建议 SAN 条目，则可方便使用。如果没有，你需要从你的证书颁发机构请求一个新证书或多个证书（具体取决于你的配置）。
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>从你的证书颁发机构 (CA) 请求一个新证书或多个证书。

1. 检查你具有哪些 SAN 条目后，你就知道你具有**单个证书**（通过上述步骤检查后），并且你知道自己没有所需的所有条目。 需要向你的 CA 发出新证书请求。 打开 Skype for Business 服务器 PowerShell:
    
   - 对于缺少的自动发现服务 SAN（将 -Ca 参数替换为你自己的证书颁发机构路径）：
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 现在, 如果您有多个 SIP 域, 则不能使用 AllSipDomain 参数, 如上例中所示。 你需要改为使用 DomainName 参数。 当你使用 DomainName 参数时，你必须为 lyncdiscoverinternal 和 lyncdiscover 记录定义 FQDN。 例如（将 -Ca 参数替换为你自己的证书颁发机构路径）：
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. 或者，检查你具有哪些 SAN 条目后，你发现你具有**多个证书**，其中并不包含你所需的所有条目。 需要向你的 CA 发出新证书请求。 打开 Skype for Business 服务器 PowerShell:
    
   - 对于缺少的自动发现服务 SAN（将 -Ca 参数替换为你自己的证书颁发机构路径）：
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 现在, 如果您有多个 SIP 域, 则不能使用 AllSipDomain 参数, 如上例中所示。 你需要改为使用 DomainName 参数。 当你使用 DomainName 参数时，你必须为 lyncdiscoverinternal 和 lyncdiscover 记录定义 FQDN。 例如（将 -Ca 参数替换为你自己的证书颁发机构路径）：
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - 由 CA 生成新证书后，你需要对其进行分配。
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序分配证书

- 根据你在上面的“是否需要新证书”部分中发现的内容，你需要运行以下命令**之一**。
    
  - 如果所有内容具有单个证书（指纹相同），则需要运行以下命令：
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 如果某些内容具有不同证书（指纹都不同），请改为运行以下命令：
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>在 Microsoft 管理控制台 (MMC) 中查看证书

1. 你可以选择使用 MMC 的证书管理单元查看你的证书。只需在搜索中键入 MMC，它应作为应用程序选项弹出。
    
2. 要添加证书管理单元，你需要单击**文件**，然后单击**添加/删除管理单元...**（或者键盘快捷方式 **Ctrl+M** 也会奏效）。**证书**将成为左侧窗格中的一个选项，选中它并在弹出窗口中单击**计算机帐户**，然后单击**下一步**。
    
3. 仍在弹出窗口中，你极有可能在承载需要查看的证书的计算机上执行此操作，因此如果是那样，请选择**本地计算机**。 如果你正在远程计算机上工作，请将单选按钮更改为**其他计算机**，然后输入该计算机的 FQDN 或使用**浏览**按钮通过 AD 搜索该计算机。 选择计算机后, 需要在 "准备就绪" 后单击 "**完成**", 然后单击 **"确定"** 以将该管理单元添加到 MMC。
    
4. 展开 MMC 左侧窗格中的 "**证书**" 部分。 还需展开**个人**文件夹，然后选择**证书**。 这样，你可以在此存储中查看证书。
    
5. 你需要查找要查看的证书，右键单击它，然后选择**打开**。
    
    > [!NOTE]
    > 你如何知道这是什么证书？ 它应该是分配给你的场的所有内容的单个证书, 或者你可以为不同的内容 (如默认、内部 Web 服务等) 使用多个证书, 在这种情况下, 你可能需要查看多个证书。 多个证书将具有相同的指纹。 
  
6. 进入**证书**视图后，选择**详细信息**。这样，你可以在选择**主题**时看到证书主题名称，并且会显示分配的主题名称和关联的属性。
    
7. 你还需要检查**使用者替代名称**条目。你将发现以下一个或多个条目：
    
   - 此池的池名称, 如果不是池, 则为单个服务器名称。
    
   - 向其分配证书的服务器名称。
    
   - 简单 URL 记录，一般为 meet 和 dialin。
    
   - Web 服务内部和 Web 服务外部名称 (例如, webpool01.contoso.net、webpool01.contoso.com), 基于在拓扑生成器和 ridden 的 Web 服务选择中所做的选择。
    
   - 如果已分配, 则 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>记录。
    
     如果分配有多个证书，你需要对其进行检查（查看上述备注）。
    
8. 因此, 如果你发现 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>记录已配置。 你可以关闭 MMC。
    
9. 如果未分配这些证书，你需要发出新证书请求（上面概述）或需要在请求后进行安装（我们建议使用上述 PowerShell 实现该目的）。
    
## <a name="configure-the-reverse-proxy"></a>配置反向代理
<a name="ConfigRP"> </a>

不应严格遵循以下步骤。因为在该产品的早期版本中，我们已引导你配置 Threat Management Gateway (TMG)，如果你未使用该产品，你需要从其创建自己的版本。
  
TMG 不再由 Microsoft 作为产品提供, 如果仍需要配置它, 你可以查看[Lync Server 2013 步骤](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)。 但是, 以下信息的预期更普遍有用, 即使没有办法可以为每个反向代理提供特定的演练步骤。
  
需要考虑以下两个主要事项：
  
- 是否要通过 HTTPS（推荐）执行你的初始自动发现请求？
    
  - 如果你具有 Web 发布规则，则需要对其进行修改。
    
  - 如果你还没有 Web 发布规则，则需要进行创建。
    
- 如果你正在通过 HTTP 执行你的初始自动发现请求，则还需要创建或修改该规则。
    
> [!NOTE]
> **重要提示**代理超时值是一个数字, 该数字将因部署而异。 应监视你的部署并修改客户端最佳体验的值。 你可以将值设置为低至200。 如果你在你的环境中支持 Lync 移动客户端, 则应将该值设置为960以允许来自 Office 365 的推送通知超时, 该超时值为900。 很有可能必须增加超时值以避免客户端在值太低时断开连接, 或者, 如果通过代理的连接不能断开连接, 但在客户端断开连接后很长时间, 则会减少数字。 监视和设置环境的常规功能是确定此值的适当设置的唯一准确方式。
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>为你的外部自动发现 SAN 和 URL 修改现有 Web 发布规则

1. 打开反向代理接口。
    
2. 您需要找到 web 发布规则, 然后选择 "编辑" 选项 (它可能位于菜单或选项卡上, 具体取决于您的反向代理配置)。
    
3. 应存在一个区域, 指明应用此 web 发布规则的内容。 你需要为传入站点或站点请求修改此规则。 你要**添加**新条目。
    
4. 键入自动发现网站的名称 (我们将使用的示例为 lyncdiscover.contoso.com), 然后单击 **"确定" 或 "** **保存**", 具体取决于你的反向代理的格式。
    
5. 你可能会有一个其中具有自动发现 SAN 条目的新证书。 这还需要安装, 并根据您的反向代理设置进行配置以供使用。 配置完成后，请务必保存所有内容。
    
6. 如果反向代理具有**测试**功能, 请使用它来确保一切正常工作。
    
7. 现在, 如果你的环境中有 Director 或控制器池, 你可能需要重复这些步骤 (这意味着你有第二条规则)。
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>为外部自动发现 URL 创建 web 发布规则

1. 打开反向代理接口。
    
2. 您需要找到在界面上创建 web 发布规则的位置, 然后选择 "**新建**" 或 "**创建**" 选项 (它可能位于菜单或选项卡上, 具体取决于您的反向代理配置)。 你要查找用于创建新的 Web 发布规则的选项。
    
3. 通常，你需要输入以下信息：
    
   - **名称**：规则的名称
    
   - **规则操作**: 在这种情况下, 这是一个**允许**规则, 你可以通过反向代理来传递内容。
    
   - 你选择的**发布**规则或选项将为**单个网站或负载平衡器**。
    
   - 这需要为 **SSL** 以供外部访问，请选择该选项。
    
   - 你将需要发布**内部发布**的路径, 并在你的前端池的负载平衡器 (或控制器池的负载平衡器的 fqdn (如果有)) 上输入外部 Web 服务的 fqdn, 例如, sfb_pool01。
    
   - 应键入** / *** 作为要发布的路径, 但也需要**转发原始主机头**。
    
   - 有一个**公共或外部名称**详细信息或信息的选项。你可在其中输入以下内容：
    
   - **接受请求**，但应为域名。
    
   - 对于**名称**，你应输入 **lyncdiscover.** <sipdomain>(这是外部自动发现服务 URL)。 现在, 如果你要为前端池上的外部 Web 服务 URL 创建规则, 你需要在你的前端池 (如 lyncwebextpool01.contoso.com) 上键入外部 Web 服务的 FQDN (例如,)。
    
   - 将出现 "**路径**" 选项, 您需要在此处输入** / **"*"。
    
   - 你需要选择具有最新公共证书的 **SSL 侦听器**。
    
   - **身份验证委派**应设置为**无委派**，但直接客户端身份验证**应**被允许。
    
   - 规则应设置为**所有用户**。
    
   - 这应是创建此规则所需的所有信息，并且允许你继续操作。
    
4. 你需要确保已转发**原始主机头**。
    
5. 还需要设置 **Web 服务器**端口，为此，你需要执行以下操作：
    
   - **将请求重定向到 HTTP 端口**，端口号应为 **8080**。
    
   - **将请求重定向到 SSL 端口**，端口号应为 **4443**。
    
6. 一切均配置好后，你需要对其进行保存或应用，然后你将需要测试该规则。
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>为端口 80 创建 Web 发布规则（可选）

1. 打开反向代理接口。
    
2. 您需要找到在界面上创建 web 发布规则的位置, 然后选择 "**新建**" 或 "**创建**" 选项 (它可能位于菜单或选项卡上, 具体取决于您的反向代理配置)。 你要查找用于创建新的 Web 发布规则的选项。
    
3. 通常，你需要输入以下信息：
    
   - **名称**：规则的名称
    
   - **规则操作**: 在这种情况下, 这是一个**允许**规则, 你可以通过反向代理来传递内容。
    
   - 你选择的**发布**规则或选项将为**单个网站或负载平衡器**。
    
   - 这必须为**用于连接发布的 Web 服务器或场的不安全连接**。
    
   - 你将需要发布**内部发布**的路径, 并输入你的前端池的负载平衡器的**VIP 地址**的 FQDN, 例如, sfb_pool01。
    
   - 应键入** / *** 作为要发布的路径, 但也需要**转发原始主机头**。
    
   - 有一个**公共或外部名称**详细信息或信息的选项。你可在其中输入以下内容：
    
   - **接受请求**，但应为域名。
    
   - 对于**名称**，你应输入 **lyncdiscover.** <sipdomain>(这是外部自动发现服务 URL)。
    
   - 将出现 "**路径**" 选项, 您需要在此处输入** / **"*"。
    
   - 您需要选择 web 侦听器, 或者允许反向代理为您创建一个侦听器。
    
   - **身份验证委派**应设置为**无委派**，但直接客户端身份验证**不应**被允许。
    
   - 规则应设置为**所有用户**。
    
   - 这应是创建此规则所需的所有信息，并且允许你继续操作。
    
4. 需要设置 **Web 服务器**端口，为此，你需要执行以下操作：
    
   - **将请求重定向到 HTTP 端口**，端口号应为 **8080**。
    
   - **将请求重定向到 SSL 端口**，端口号应为 **4443**。
    
5. 一切均配置好后，你需要对其进行保存或应用，然后你将需要测试该规则。
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>使用混合部署配置移动性的自动发现
<a name="ConfigAutoD"> </a>

Skype for Business 服务器中的混合环境是结合了内部部署和 O365 环境的环境。 当您的 Skype for Business 服务器在混合环境中工作时, 自动发现服务需要能够从这些环境中的任一环境找到用户。
  
要让移动客户端发现用户所在位置，需要使用新的统一资源定位器 (URL) 配置自动发现服务。步骤包括：
  
1. 打开 Skype for Business Server 命令行管理程序。
    
2. 运行以下内容, 获取 Skype for business Server 环境的属性**ProxyFQDN**的值:
    
   ```
   Get-CsHostingProvider
   ```

3. 然后，仍在 shell 窗口中，运行：
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    其中 [identity] 使用共享 SIP 地址空间的域名替换。
    
## <a name="test-your-mobility-deployment"></a>测试移动功能部署
<a name="TestMobility"> </a>

部署 Skype for business Server 移动服务和 Skype for business Server 自动发现服务后, 你将需要运行测试事务, 以确保你的部署正确工作。 你可以运行 **Test-CsUcwaConference** 来测试两个用户能否创建和加入会议以及在会议中通信。 你需要两个用户（实际或测试）及其完整凭据来执行此测试。 此命令将同时适用于 Skype for business 客户端和 Lync Server 2013 客户端。
  
对于 Skype for business Server 2015 上的 Lync Server 2010 客户端, 你需要运行**测试 CsMcxP2PIM**进行测试。 您的 Lync Server 2010 用户仍必须是实际用户或预定义的测试用户, 并且您需要其密码凭据。

> [!NOTE]
> 在 Skype for Business Server 2019 中, MCX (移动服务) 对旧式移动客户端的支持不再可用。 所有当前 Skype for business 移动客户端都已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、状态和联系人。 具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>测试 Skype for Business 和 Lync 2013 移动客户端的会议功能

1. 在安装了**Skype For Business Server Management Shell**和**Ocscore**的任何计算机上以**CsAdministrator**角色的成员身份登录。
    
2. 启动**Skype For Business Server 命令行管理**程序 (您可以在 "搜索" 中键入名称, 或选择 "**所有程序**" 并选择它)。
    
3. 在命令行中输入：
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   还可以在脚本中设置凭据并将这些凭据传送给测试 cmdlet。示例如下。
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>测试 Lync 2010 移动客户端的会议功能

> [!NOTE]
> 在 Skype for Business Server 2019 中, MCX (移动服务) 对旧式移动客户端的支持不再可用。 所有当前 Skype for business 移动客户端都已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、状态和联系人。 具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。

1. 在安装了**Skype For Business Server Management Shell**和**Ocscore**的任何计算机上以**CsAdministrator**角色的成员身份登录。
    
2. 启动**Skype For Business Server 命令行管理**程序 (您可以在 "搜索" 中键入名称, 或选择 "**所有程序**" 并选择它)。
    
3. 在命令行中输入：
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   还可以在脚本中设置凭据并将这些凭据传送给测试 cmdlet。示例如下。
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

要进一步查看命令过程，你可以参阅 [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 和 [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。
  
## <a name="configure-for-push-notifications"></a>配置推送通知
<a name="ConfigPush"> </a>

即使 Skype 或 Lync 应用处于非活动状态，也可以向移动设备发送推送通知（以徽章、图标或警告的形式）。 但什么是推送通知？ 它们是事件警报，如新的或错过的 IM 邀请，或收到的语音邮件。 Skype for Business Server 移动服务将这些通知发送到基于云的 Skype for business 服务器推送通知服务, 然后向 Windows Phone 用户发送通知到 Microsoft 推送通知服务 (MSNS)。
  
Lync Server 2013 未更改此功能, 但如果你有 Skype for business 服务器, 你将需要执行以下操作:
  
- 对于 Skype for Business 服务器 Edge 服务器, 请添加新的托管提供商、Microsoft Skype for Business Online, 然后在您的组织和 Skype for business Online 之间设置托管提供商联盟。
    
- 通过运行 **Set-CsPushNotificationConfiguration** cmdlet 启用推送通知。默认情况下，推送通知已关闭。
    
- 测试你的联盟配置和推送通知。
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>针对推送通知配置你的 Skype for Business 边缘服务器

1. 使用**CsAdministrator**角色成员的帐户登录到安装了**Skype For Business Server Management Shell**和**Ocscore**的计算机。
    
2. 启动**Skype For Business Server 命令行管理程序**。
    
3. 添加 Skype for Business Server online 托管提供商。
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   例如：
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 你不能与一个宿主提供程序建立多个联盟关系。因此，如果你已设置一个与 sipfed.online.lync.com 建立了联盟关系的宿主提供程序，请不要为其添加其他宿主提供程序，即使该宿主提供程序的标识不是 SkypeOnline 也是如此。 
  
4. 在 Skype for business Online 中设置你的组织和推送通知服务之间的托管提供程序联合身份验证。 在命令行中，你需要键入：
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>启用推送通知

1. 使用**CsAdministrator**角色成员的帐户登录到安装了**Skype For Business Server Management Shell**和**Ocscore**的计算机。
    
2. 启动**Skype For Business Server 命令行管理程序**。
    
3. 启用推送通知：
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. 启用联盟：
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>测试联盟和推送通知

1. 使用**CsAdministrator**角色成员的帐户登录到安装了**Skype For Business Server Management Shell**和**Ocscore**的计算机。
    
2. 启动**Skype For Business Server 命令行管理程序**。
    
3. 测试联盟配置：
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    例如：
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. 测试你的推送通知：
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    例如：
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>配置移动策略
<a name="ConfigMob"> </a>

你可以使用 Skype for Business 服务器来确定谁可以使用你的移动服务、通过工作、IP 语音 (VoIP) 或视频通话, 以及 VoIP 或视频是否需要 WiFi。 使用通过工号拨号功能，移动用户可以在发出和接收呼叫时使用其工作电话号码，而不是其移动电话号码。 该线路另一端上的人员不会看到移动用户的移动电话号码，并且可以让移动用户避免产生拨出呼叫费用。 设置 VoIP 和视频后，用户可以接收和发出 VoIP 呼叫和视频。 WiFi 用法的设置确定通过蜂窝数据网络使用 WiFi 网络是否需要用户的移动设备。
  
移动、通过工作通话, 并且 VoIP 和视频功能在默认情况下处于启用状态。 禁用了 VoIp 和视频需要 WiFi 的设置。 管理员可以全局、按网站或按用户对其进行更改。
  
若要能够通过工作使用移动功能和通话, 用户必须:
  
- 已启用 Skype for Business 服务器
    
- 启用企业语音。
    
- 分配了**EnableMobility**选项设置为**True**的移动策略。
    
对于希望能使用通过工号拨号功能的用户，他们还必须：
  
- 分配已选择**允许多部电话同时响铃**选项的语音策略。
    
- 分配了**EnableOutsideVoice**设置为**True**的移动策略。
    
> [!NOTE]
> 未启用企业语音的用户可以使用其移动设备发出 Skype 至 Skype VoIP 呼叫，也可以使用“单击以加入”链接来通过移动设备加入会议（如果已为与其关联的语音策略设置相应的选项）。规划主题中有更多详细信息。 
  
### <a name="modify-global-mobility-policy"></a>修改全局移动策略

1. 使用**CsAdministrator**角色成员的帐户登录到安装了**Skype For Business Server Management Shell**和**Ocscore**的计算机。
    
2. 启动**Skype For Business Server 命令行管理程序**。
    
3. 通过键入以下内容来关闭对移动和通过工作全球通话的访问
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > 您可以通过工作来关闭呼叫, 而无需关闭移动访问。 但是, 如果未关闭 "通过工作进行呼叫", 则无法关闭行动。 
  
    有关详细信息, 请参阅[CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-site"></a>按网站修改移动策略

1. 使用**CsAdministrator**角色成员的帐户登录到安装了**Skype For Business Server Management Shell**和**Ocscore**的计算机。
    
2. 启动**Skype For Business Server 命令行管理程序**。
    
3. 你可以创建站点级别的策略、禁用 VoIP 和视频，以及按网站启用“IP 音频需要 WiFi”和“IP 视频需要 WiFi”。键入：
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    在 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps) 中了解更多信息。
    
### <a name="modify-mobility-policy-by-user"></a>按用户修改移动策略

1. 使用**CsAdministrator**角色成员的帐户登录到安装了**Skype For Business Server Management Shell**和**Ocscore**的计算机。
    
2. 启动**Skype For Business Server 命令行管理程序**。
    
3. 创建用户级移动策略, 并通过用户的工作方式关闭移动性和呼叫。 键入：
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    包含示例数据的另一个示例：
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > 您可以通过工作来关闭呼叫, 而无需关闭移动访问。 但是, 如果未关闭 "通过工作进行呼叫", 则无法关闭行动。 
  

