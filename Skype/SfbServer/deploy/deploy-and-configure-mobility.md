---
title: 部署和配置 Skype for Business Server 2015 的移动功能
ms.author: heidip
author: microsoftheidi
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 这篇文章将引导您完成配置为使用移动服务，使您能够充分利用 Skype 业务服务器移动功能的移动设备业务服务器 2015年安装现有 Skype 的步骤。
ms.openlocfilehash: c23974477ec815fca9c0cd3d78ac7acc0b81912e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server-2015"></a>部署和配置 Skype for Business Server 2015 的移动功能
 
这篇文章将引导您完成配置为使用移动服务，使您能够充分利用 Skype 业务服务器移动功能的移动设备业务服务器 2015年安装现有 Skype 的步骤。
  
我们已看过[规划业务服务器 2015年的 Skype 的移动性](../plan-your-deployment/mobility.md)文章，您应该可以继续下面的步骤将部署移动到您 Skype 业务服务器 2015年环境。 步骤如下所示（并且此表中包含权限列表）：
  
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
  
## <a name="create-dns-records"></a>创建 DNS 记录
<a name="CreateDNSRec"> </a>

您可能已经为您的业务服务器环境中，Skype 的一部分，但您需要创建以下有关自动搜索工作记录：
  
- 支持从组织网络内部进行连接的移动用户的内部 DNS 记录。
    
- 支持从组织网络外部进行连接的移动用户的外部（或公共）DNS 记录。
    
这些记录可以是 A（主机）名称或 CNAME 记录（你不必同时创建两者，我们这里只是将步骤都介绍一遍）。
  
### <a name="create-an-internal-dns-cname-record"></a>创建内部 DNS CNAME 记录

1. 以 **Domain Admins** 组成员或 **DnsAdmins** 组成员的身份登录网络中的 DNS 服务器。
    
2. 单击**开始**，选择**管理工具**（如果它不是“开始”菜单的选项，你可能需要对其进行**搜索**），然后单击 **DNS** 以打开 DNS 管理单元。
    
3. 在控制台窗口的左侧窗格中，您需要转到域的业务服务器的前端服务器，对于家庭到您 Skype 就展开**正向搜索区域**存在。
    
4. 检查一下你是否具有以下记录：
    
   - 您的前端服务器 （常用或企业） 或前端池的任何主机 A 或 AAAA 记录。
    
   - 任何主机 A 或 AAAA 记录为主任或主任池 （部署中可能会有可选配置）。
    
5. 记下此信息后，右键单击你的 SIP 域名，然后从菜单中选择**新建别名 (CNAME)**。
    
6. 在**别名**文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。
    
7. 在**完全合格的域名称 (FQDN 目标主机的**，您需要键入或浏览到内部 Web 服务 FQDN 前端池 （或单个前端服务器，或总监池或控制器），在上面的步骤 4 中标识。 输入后，单击“确定”。
    
8. 您将需要在您 Skype 业务服务器环境中支持每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。
    
### <a name="create-an-external-dns-cname-record"></a>创建外部 DNS CNAME 记录

1. 这些步骤是常规步骤，因为我们无法知道你正在使用的是哪个公共 DNS 提供程序，但我们仍希望帮助你排忧解难。请使用能够创建新的 DNS 记录的帐户登录到你的公共 DNS 提供程序。
    
2. 在此时间点，SIP 域应该存在存在于 Skype 业务服务器 2015年个。 请展开此 SIP 域的**正向查找区域**，否则请打开它。
    
3. 检查一下你是否具有以下记录：
    
   - 您的前端服务器 （常用或企业） 或前端池的任何主机 A 或 AAAA 记录。
    
   - 任何主机 A 或 AAAA 记录为主任或主任池 （部署中可能会有可选配置）。
    
4. 拥有该信息后，应该能够选择用于**新建别名 (CNAME)** 的选项。
    
5. 现在，你应该能够输入**别名**，你需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。
    
6. 下一步应该有一个区域进入一个**目标主机的 FQDN**，则需要为前端池 （或单个前端服务器，或总监池或控制器），上面的第 3 步中标识出的 FQDN。
    
7. 您可能需要保存在这里，或者如果您需要在您 Skype 业务服务器环境中的每个 SIP 域的正向查找区域中创建附加的 CNAME 记录，您应该做，但一旦你已准备好，保存您的工作。
    
### <a name="create-an-internal-dns-a-record"></a>创建内部 DNS A 记录

1. 以 **Domain Admins** 组成员或 **DnsAdmins** 组成员的身份登录网络中的 DNS 服务器。
    
2. 单击**开始**，选择**管理工具**（如果它不是“开始”菜单的选项，你可能需要对其进行**搜索**），然后单击 **DNS** 以打开 DNS 管理单元。
    
3. 在控制台窗口的左侧窗格中，您需要转到域的业务服务器的前端服务器，对于家庭到您 Skype 就展开**正向搜索区域**存在。
    
4. 检查一下你是否具有以下记录：
    
   - 您的前端服务器 （常用或企业） 或前端池的任何主机 A 或 AAAA 记录。
    
   - 任何主机 A 或 AAAA 记录为主任或主任池 （部署中可能会有可选配置）。
    
5. 记下此信息后，右键单击你的 SIP 域名，然后从菜单中选择**新建主机 (A 或 AAAA)**。
    
6. 在**名称**文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。
    
7. 在**IP 地址**文本框中，键入前端池 （或单个前端服务器，或总监池或控制器），内部 Web 服务 IP 地址标识在上面的步骤 4 中。
    
8. 完成此操作后，单击**添加主机**，然后单击**确定**。
    
9. 您将需要在您 Skype 业务服务器环境中支持每个 SIP 域的正向查找区域中创建新的自动发现 A 或 AAAA 记录。 为此，请根据需要多次重复步骤 6-8。
    
10. 完成后，单击**完成**。
    
### <a name="create-an-external-dns-a-record"></a>创建外部 DNS A 记录

1. 这些步骤是常规步骤，因为我们无法知道你正在使用的是哪个公共 DNS 提供程序，但我们仍希望帮助你排忧解难。请使用能够创建新的 DNS 记录的帐户登录到你的公共 DNS 提供程序。
    
2. 在此时间点，SIP 域应该存在存在于 Skype 业务服务器 2015年个。 请展开此 SIP 域的**正向查找区域**，否则请打开它。
    
3. 检查一下你是否具有以下记录：
    
   - 您的前端服务器 （常用或企业） 或前端池的任何主机 A 或 AAAA 记录。
    
   - 任何主机 A 或 AAAA 记录为主任或主任池 （部署中可能会有可选配置）。
    
4. 拥有该信息后，应该能够选择用于创建**新主机 A 或 AAAA** 的选项。
    
5. 现在，你应该能够输入**名称**，你需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。
    
6. 下一步应在**IP 地址**中输入区域，这将需要前端池 （或单个前端服务器，或总监池或控制器），在上面的步骤 3 中标识的 IP。
    
7. 您可能需要保存在这里，或者如果您需要创建其他 A 或 AAAA 记录每个 SIP 域的正向查找区域中供您的企业服务器环境的 Skype，您应该做的但一次就可以，保存您的工作。
    
## <a name="modify-certificates"></a>修改证书
<a name="ModCerts"> </a>

如果您有关于规划围绕证书的问题，我们已经记录，在我们[规划业务服务器 2015年的 Skype 的移动性](../plan-your-deployment/mobility.md)的文章。 阅读该文章后，我们将引导你完成以下步骤：
  
- 是否需要新证书？
    
- 从你的证书颁发机构 (CA) 请求新证书。
    
- 使用 PowerShell 通过替换内容更新你的就地证书。
    
- 检查使用证书管理单元在 Microsoft 管理控制台 (MMC) 的证书。
    
### <a name="do-i-need-new-certificates"></a>是否需要新证书？

1. 首先，你可能需要检查哪些证书是就地证书，以及它们是否具有所需的条目。 为此，您需要登录到您的业务服务器 2015年服务器的本地管理员帐户的 Skype。 此帐户可能还需要对证书颁发机构 (CA) 具有权限才能执行下面的某些步骤。
    
2. 打开 Skype 业务服务器命令行管理程序 （您可以使用搜索来找到它，如果您没有固定到您的开始菜单或任务条）。
    
3. 你必须了解在尝试添加更新证书之前已分配哪些证书。因此，在命令行中键入：
    
   ```
   Get-CsCertificate
   ```

4. 步骤 3 中的信息对你具有唯一性。你需要仔细检查，以确定你是否具有为所有内容分配的单个证书，或者是否具有为所需的不同组件分配的不同证书。**Use** 参数将告知你证书的使用方式，**Thumbprint** 参数将告知你所有证书都相同还是具有多个证书。
    
5. 如果你已在规划部分中建议 SAN 条目，则可方便使用。如果没有，你需要从你的证书颁发机构请求一个新证书或多个证书（具体取决于你的配置）。
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>从你的证书颁发机构 (CA) 请求一个新证书或多个证书。

1. 检查你具有哪些 SAN 条目后，你就知道你具有**单个证书**（通过上述步骤检查后），并且你知道自己没有所需的所有条目。 需要向你的 CA 发出新证书请求。 打开您的 Skype 业务服务器 PowerShell:
    
   - 对于缺少的自动发现服务 SAN（将 -Ca 参数替换为你自己的证书颁发机构路径）：
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 现在，如果你有多个 SIP 域，则无法使用如上述示例中所示的 AllSipDomain 参数。你需要改为使用 DomainName 参数。当你使用 DomainName 参数时，你必须为 lyncdiscoverinternal 和 lyncdiscover 记录定义 FQDN。例如（将 -Ca 参数替换为你自己的证书颁发机构路径）：
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. 或者，检查你具有哪些 SAN 条目后，你发现你具有**多个证书**，其中并不包含你所需的所有条目。 需要向你的 CA 发出新证书请求。 打开您的 Skype 业务服务器 PowerShell:
    
   - 对于缺少的自动发现服务 SAN（将 -Ca 参数替换为你自己的证书颁发机构路径）：
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 现在，如果你有多个 SIP 域，则无法使用如上述示例中所示的 AllSipDomain 参数。你需要改为使用 DomainName 参数。当你使用 DomainName 参数时，你必须为 lyncdiscoverinternal 和 lyncdiscover 记录定义 FQDN。例如（将 -Ca 参数替换为你自己的证书颁发机构路径）：
    
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
    
3. 仍在弹出窗口中，你极有可能在承载需要查看的证书的计算机上执行此操作，因此如果是那样，请选择**本地计算机**。 如果你正在远程计算机上工作，请将单选按钮更改为**其他计算机**，然后输入该计算机的 FQDN 或使用**浏览**按钮通过 AD 搜索该计算机。 选择的计算机后, 您需要**完成**准备完成后，单击，然后单击**确定**以将该管理单元添加到 MMC。
    
4. 展开在 MMC 的左侧窗格中的**证书**部分。 还需展开**个人**文件夹，然后选择**证书**。 这样，你可以在此存储中查看证书。
    
5. 你需要查找要查看的证书，右键单击它，然后选择**打开**。
    
    > [!NOTE]
    > 你如何知道这是什么证书？ 它应该是分配给您的服务器场中，所有内容都是单个证书或可能有的不同技能，如默认值、 内部 Web 服务等多个证书，这种情况下，您可能需要查看多个证书。 多个证书将具有相同的指纹。 
  
6. 进入**证书**视图后，选择**详细信息**。这样，你可以在选择**主题**时看到证书主题名称，并且会显示分配的主题名称和关联的属性。
    
7. 你还需要检查**使用者替代名称**条目。你将发现以下一个或多个条目：
    
   - 为该池的池名称或如果此单个服务器名称不是一个池。
    
   - 向其分配证书的服务器名称。
    
   - 简单 URL 记录，一般为 meet 和 dialin。
    
   - Web 服务内部和 Web 服务外部名称 （例如，webpool01.contoso.net，webpool01.contoso.com），根据所做的选择中拓扑生成器和覆盖的 Web 服务选择。
    
   - 如果已分配，lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>记录。
    
    如果分配有多个证书，你需要对其进行检查（查看上述备注）。
    
8. 因此，如果您发现 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>的记录，您果然已经配置。 你可以关闭 MMC。
    
9. 如果未分配这些证书，你需要发出新证书请求（上面概述）或需要在请求后进行安装（我们建议使用上述 PowerShell 实现该目的）。
    
## <a name="configure-the-reverse-proxy"></a>配置反向代理
<a name="ConfigRP"> </a>

不应严格遵循以下步骤。因为在该产品的早期版本中，我们已引导你配置 Threat Management Gateway (TMG)，如果你未使用该产品，你需要从其创建自己的版本。
  
作为一种产品，Microsoft 不再提供 TMG，如果仍然需要对其进行配置，您可以查看[Lync Server 2013 步骤](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)。 但以下信息的目的是更通常会有帮助，即使没有我们可以为每个反向代理有提供特定演练步骤的方法。
  
需要考虑以下两个主要事项：
  
- 是否要通过 HTTPS（推荐）执行你的初始自动发现请求？
    
  - 如果你具有 Web 发布规则，则需要对其进行修改。
    
  - 如果你还没有 Web 发布规则，则需要进行创建。
    
- 如果你正在通过 HTTP 执行你的初始自动发现请求，则还需要创建或修改该规则。
    
> [!NOTE]
> **重要**代理服务器的超时值是大量部署部署而异。 应监视您的部署，并修改客户端的最佳体验的值。 您可以将值设置为 200 低。 如果您在您的环境中支持 Lync 移动客户端，您应将值设置为 960 从 Office 365 的推式通知超时允许其超时值为 900。 很可能需要增大超时值，以避免客户端断开连接时的值是太低，或减少的数量，如果通过代理服务器建立连接，请勿断开连接，但清除客户端已断开连接后很长时间。 监视和基线什么是适合您的环境通常是只有准确的方法来确定此值的相应设置。
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>为你的外部自动发现 SAN 和 URL 修改现有 Web 发布规则

1. 打开您的反向代理界面。
    
2. 您需要找到您的 web 发布规则，并选择编辑选项 （它可能在菜单或选项卡，具体取决于您的反向代理配置）。
    
3. 应指出此 web 发布规则应用于某个区域。 你需要为传入站点或站点请求修改此规则。 你要**添加**新条目。
    
4. 键入网站名称的自动发现 （我们将使用的示例中为 lyncdiscover.contoso.com），并单击**确定**或**保存**，具体取决于您的反向代理服务器的格式。
    
5. 你可能会有一个其中具有自动发现 SAN 条目的新证书。 需要同时安装并配置用于根据反向代理服务器的设置。 配置完成后，请务必保存所有内容。
    
6. 如果您的反向代理服务器具有**测试**功能，然后请使用它，以确保一切正常。
    
7. 现在，您可能需要重复这些步骤，如果您有一个控制器或控制器池环境中的 （这意味着您拥有第二条规则）。
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>为外部自动发现 URL 创建 web 发布规则

1. 打开您的反向代理界面。
    
2. 您需要找到其中界面中创建 web 发布规则，并选择**新建**或**创建**选项 （它可能在菜单或选项卡，具体取决于您的反向代理配置）。 你要查找用于创建新的 Web 发布规则的选项。
    
3. 通常，你需要输入以下信息：
    
   - **名称**：规则的名称
    
   - **规则操作**：**允许**规则在这种情况下，要让东西通过反向代理服务器。
    
   - 你选择的**发布**规则或选项将为**单个网站或负载平衡器**。
    
   - 这需要为 **SSL** 以供外部访问，请选择该选项。
    
   - 您将需要为**内部发布**，发布路径和前端池的负载平衡器 （或如果您有一个导演池的负载平衡器的 FQDN） 上的外部 Web 服务输入的 FQDN，一个例子就是 sfb_pool01.contoso.local。
    
   - 您应该键入**/**为路径，才能发布，但您还需要**转发原始主机头**。
    
   - 有一个**公共或外部名称**详细信息或信息的选项。你可在其中输入以下内容：
    
   - **接受请求**，但应为域名。
    
   - 对于**名称**，你应输入 **lyncdiscover.** <sipdomain>（这是外部的自动发现服务 URL）。 现在，如果前端池上的外部 Web 服务 url，您正在创建一条规则，您需要键入 FQDN 的前端池 (例如，lyncwebextpool01.contoso.com) 上的外部 Web 服务。
    
   - 将**路径**选项，您将需要输入**/**在此处。
    
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

1. 打开您的反向代理界面。
    
2. 您需要找到其中界面中创建 web 发布规则，并选择**新建**或**创建**选项 （它可能在菜单或选项卡，具体取决于您的反向代理配置）。 你要查找用于创建新的 Web 发布规则的选项。
    
3. 通常，你需要输入以下信息：
    
   - **名称**：规则的名称
    
   - **规则操作**：**允许**规则在这种情况下，要让东西通过反向代理服务器。
    
   - 你选择的**发布**规则或选项将为**单个网站或负载平衡器**。
    
   - 这必须为**用于连接发布的 Web 服务器或场的不安全连接**。
    
   - 您将需要为**内部发布**，发布路径并为前端池的负载平衡器的**VIP 地址**输入的 FQDN，一个例子就是 sfb_pool01.contoso.local。
    
   - 您应该键入**/**为路径，才能发布，但您还需要**转发原始主机头**。
    
   - 有一个**公共或外部名称**详细信息或信息的选项。你可在其中输入以下内容：
    
   - **接受请求**，但应为域名。
    
   - 对于**名称**，你应输入 **lyncdiscover.** <sipdomain>（这是外部的自动发现服务 URL）。
    
   - 将**路径**选项，您将需要输入**/**在此处。
    
   - 您需要选择一个 web 侦听器，或允许反向代理为您创建一个。
    
   - **身份验证委派**应设置为**无委派**，但直接客户端身份验证**不应**被允许。
    
   - 规则应设置为**所有用户**。
    
   - 这应是创建此规则所需的所有信息，并且允许你继续操作。
    
4. 需要设置 **Web 服务器**端口，为此，你需要执行以下操作：
    
   - **将请求重定向到 HTTP 端口**，端口号应为 **8080**。
    
   - **将请求重定向到 SSL 端口**，端口号应为 **4443**。
    
5. 一切均配置好后，你需要对其进行保存或应用，然后你将需要测试该规则。
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>使用混合部署配置移动性的自动发现
<a name="ConfigAutoD"> </a>

混合环境中的业务服务器 2015 Skype 是组合内部部署的环境和 O365 的环境。 如果在混合环境中工作的业务服务器有 Skype，自动发现服务需要能够找到从这些环境中的用户。
  
要让移动客户端发现用户所在位置，需要使用新的统一资源定位器 (URL) 配置自动发现服务。步骤包括：
  
1. 企业服务器管理外壳程序打开 Skype。
    
2. 运行以下操作以获取为您的企业服务器环境的 Skype 的**ProxyFQDN**属性的值：
    
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

一旦您已经部署 Skype 业务服务器移动服务和 Skype 业务服务器自动发现服务，您需要运行一个测试交易记录，以确保您的部署工作均正确。 你可以运行 **Test-CsUcwaConference** 来测试两个用户能否创建和加入会议以及在会议中通信。 你需要两个用户（实际或测试）及其完整凭据来执行此测试。 此命令适用于这两种 Skype 业务客户端以及 Lync Server 2013 客户端。
  
Lync Server 2010 中的客户端，您需要运行**测试 CsMcxP2PIM**进行测试。 Lync Server 2010 用户仍必须是实际用户或预定义的测试用户，而您需要其密码凭据。
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>测试 Skype for Business 和 Lync 2013 移动客户端的会议功能

1. **企业服务器管理外壳的 Skype**和**Ocscore**的安装位置的任何计算机上**CsAdministrator**角色的成员身份登录。
    
2. 启动**业务服务器管理外壳的 Skype** （您可能在搜索中键入的名称或者转到**所有程序**，然后选择它）。
    
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

1. **企业服务器管理外壳的 Skype**和**Ocscore**的安装位置的任何计算机上**CsAdministrator**角色的成员身份登录。
    
2. 启动**业务服务器管理外壳的 Skype** （您可能在搜索中键入的名称或者转到**所有程序**，然后选择它）。
    
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

若要查看命令过程进一步，您可以签出[测试 CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)和[测试 CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。
  
## <a name="configure-for-push-notifications"></a>配置推送通知
<a name="ConfigPush"> </a>

即使 Skype 或 Lync 应用处于非活动状态，也可以向移动设备发送推送通知（以徽章、图标或警告的形式）。 但什么是推送通知？ 它们是事件警报，如新的或错过的 IM 邀请，或收到的语音邮件。 为业务服务器推送通知服务，该服务然后将通知发送到 Microsoft 推送通知服务 (MSNS) 为 Windows Phone 用户，业务服务器 2015年移动服务 Skype 将这些通知发送到基于云的 Skype。
  
此功能不会改变从 Lync Server 2013，但如果 Skype 业务服务器，您需要执行下列操作：
  
- 为 Skype 业务服务器 2015年边缘服务器，添加新的宿主提供商，Microsoft Skype 的在线业务，然后设置托管提供商联盟组织和 Skype 之间的在线业务。
    
- 通过运行 **Set-CsPushNotificationConfiguration** cmdlet 启用推送通知。默认情况下，推送通知已关闭。
    
- 测试你的联盟配置和推送通知。
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>针对推送通知配置你的 Skype for Business 边缘服务器

1. 在以是为计算机安装了**业务服务器管理外壳的 Skype**和**Ocscore** **CsAdministrator**角色的成员的帐户登录。
    
2. 启动**业务服务器管理外壳的 Skype**。
    
3. 添加业务服务器在线托管提供商 Skype。
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   例如：
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 你不能与一个宿主提供程序建立多个联盟关系。因此，如果你已设置一个与 sipfed.online.lync.com 建立了联盟关系的宿主提供程序，请不要为其添加其他宿主提供程序，即使该宿主提供程序的标识不是 SkypeOnline 也是如此。 
  
4. 设置托管提供商之间的联盟组织与 Skype 的推送通知服务的在线业务。 在命令行中，你需要键入：
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>启用推送通知

1. 在以是为计算机安装了**业务服务器管理外壳的 Skype**和**Ocscore** **CsAdministrator**角色的成员的帐户登录。
    
2. 启动**业务服务器管理外壳的 Skype**。
    
3. 启用推送通知：
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. 启用联盟：
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>测试联盟和推送通知

1. 在以是为计算机安装了**业务服务器管理外壳的 Skype**和**Ocscore** **CsAdministrator**角色的成员的帐户登录。
    
2. 启动**业务服务器管理外壳的 Skype**。
    
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

您可以使用 Skype 的业务服务器 2015 来确定哪些用户可以使用您的移动服务，调用通过工作，语音通信 (VoIP)，IP 或视频，以及 WiFi 是 VoIP 或视频需要。 使用通过工号拨号功能，移动用户可以在发出和接收呼叫时使用其工作电话号码，而不是其移动电话号码。 该线路另一端上的人员不会看到移动用户的移动电话号码，并且可以让移动用户避免产生拨出呼叫费用。 设置 VoIP 和视频后，用户可以接收和发出 VoIP 呼叫和视频。 WiFi 用法的设置确定通过蜂窝数据网络使用 WiFi 网络是否需要用户的移动设备。
  
移动性、 工作，通过电话和 VoIP 和视频功能是默认启用的。 禁用了 VoIp 和视频需要 WiFi 的设置。 管理员可以全局、按网站或按用户对其进行更改。
  
若要能够使用移动功能并调用通过工作，用户必须是：
  
- 启用对 Skype 业务服务器 2015
    
- 启用企业语音。
    
- 分配具有**EnableMobility**选项设置为**True**的移动策略。
    
对于希望能使用通过工号拨号功能的用户，他们还必须：
  
- 分配已选择**允许多部电话同时响铃**选项的语音策略。
    
- 分配具有**EnableOutsideVoice**设置为**True**的移动策略。
    
> [!NOTE]
> 未启用企业语音的用户可以使用其移动设备发出 Skype 至 Skype VoIP 呼叫，也可以使用“单击以加入”链接来通过移动设备加入会议（如果已为与其关联的语音策略设置相应的选项）。规划主题中有更多详细信息。 
  
### <a name="modify-global-mobility-policy"></a>修改全局移动策略

1. 在以是为计算机安装了**业务服务器管理外壳的 Skype**和**Ocscore** **CsAdministrator**角色的成员的帐户登录。
    
2. 启动**业务服务器管理外壳的 Skype**。
    
3. 请关闭移动性和呼叫通过工作访问全局通过键入：
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > 关闭移动访问关闭的情况下，可以关闭工作通过调用。 但是，您不能关闭移动还关闭工作通过调用关闭的情况下。 
  
    有关更多信息，敬请[组 CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-site"></a>修改网站的移动策略

1. 在以是为计算机安装了**业务服务器管理外壳的 Skype**和**Ocscore** **CsAdministrator**角色的成员的帐户登录。
    
2. 启动**业务服务器管理外壳的 Skype**。
    
3. 你可以创建站点级别的策略、禁用 VoIP 和视频，以及按网站启用“IP 音频需要 WiFi”和“IP 视频需要 WiFi”。键入：
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    了解更多信息，请访问[新建 CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-user"></a>修改用户的移动策略

1. 在以是为计算机安装了**业务服务器管理外壳的 Skype**和**Ocscore** **CsAdministrator**角色的成员的帐户登录。
    
2. 启动**业务服务器管理外壳的 Skype**。
    
3. 创建用户级别移动策略并关闭移动性和呼叫通过用户的工作。 键入：
    
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
    > 关闭移动访问关闭的情况下，可以关闭工作通过调用。 但是，您不能关闭移动还关闭工作通过调用关闭的情况下。 
  

