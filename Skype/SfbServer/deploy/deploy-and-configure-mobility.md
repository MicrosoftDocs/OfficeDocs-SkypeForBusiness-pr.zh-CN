---
title: 为 Skype for business Server 部署和配置移动功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文将指导您完成配置现有 Skype for Business Server 安装以使用移动服务的步骤，从而使您的移动设备能够充分利用 Skype for business Server 移动功能。
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029063"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>为 Skype for business Server 部署和配置移动功能  
 
本文将指导您完成配置现有 Skype for Business Server 安装以使用移动服务的步骤，从而使您的移动设备能够充分利用 Skype for business Server 移动功能。
  
查看了[Skype For Business server 的移动性计划](../plan-your-deployment/mobility.md)，应准备好继续执行以下步骤，以将移动性部署到 Skype For business server 环境中。 步骤如下所示（我们将在此表中加入权限列表中）：
  
|**阶段**|**权限**|
|:-----|:-----|
|[创建 DNS 记录](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[修改证书](deploy-and-configure-mobility.md#ModCerts) <br/> |本地管理员  <br/> |
|[配置反向代理](deploy-and-configure-mobility.md#ConfigRP) <br/> |本地管理员  <br/> |
|[为具有混合部署的移动性配置自动发现](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[测试移动性部署](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[配置推送通知](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[配置移动策略](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
以下所有部分都包含假设您已阅读规划主题的步骤。 如果有任何困惑，请随时查看此处的信息。

> [!NOTE]
> Skype for Business Server 2019 中不再提供对旧版移动客户端的 MCX （移动服务）支持。 所有当前 Skype for Business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。 具有使用 MCX 的旧版客户端的用户将需要升级到当前客户端。
  
## <a name="create-dns-records"></a>创建 DNS 记录
<a name="CreateDNSRec"> </a>

您可能已将这些作为 Skype for Business Server 环境的一部分，但您需要创建以下记录才能使自动发现正常工作：
  
- 支持从组织网络内部进行连接的移动用户的内部 DNS 记录。
    
- 支持从组织网络外部连接的移动用户的外部（或公共） DNS 记录。
    
这些记录可以是（主机）名称或 CNAME 记录（无需同时执行这两种操作）。
  
### <a name="create-an-internal-dns-cname-record"></a>创建内部 DNS CNAME 记录

1. 以**Domain Admins**组或**DnsAdmins**组成员的身份登录到网络中的 DNS 服务器。
    
2. 单击 "**开始**"，选择 "**管理工具**" （如果不是 "开始" 菜单上的选项，您可能需要进行**搜索**），然后单击 " **dns** " 以打开 "dns 管理" 管理单元。
    
3. 在控制台窗口的左侧窗格中，需要转到位于 Skype for business Server 前端服务器的主域，然后在此处展开 "**正向查找区域**"。
    
4. 请花点时间查看你的以下哪一项：
    
   - 前端服务器（标准版或企业版）或前端池的任何主机 A 或 AAAA 记录。
    
   - 控制器或控制器池的任何主机 A 或 AAAA 记录（您在部署中可能已有的可选配置）。
    
5. 记下此项后，右键单击您的 SIP 域名，然后从菜单中选择 "**新建别名（CNAME）** "。
    
6. 在 "**别名名称**" 文本框中，为内部自动发现服务 URL 键入 lyncdiscoverinternal. 作为主机名。
    
7. 在**完全限定的域名（FQDN 用于目标主机**中，需要键入或浏览到前端池（或单个前端服务器，或控制器池或控制器）的内部 WEB 服务 FQDN （在上面的步骤4中确定）。 输入此输入时，单击 "确定"。
    
8. 您需要在 Skype for Business Server 环境中支持的每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。
    
### <a name="create-an-external-dns-cname-record"></a>创建外部 DNS CNAME 记录

1. 这些步骤是一般性的，因为我们无法知道您可能正在使用什么公共 DNS 提供程序，但我们仍希望帮助你。请使用能够将新的 DNS 记录放在其中的帐户登录到您的公共 DNS 提供程序。
    
2. 在此时间点，SIP 域应已存在于 Skype for business Server 中。 展开此 SIP 域的**正向查找区域**，或以其他方式打开它。
    
3. 请花点时间查看你的以下哪一项：
    
   - 前端服务器（标准版或企业版）或前端池的任何主机 A 或 AAAA 记录。
    
   - 控制器或控制器池的任何主机 A 或 AAAA 记录（您在部署中可能已有的可选配置）。
    
4. 拥有该信息后，您应该能够选择用于创建**新别名（CNAME）** 的选项。
    
5. 现在，您应该能够输入**别名**，您需要在此处输入外部自动发现服务 URL 的 lyncdiscover.。
    
6. 接下来，应该有一个要输入到**目标主机的 fqdn**中的区域，这将需要是前端池（或单个前端服务器，或控制器池或控制器）的 fqdn，在上面的步骤3中进行了标识。
    
7. 您可能需要在此处保存，或者如果需要在 Skype for Business Server 环境中的每个 SIP 域的正向查找区域中创建其他 CNAME 记录，则应执行此操作，但在准备好后，请保存您的工作。
    
### <a name="create-an-internal-dns-a-record"></a>创建内部 DNS A 记录

1. 以**Domain Admins**组或**DnsAdmins**组成员的身份登录到网络中的 DNS 服务器。
    
2. 单击 "**开始**"，选择 "**管理工具**" （如果不是 "开始" 菜单上的选项，您可能需要进行**搜索**），然后单击 " **dns** " 以打开 "dns 管理" 管理单元。
    
3. 在控制台窗口的左侧窗格中，需要转到位于 Skype for business Server 前端服务器的主域，然后在此处展开 "**正向查找区域**"。
    
4. 请花点时间查看你的以下哪一项：
    
   - 前端服务器（标准版或企业版）或前端池的任何主机 A 或 AAAA 记录。
    
   - 控制器或控制器池的任何主机 A 或 AAAA 记录（您在部署中可能已有的可选配置）。
    
5. 记下此项后，右键单击您的 SIP 域名，然后从菜单中选择 "**新建主机（A 或 AAAA）** "。
    
6. 在 "**名称**" 文本框中，为 "内部自动发现服务" URL 键入 lyncdiscoverinternal. 作为主机名。
    
7. 在 " **IP 地址**" 文本框中，键入前端池（或单个前端服务器，或控制器池或控制器）的内部 WEB 服务 IP 地址，这些地址在上述步骤4中确定。
    
8. 完成此操作后，单击 "**添加主机**"，然后单击 **"确定"**。
    
9. 您需要在 Skype for business Server 环境中支持的每个 SIP 域的正向查找区域中创建新的自动发现 A 或 AAAA 记录。 为此，请根据需要重复步骤6-8 多次。
    
10. 完成后，单击 "**完成**"。
    
### <a name="create-an-external-dns-a-record"></a>创建外部 DNS A 记录

1. 这些步骤是一般性的，因为我们无法知道您可能正在使用什么公共 DNS 提供程序，但我们仍希望帮助你。请使用能够将新的 DNS 记录放在其中的帐户登录到您的公共 DNS 提供程序。
    
2. 在此时间点，SIP 域应已存在于 Skype for business Server 中。 展开此 SIP 域的**正向查找区域**，或以其他方式打开它。
    
3. 请花点时间查看你的以下哪一项：
    
   - 前端服务器（标准版或企业版）或前端池的任何主机 A 或 AAAA 记录。
    
   - 控制器或控制器池的任何主机 A 或 AAAA 记录（您在部署中可能已有的可选配置）。
    
4. 拥有该信息后，您应该能够选择用于创建**新主机 a 或 AAAA**的选项。
    
5. 现在，您应该能够输入**名称**，您需要在此处输入外部自动发现服务 URL 的 lyncdiscover.。
    
6. 接下来，应该有一个区域可在**Ip Addresss**中输入，这将需要是前端池（或单个前端服务器，或控制器池或控制器）的 ip，在上面的步骤3中进行了标识。
    
7. 您可能需要保存到此处，或者，如果需要在每个 SIP 域的正向查找区域中为 Skype for Business Server 环境创建额外的 A 或 AAAA 记录，则应执行此操作，但在准备好后，请保存您的工作。
    
## <a name="modify-certificates"></a>修改证书
<a name="ModCerts"> </a>

如果你对证书规划有疑问，我们已在计划中介绍了[Skype for Business Server 文章的移动性](../plan-your-deployment/mobility.md)方面的问题。 审阅之后，我们将指导您完成以下操作：
  
- 我是否需要新证书？
    
- 从证书颁发机构（CA）请求新证书。
    
- 使用 PowerShell 更新就地证书和替换。
    
- 使用 Microsoft 管理控制台（MMC）中的 "证书" 管理单元检查证书。
    
### <a name="do-i-need-new-certificates"></a>我是否需要新证书？

1. 首先，您可能需要检查并查看哪些证书是现成的，以及它们是否具有所需的条目。 为此，你需要使用本地管理员帐户登录到你的 Skype for Business Server。 此帐户可能还需要对颁发证书颁发机构（CA）拥有权限，其中一些步骤也可能需要。
    
2. 打开 Skype for Business Server 命令行管理程序（如果未将其固定到 "开始" 菜单或任务栏，则可以使用 "搜索" 来查找它）。
    
3. 在尝试添加已更新的证书之前，必须先了解已分配的证书，这一点非常重要。 在命令中，键入：
    
   ```powershell
   Get-CsCertificate
   ```

4. 步骤3中的信息将对您是唯一的。 您需要对其进行查找，以确定是否已为多个项目分配了一个证书，或者是否为需要的不同组件分配了不同的证书。 **使用**参数将告诉你证书的使用方式，以及**指纹**参数将告知你是使用相同的证书还是多个证书。
    
5. 如果我们的 "规划" 部分中有建议的 SAN 条目，那么您是个理想之用。 如果不是，则需要从证书颁发机构请求一个新证书或多个证书（具体取决于您的配置）。
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>从证书颁发机构（CA）请求新证书或证书

1. 检查以查看您拥有的 SAN 条目后，您会知道您有一个**证书**（通过上述步骤进行检查后），并且您了解到您没有所需的所有条目。 需要向你的 CA 发出新的证书请求。 打开 Skype for Business Server PowerShell：
    
   - 对于缺少的自动发现服务 SAN （将-Ca 参数替换为你自己的证书颁发机构路径）：
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 现在，如果您有多个 SIP 域，则不能使用 AllSipDomain 参数，如上面的示例中所示。 你需要改为使用 DomainName 参数。 使用 DomainName 参数时，您必须定义 lyncdiscoverinternal. 和 lyncdiscover. 记录的 FQDN。 例如（将-Ca 参数替换为您自己的证书颁发机构路径）：
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. 或者，在检查以查看您拥有的 SAN 条目之后，您发现您有**多个证书**没有您所需的所有条目。 需要向你的 CA 发出新的证书请求。 打开 Skype for Business Server PowerShell：
    
   - 对于缺少的自动发现服务 SAN （将-Ca 参数替换为你自己的证书颁发机构路径）：
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 现在，如果您有多个 SIP 域，则不能使用 AllSipDomain 参数，如上面的示例中所示。 你需要改为使用 DomainName 参数。 使用 DomainName 参数时，您必须定义 lyncdiscoverinternal. 和 lyncdiscover. 记录的 FQDN。 例如（将-Ca 参数替换为您自己的证书颁发机构路径）：
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - 在 CA 生成新证书后，您需要对其进行分配。
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序分配证书

- 根据您在上面的 "我需要新的认证" 一节中找到的内容，您需要运行以下各**项之一**。
    
  - 如果你有一个证书用于所有内容（指纹完全相同），则需要运行以下命令：
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 如果你的事物有不同的证书（指纹都是不同的），请改为运行以下命令：
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>在 Microsoft 管理控制台（MMC）中查看证书

1. 您可以选择使用 MMC 的 "证书" 管理单元查看您的证书。 只需将 MMC 键入到搜索中，就应将其作为应用程序选项进行弹出。
    
2. 若要添加证书管理单元，需要单击 "**文件**"，然后 "**添加/删除管理单元 ...** " （或键盘快捷方式**Ctrl + M**也有效）。 **证书**将是左侧窗格中的一个选项，在弹出窗口中依次选择 "**计算机帐户**" 和 "**下一步**"。
    
3. 仍在弹出窗口中，在您需要查看的证书所在的计算机上执行此操作时，请在**本地计算机**上保留所选内容（如果这样做的话）。 如果正在远程计算机上工作，请将单选按钮更改为**另一台计算机**，然后输入该计算机的 FQDN 或使用 "**浏览**" 按钮，通过 AD 搜索该计算机。 选择计算机后，需要在准备好后单击 "**完成**"，然后单击 **"确定"** 以将该管理单元添加到 MMC。
    
4. 在 MMC 的左侧窗格中展开 "**证书**" 部分。 同时展开 "**个人**" 文件夹，然后选择 "**证书**"。 这将允许您查看此存储中的证书。
    
5. 您需要找到要查看的证书，右键单击该证书，然后选择 "**打开**"。
    
    > [!NOTE]
    > 您如何知道这是什么证书？ 它应该是分配给服务器场所有内容的单个证书，或者您可能有不同事物的多个证书，如默认设置、内部 Web 服务等。在这种情况下，您可能需要查看多个证书。 多个证书将具有相同的指纹。 
  
6. 进入**证书**视图后，请选择 "**详细信息**"。 这将允许您在选择 "**主题**" 时查看证书主题名称，并显示分配的主题名称和关联的属性。
    
7. 你还需要检查**主题替代名称**条目。 您将找到以下一个或多个选项：
    
   - 此池的池名称，如果不是池，则为单个服务器名称。
    
   - 证书分配到的服务器名称。
    
   - 简单的 URL 记录，通常是 "符合" 和 "拨入"。
    
   - Web 服务内部和 Web 服务外部名称（例如，webpool01.contoso.net、webpool01.contoso.com），这取决于在拓扑生成器和替代 Web 服务选择中所做的选择。
    
   - 如果已分配，则为 lyncdiscover.。\<sipdomain\>和 lyncdiscoverinternal.。\<sipdomain\>记录。
    
     如果分配了多个证书，则需要检查多个证书（请选中上面的注释）。
    
8. 如果找到 lyncdiscover.，则为。\<sipdomain\>和 lyncdiscoverinternal.。\<sipdomain\>记录，您已进行了此配置。 您可以关闭 MMC。
    
9. 如果未分配，则需要创建新的证书请求（如上所述），或者需要将其安装在 post 请求中（我们建议上述针对此的 PowerShell）。
    
## <a name="configure-the-reverse-proxy"></a>配置反向代理
<a name="ConfigRP"> </a>

下面的步骤并不应完全遵循。 这是因为在产品的早期版本中，我们已向你介绍了，例如，配置威胁管理网关（TMG），如果你未使用，则需要从那里使用自己的版本。
  
TMG 不再由 Microsoft 作为产品提供，如果仍需要对其进行配置，则可以查看[Lync Server 2013 步骤](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)。 但是，以下信息的预期更为普遍，即使无法为每个反向代理提供具体的演练步骤，也是如此。
  
要考虑的主要事项有两个：
  
- 您是否要通过 HTTPS 执行初始自动发现请求（我们建议这样做）？
    
  - 如果您有 web 发布规则，则需要对其进行修改。
    
  - 如果还没有 web 发布规则，则需要创建它。
    
- 如果你正在通过 HTTP 执行初始自动发现请求，则还需要创建或修改该规则。
    
> [!NOTE]
> **重要说明**代理超时值是一个数字，该数字将因部署而异。 您应监视您的部署并修改客户端的最佳体验的价值。 您可以将值设置为低达200。 如果您在您的环境中支持 Lync 移动客户端，则应将值设置为960，以允许来自 Office 365 的推送通知超时（超时值为900）。 很可能需要增加超时值，以避免在值太低时客户端断开连接，或者如果在客户端断开连接后，通过代理连接不会断开连接，则减少号码。 监视和设置环境的常规设置是确定此值的适当设置的唯一准确方式。
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>修改外部自动发现 SAN 和 URL 的现有 web 发布规则

1. 打开反向代理接口。
    
2. 您需要找到 web 发布规则，然后选择 "编辑" 选项（它可能位于菜单或选项卡上，具体取决于反向代理配置）。
    
3. 应有一个区域，指出该 web 发布规则的应用内容。 您需要为传入的网站或网站的请求修改此规则。 你**将添加**新条目。
    
4. 键入自动发现网站的名称（我们将使用的示例是 lyncdiscover.contoso.com），然后单击 **"确定" 或 "** **保存**"，具体取决于反向代理的格式。
    
5. 您可能具有一个新证书，其中包含自动发现 SAN 条目。 还需要安装并配置为根据反向代理的设置使用。 完成配置后，请务必保存所有内容。
    
6. 如果反向代理具有**测试**功能，请使用它，以确保一切正常工作。
    
7. 现在，如果您的环境中有一个控制器或控制器池（这意味着您有第二个规则），您可能需要重复这些步骤。
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>为外部自动发现 URL 创建 web 发布规则

1. 打开反向代理接口。
    
2. 您需要在界面中创建 web 发布规则的位置查找，然后选择 "**新建**" 或 "**创建**" 选项（它可能位于菜单或选项卡上，具体取决于反向代理配置）。 您正在寻找创建新的 web 发布规则的选项。
    
3. 通常情况下，您需要输入以下信息：
    
   - **名称**：规则的名称
    
   - **规则操作**：在这种情况下，这是**允许**的规则，您可以通过反向代理进行某个传递。
    
   - 您要选择的**发布**规则或选项为**单个网站或负载平衡器**。
    
   - 这需要是用于外部访问的**SSL** ，请选择该选项。
    
   - 您需要发布**内部发布**的路径，并在前端池的负载平衡器（或控制器池的负载平衡器的 fqdn （如果有））中输入外部 Web 服务的 fqdn，例如，sfb_pool01 为 "contoso. 本地"。
    
   - 应键入** / *** 作为要发布的路径，但还需要**转发原始主机头**。
    
   - 将有一个用于**公用或外部名称**详细信息或信息的选项。 你可以在此处输入以下内容：
    
   - **接受请求**，但它应针对域名。
    
   - 对于**名称**，您应输入 " **lyncdiscover."。** <sipdomain>（这是外部自动发现服务 URL）。 现在，如果要为前端池上的外部 Web 服务 URL 创建规则，则需要为前端池上的外部 Web 服务键入 FQDN （例如，lyncwebextpool01.contoso.com）。
    
   - 将有一个**路径**选项，您需要在此处输入** / ***。
    
   - 你需要选择具有最新公共证书的**SSL 侦听器**。
    
   - **身份验证委派**应设置为 "**无委派**"，但**应**允许直接客户端身份验证。
    
   - 应将规则设置为 "**所有用户**"。
    
   - 这应该是创建此规则所需的所有信息，并允许您继续操作。
    
4. 您需要确保**原始主机标头**已转发。
    
5. 还需要设置**Web 服务器**端口，您需要执行以下操作：
    
   - 将**请求重定向到 HTTP 端口**，端口号应为**8080**。
    
   - 将**请求重定向到 SSL 端口**，端口号应为**4443**。
    
6. 配置所有内容后，需要保存或应用这些内容，然后您将需要测试该规则。
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>为端口80创建 web 发布规则（可选）

1. 打开反向代理接口。
    
2. 您需要在界面中创建 web 发布规则的位置查找，然后选择 "**新建**" 或 "**创建**" 选项（它可能位于菜单或选项卡上，具体取决于反向代理配置）。 您正在寻找创建新的 web 发布规则的选项。
    
3. 通常情况下，您需要输入以下信息：
    
   - **名称**：规则的名称
    
   - **规则操作**：在这种情况下，这是**允许**的规则，您可以通过反向代理进行某个传递。
    
   - 您要选择的**发布**规则或选项为**单个网站或负载平衡器**。
    
   - 这需要是**连接到发布的 Web 服务器或服务器场的非安全连接**。
    
   - 您需要发布**内部发布**的路径，并输入前端池的负载平衡器的**VIP 地址**的 FQDN，例如，sfb_pool01 为 "contoso. 本地"。
    
   - 应键入** / *** 作为要发布的路径，但还需要**转发原始主机头**。
    
   - 将有一个用于**公用或外部名称**详细信息或信息的选项。 你可以在此处输入以下内容：
    
   - **接受请求**，但它应针对域名。
    
   - 对于**名称**，您应输入 " **lyncdiscover."。** <sipdomain>（这是外部自动发现服务 URL）。
    
   - 将有一个**路径**选项，您需要在此处输入** / ***。
    
   - 你需要选择 web 侦听器，或允许反向代理为你创建一个侦听器。
    
   - **身份验证委派**应设置为 "**无委派**"，但**不应**允许直接客户端身份验证。
    
   - 应将规则设置为 "**所有用户**"。
    
   - 这应该是创建此规则所需的所有信息，并允许您继续操作。
    
4. 需要设置**Web 服务器**端口，将需要执行以下操作：
    
   - 将**请求重定向到 HTTP 端口**，端口号应为**8080**。
    
   - 将**请求重定向到 SSL 端口**，端口号应为**4443**。
    
5. 配置所有内容后，需要保存或应用这些内容，然后您将需要测试该规则。
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>为具有混合部署的移动性配置自动发现
<a name="ConfigAutoD"> </a>

Skype for Business Server 中的混合环境是结合了本地和 O365 环境的环境。 当您的 Skype for Business Server 在混合环境中工作时，自动发现服务需要能够从这些环境中的任一环境中查找用户。
  
若要让移动客户端发现用户所在的位置，则需要使用新的统一资源定位器（URL）配置自动发现服务。 步骤如下：
  
1. 打开 Skype for Business Server 命令行管理程序。
    
2. 运行以下命令，获取 Skype for Business Server 环境的属性**ProxyFQDN**的值：
    
   ```powershell
   Get-CsHostingProvider
   ```

3. 然后，仍在命令行管理程序窗口中运行：
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    其中 [identity] 使用共享 SIP 地址空间的域名替换。
    
## <a name="test-your-mobility-deployment"></a>测试移动性部署
<a name="TestMobility"> </a>

部署 Skype for Business Server 移动服务和 Skype for business Server 自动发现服务后，您需要运行测试事务，以确保部署的工作正确。 您可以运行**test-csucwaconference**以测试两个用户在会议中创建、加入和交流的能力。 你将需要两个用户（实际或测试）及其完整凭据来执行此测试。 此命令将适用于 Skype for business 客户端和 Lync Server 2013 客户端。
  
对于 Skype for Business Server 2015 上的 Lync Server 2010 客户端，您需要运行**测试 test-csmcxp2pim**以进行测试。 你的 Lync Server 2010 用户仍必须是实际用户或预定义的测试用户，并且你将需要其密码凭据。

> [!NOTE]
> Skype for Business Server 2019 中不再提供对旧版移动客户端的 MCX （移动服务）支持。 所有当前 Skype for Business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。 具有使用 MCX 的旧版客户端的用户将需要升级到当前客户端。
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>为 Skype for Business 和 Lync 2013 移动客户端测试会议

1. 在安装了**Skype For Business Server 命令行管理**程序和**Ocscore**的任何计算机上以**CsAdministrator**角色的成员身份登录。
    
2. 启动**Skype For Business Server 命令行管理程序**（可以在 "搜索" 中键入名称，也可以选择 "转到**所有程序**" 并选择它）。
    
3. 在命令行中，输入：
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   此外，还可以在脚本中设置凭据并将其传递给测试 cmdlet。 下面举例介绍了这一点。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>为 Lync 2010 移动客户端测试会议

> [!NOTE]
> Skype for Business Server 2019 中不再提供对旧版移动客户端的 MCX （移动服务）支持。 所有当前 Skype for Business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。 具有使用 MCX 的旧版客户端的用户将需要升级到当前客户端。

1. 在安装了**Skype For Business Server 命令行管理**程序和**Ocscore**的任何计算机上以**CsAdministrator**角色的成员身份登录。
    
2. 启动**Skype For Business Server 命令行管理程序**（可以在 "搜索" 中键入名称，也可以选择 "转到**所有程序**" 并选择它）。
    
3. 在命令行中，输入：
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   此外，还可以在脚本中设置凭据并将其传递给测试 cmdlet。 下面举例介绍了这一点。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

若要进一步查看命令过程，可以查看[test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)和[test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。
  
## <a name="configure-for-push-notifications"></a>配置推送通知
<a name="ConfigPush"> </a>

即使在 Skype 或 Lync 应用处于非活动状态时，也可以将徽章、图标或警报等推送通知发送到移动设备。 但什么是推送通知？ 它们是事件警报，如新的或错过的 IM 邀请，或接收到的语音邮件。 Skype for Business Server 移动服务将这些通知发送到基于云的 Skype for Business Server 推送通知服务，后者随后会将通知发送给 Windows Phone 用户的 Microsoft 推送通知服务（MSNS）。
  
此功能在 Lync Server 2013 中保持不变，但如果你有 Skype for Business 服务器，你将需要执行以下操作：
  
- 对于 Skype for Business Server 边缘服务器，请添加新的托管提供程序、Microsoft Skype for Business Online，然后在您的组织和 Skype for business Online 之间设置托管提供程序联盟。
    
- 通过运行**CsPushNotificationConfiguration** cmdlet 启用推送通知。 默认情况下，推送通知已关闭。
    
- 测试联合身份验证配置和推送通知。
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>为推送通知配置 Skype for Business 边缘服务器

1. 使用**CsAdministrator**角色的成员的帐户登录到安装了**Skype For Business Server 命令行管理程序**和**Ocscore**的计算机。
    
2. 启动**Skype For Business Server 命令行管理程序**。
    
3. 添加 Skype for Business Server online 托管提供商。
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   例如：
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 同一个托管提供程序不能有多个联合关系。 因此，如果您已经设置了与 sipfed.online.lync.com 具有联合关系的托管提供程序，则不要为其添加另一个托管提供程序，即使承载提供程序的标识是 SkypeOnline 以外的其他内容也是如此。 
  
4. 在您的组织和 Skype for Business Online 的推送通知服务之间设置托管提供程序联盟。 在命令行中，需要键入以下内容：
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>启用推送通知

1. 使用**CsAdministrator**角色的成员的帐户登录到安装了**Skype For Business Server 命令行管理程序**和**Ocscore**的计算机。
    
2. 启动**Skype For Business Server 命令行管理程序**。
    
3. 启用推送通知：
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. 启用联盟：
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>测试联盟和推送通知

1. 使用**CsAdministrator**角色的成员的帐户登录到安装了**Skype For Business Server 命令行管理程序**和**Ocscore**的计算机。
    
2. 启动**Skype For Business Server 命令行管理程序**。
    
3. 测试联合身份验证配置：
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    例如：
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. 测试推送通知：
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    例如：
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>配置移动策略
<a name="ConfigMob"> </a>

您可以使用 Skype for Business Server 来确定哪些用户可以使用移动服务、通过工作呼叫、IP 语音（VoIP）或视频，以及 VoIP 或视频是否需要 WiFi。 通过工作进行呼叫可让移动用户在发出和接收呼叫时使用其工作电话号码，而不是其移动电话号码。 行另一端的人将看不到移动用户的手机号码，并允许移动用户避免传出呼叫费用。 在设置 VoIP 和视频时，用户可以采用并发出 VoIP 呼叫和视频。 WiFi 使用的设置决定了用户的移动设备是否需要通过蜂窝数据网络使用 WiFi 网络。
  
默认情况下，移动、通过工作呼叫以及 VoIP 和视频功能均已启用。 禁用 VoIP 和视频需要 WiFi 的设置。 管理员可以按网站或按用户更改全局权限。
  
若要能够通过工作使用移动功能和呼叫，用户必须：
  
- 为 Skype for Business Server 启用
    
- 启用企业语音。
    
- 分配了一个将**EnableMobility**选项设置为**True**的移动策略。
    
为使用户能够通过工作使用呼叫，他们还需要：
  
- 为选择 "**启用同时响铃的电话**" 选项分配了语音策略。
    
- 分配了一个将**EnableOutsideVoice**设置为**True**的移动策略。
    
> [!NOTE]
> 未启用企业语音的用户可以使用其移动设备进行 Skype 到 Skype VoIP 呼叫，也可以在移动设备上使用 "单击此处加入会议" （如果为其关联的语音策略设置了相应的选项）加入会议。带有. 规划主题中有更多详细信息。 
  
### <a name="modify-global-mobility-policy"></a>修改全局移动策略

1. 使用**CsAdministrator**角色的成员的帐户登录到安装了**Skype For Business Server 命令行管理程序**和**Ocscore**的计算机。
    
2. 启动**Skype For Business Server 命令行管理程序**。
    
3. 通过键入以下内容，禁止访问移动性并通过工作全球化呼叫：
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > 您可以在不关闭对移动性的访问的情况下关闭通过工作的呼叫。 但您不能关闭移动功能，而无需通过工作关闭呼叫。 
  
    有关详细信息，请参阅[set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-site"></a>按网站修改移动策略

1. 使用**CsAdministrator**角色的成员的帐户登录到安装了**Skype For Business Server 命令行管理程序**和**Ocscore**的计算机。
    
2. 启动**Skype For Business Server 命令行管理程序**。
    
3. 您可以创建站点级别的策略，关闭 VoIP 和视频，启用 IP 音频的需要 WiFi，并需要按站点的 IP 视频的 WiFi。 类型：
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    有关详细信息，请参阅[set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-user"></a>按用户修改移动策略

1. 使用**CsAdministrator**角色的成员的帐户登录到安装了**Skype For Business Server 命令行管理程序**和**Ocscore**的计算机。
    
2. 启动**Skype For Business Server 命令行管理程序**。
    
3. 创建用户级别移动策略，并通过用户的工作方式关闭移动性和呼叫。 类型：
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    示例数据的另一个示例：
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > 您可以在不关闭对移动性的访问的情况下关闭通过工作的呼叫。 但您不能关闭移动功能，而无需通过工作关闭呼叫。 
  

