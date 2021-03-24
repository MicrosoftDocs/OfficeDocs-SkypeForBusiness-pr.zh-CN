---
title: 部署和配置 Skype for Business Server 的移动功能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文将介绍配置现有 Skype for Business Server 安装以使用 Mobility Service 的步骤，以便你的移动设备能够利用 Skype for Business Server Mobility 功能。
ms.openlocfilehash: 2ba0a81350dac6e47f4e909b4cfba256ee90de18
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103858"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>部署和配置 Skype for Business Server 的移动功能  
 
本文将介绍配置现有 Skype for Business Server 安装以使用 Mobility Service 的步骤，以便你的移动设备能够利用 Skype for Business Server Mobility 功能。
  
查看 Plan [for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) 一文后，您应该已准备好继续执行以下步骤，将 Mobility 部署到 Skype for Business Server 环境中。 步骤如下， (在此表中包括权限列表) ：
  
|**阶段**|**权限**|
|:-----|:-----|
|[创建 DNS 记录](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[修改证书](deploy-and-configure-mobility.md#ModCerts) <br/> |本地管理员  <br/> |
|[配置反向代理](deploy-and-configure-mobility.md#ConfigRP) <br/> |本地管理员  <br/> |
|[使用混合部署配置移动性自动发现](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[测试移动部署](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[配置推送通知](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[配置移动策略](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
以下所有部分都包含假定你已阅读规划主题的步骤。 如果有任何令人困惑的事情，请随时查看相关信息。

> [!NOTE]
> Skype for Business Server 2019 (MCX) Mobility Service 不再提供对旧版移动客户端的支持。 所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
## <a name="create-dns-records"></a>创建 DNS 记录
<a name="CreateDNSRec"> </a>

你可能已经拥有这些记录作为 Skype for Business Server 环境的一部分，但你需要创建以下记录，自动发现功能可以正常工作：
  
- 内部 DNS 记录，用于支持从组织网络内部进行连接的移动用户。
    
- 外部 (或公共) DNS 记录，以支持从组织网络外部进行连接的移动用户。
    
这些记录可以是 a (host) names 或 CNAME records (you don't have to make both， we're just including the steps for everything here) .
  
### <a name="create-an-internal-dns-cname-record"></a>创建内部 DNS CNAME 记录

1. 在作为 **Domain Admins** 组或 **DnsAdmins** 组的成员的网络中登录到 DNS 服务器。
    
2. Click **Start**， Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu) ， and then click **DNS** to open the DNS administrative snap-in.
    
3. 在控制台窗口的左侧窗格中，你需要转到 Skype for Business Server 前端服务器所位于的域，然后在那里展开"前向 **查找** 区域"。
    
4. 花一点时间查看你拥有以下哪项：
    
   - 前端服务器或 Standard (Enterprise) 或前端池的任何主机 A 或 AAAA (记录) 。
    
   - 控制器或控制器池的任何主机 A 或 AAAA 记录 (部署策略中可能具有的可选) 。
    
5. 记录此名称后，右键单击 SIP 域名，然后从菜单中选择 **"CNAME (") "** 新别名"。
    
6. 在 **"别名"** 文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。
    
7. 在目标主机的完全限定域名 **(FQDN** 中，需要键入或浏览到前端池 (或单个前端服务器、控制器池或控制器) 的内部 Web 服务 FQDN，如上面的步骤 4 所示。 输入时单击"确定"。
    
8. 你需要在 Skype for Business Server 环境中支持的每个 SIP 域的向前查找区域中创建新的自动发现 CNAME 记录。
    
### <a name="create-an-external-dns-cname-record"></a>创建外部 DNS CNAME 记录

1. 这些步骤是通用的，因为我们无法告诉你可能使用哪种公共 DNS 提供商，但仍希望帮助您解决。请使用能够在那里新建 DNS 记录的帐户登录到公共 DNS 提供商。
    
2. 此时，Skype for Business Server 的 SIP 域应该已存在。 展开此 SIP **域的** "前向查找区域"，或者以其他方式打开它。
    
3. 花一点时间查看你拥有以下哪项：
    
   - 前端服务器或 Standard (Enterprise) 或前端池的任何主机 A 或 AAAA (记录) 。
    
   - 控制器或控制器池的任何主机 A 或 AAAA 记录 (部署策略中可能具有的可选) 。
    
4. 获得该信息后，应该能够选择一个选项，以使用 **CNAME (创建新别名) 。**
    
5. 现在您应该能够输入别名，您需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。
    
6. 接下来，应该有一个要输入目标主机 **的 FQDN** 的区域，这应该是前端池 (或单台前端服务器的 FQDN，或上面步骤 3 中标识的控制器池或控制器) 。
    
7. 你可能需要在此处保存，或者如果你需要在 Skype for Business Server 环境中每个 SIP 域的向前查找区域中创建其他 CNAME 记录，你应这样做，但一旦准备就绪，请保存你的工作。
    
### <a name="create-an-internal-dns-a-record"></a>创建内部 DNS A 记录

1. 在作为 **Domain Admins** 组或 **DnsAdmins** 组的成员的网络中登录到 DNS 服务器。
    
2. Click **Start**， Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu) ， and then click **DNS** to open the DNS administrative snap-in.
    
3. 在控制台窗口的左侧窗格中，你需要转到 Skype for Business Server 前端服务器所位于的域，然后在那里展开"前向 **查找** 区域"。
    
4. 花一点时间查看你拥有以下哪项：
    
   - 前端服务器或 Standard (Enterprise) 或前端池的任何主机 A 或 AAAA (记录) 。
    
   - 控制器或控制器池的任何主机 A 或 AAAA 记录 (部署策略中可能具有的可选) 。
    
5. 记录此名称后，右键单击 SIP 域名，然后从菜单中选择"新建主机 (A 或 **AAAA**) 选择" 新建主机"。
    
6. 在" **名称** "文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。
    
7. 在 **"IP** 地址"文本框中，键入前端池或单个前端服务器 (或控制器池或控制器) 的内部 Web 服务 IP 地址，如上面的步骤 4 所示。
    
8. 完成此操作后，单击 **"添加主机**"，然后单击"确定 **"。**
    
9. 你需要在 Skype for Business Server 环境中支持的每个 SIP 域的向前查找区域中创建新的自动发现 A 或 AAAA 记录。 为此，请根据需要多次重复步骤 6-8。
    
10. 完成后，单击 **完成。**
    
### <a name="create-an-external-dns-a-record"></a>创建外部 DNS A 记录

1. 这些步骤是通用的，因为我们无法告诉你可能使用哪种公共 DNS 提供商，但仍希望帮助您解决。请使用能够在那里新建 DNS 记录的帐户登录到公共 DNS 提供商。
    
2. 此时，Skype for Business Server 的 SIP 域应该已存在。 展开此 SIP **域的** "前向查找区域"，或者以其他方式打开它。
    
3. 花一点时间查看你拥有以下哪项：
    
   - 前端服务器或 Standard (Enterprise) 或前端池的任何主机 A 或 AAAA (记录) 。
    
   - 控制器或控制器池的任何主机 A 或 AAAA 记录 (部署策略中可能具有的可选) 。
    
4. 获得该信息后，应该能够选择一个选项来创建新 **主机 A 或 AAAA。**
    
5. 现在，您应该能够输入 **Name，** 您需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。
    
6. 接下来，应该有一个要输入 IP 地址的区域，这应该是前端池 (或单个前端服务器的 **IP、** 控制器池或控制器) ，如上面的步骤 3 所示。
    
7. 你可能需要在此处保存，或者如果你需要在 Skype for Business Server 环境的每个 SIP 域的向前查找区域中创建其他 A 或 AAAA 记录，你应这样做，但一旦准备就绪，请保存你的工作。
    
## <a name="modify-certificates"></a>修改证书
<a name="ModCerts"> </a>

如果你对规划证书有疑问，我们已在 Plan [for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) 一文记录了这一点。 查看后，我们将演练以下内容：
  
- 是否需要新证书？
    
- 从 CA 证书颁发机构请求 (证书) 。
    
- 使用 PowerShell 使用替换项更新就地证书。
    
- 使用 Microsoft 管理控制台中的"证书"管理单元检查 (MMC) 。
    
### <a name="do-i-need-new-certificates"></a>是否需要新证书？

1. 首先，你可能需要检查并查看哪些证书已就位，以及它们是否有所需的条目。 为此，你需要使用本地管理员帐户登录 Skype for Business Server。 此帐户可能还需要对 CA 证书颁发机构 (，) 执行其中一些步骤。
    
2. 打开 Skype for Business Server 命令行管理程序 (如果你未将 Skype for Business Server 命令行管理程序固定到"开始"菜单或任务栏菜单，可以使用搜索) 。
    
3. 在尝试添加更新的证书之前，了解已分配哪些证书至关重要。 因此，在命令中键入：
    
   ```powershell
   Get-CsCertificate
   ```

4. 步骤 3 中的信息将是唯一的。 你需要查看它以确定你是否拥有一个已分配用于多个项的证书，或者您是否为需要它们的不同组件分配了不同的证书。 **Use** 参数将告知您证书的使用方式 **，Thumbprint** 参数将告知您证书是全部相同的证书还是多个证书。
    
5. 如果您的规划部分中推荐了 SAN 条目，则没有问题。 如果没有，则需要请求新证书或多个证书 (证书颁发机构) 配置。
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>从 CA 证书颁发机构请求新证书 (证书) 

1. 检查了具有哪些 SAN 条目后，通过上述 **)** 步骤检查后，即知道您拥有单个证书 (，并且你知道您没有所需的全部条目。 需要向 CA 提出新的证书请求。 打开 Skype for Business Server PowerShell：
    
   - 对于缺少的自动发现服务 SAN (将 -Ca 参数替换为你自己的证书颁发机构路径) ：
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 现在，如果您有多个 SIP 域，则不能像上面的示例一样使用 AllSipDomain 参数。 您需要改为使用 DomainName 参数。 使用 DomainName 参数时，必须定义 lyncdiscoverinternal 和 lyncdiscover 记录的 FQDN。 例如， (-Ca 参数替换为您自己的证书颁发机构路径) ：
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. 或者，在查看你拥有哪些 SAN 条目后，发现你拥有多个证书，这些证书没有所需的全部条目。 需要向 CA 提出新的证书请求。 打开 Skype for Business Server PowerShell：
    
   - 对于缺少的自动发现服务 SAN (将 -Ca 参数替换为你自己的证书颁发机构路径) ：
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 现在，如果您有多个 SIP 域，则不能像上面的示例一样使用 AllSipDomain 参数。 您需要改为使用 DomainName 参数。 使用 DomainName 参数时，必须定义 lyncdiscoverinternal 和 lyncdiscover 记录的 FQDN。 示例包括 (-Ca 参数替换为您自己的证书颁发机构路径) ：
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - CA 生成新证书后，你将需要分配它们。
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序分配证书

- 根据你在上面的是否需要新的认证部分中找到的内容，你需要运行 **以下操作** 之一。
    
  - 如果有一个证书用于所有 (指纹完全相同) 则需要运行以下代码：
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 如果你有不同的证书，但指纹 (都是不同的) ，请改为运行以下代码：
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>在 MICROSOFT 管理控制台中查看 (MMC) 

1. 可以选择使用 MMC 的"证书"管理单元查看证书。 只需在搜索中键入 MMC，它应作为应用程序选项弹出。
    
2. 若要添加证书管理单元，你需要单击文件，然后添加/删除管理单元 **...** (或键盘快捷方式 **Ctrl+M** 也将) 。 **证书** 将是左侧窗格中的一个选项，选择它，然后在弹出窗口中，然后选择下一步的计算机 **帐户**。
    
3. 仍在弹出窗口中，你很可能正在位于需要查看的证书的主页上执行此操作，因此，如果位于本地计算机上，请保留选择。  如果正在远程计算机上工作，将单选按钮更改为"其他计算机"，然后输入该计算机的 FQDN 或使用"浏览"按钮通过AD 搜索该计算机。  选择计算机后，你需要在准备就绪时单击"完成"，然后单击"确定"以将管理单元添加到 MMC。
    
4. 展开MMC 左侧窗格中的"证书"部分。 同时展开 **"个人**"文件夹，然后选择"证书 **"。** 这使你可以在此存储中查看证书。
    
5. 您需要找到要查看的证书，右键单击它，然后选择"打开 **"。**
    
    > [!NOTE]
    > 您如何知道这是一个证书？ 它应是分配给服务器场中所有内容的单一证书，或者您可能具有用于不同内容的多个证书，如 Default、Internal Web Services 等，在这种情况下，您可能需要查看多个证书。 多个证书将具有相同的指纹。 
  
6. 进入证书视图后 **，选择详细信息****。** 这将在选择"主题"时看到证书主题名称，并且将显示分配的主题名称和关联属性。
    
7. 你还需要检查主题备用 **名称** 条目。 你将找到以下一个或多个内容：
    
   - 此池的池名称，或单个服务器名称（如果不是池）。
    
   - 证书分配到的服务器名称。
    
   - 简单 URL 记录，通常为 meet 和 dialin。
    
   - Web 服务内部名称和 Web 服务外部名称 (，例如，webpool01.contoso.net、webpool01.contoso.com) ，这些名称基于在拓扑生成器和覆盖的 Web 服务选择中做出的选择。
    
   - 如果已分配，则 lyncdiscover。\<sipdomain\> 和 lyncdiscoverinternal。\<sipdomain\> 记录。
    
     如果分配了多个证书，则需要检查多个证书 (检查上述) 。
    
8. 因此，如果您找到 lyncdiscover。\<sipdomain\> 和 lyncdiscoverinternal。\<sipdomain\> 记录，你已对此进行配置。 你可以关闭 MMC。
    
9. 如果未分配证书，你将需要提出上述 (列出的新证书请求) 或者需要安装它们请求后 (我们建议针对该证书的 powerShell 进行以下) 。
    
## <a name="configure-the-reverse-proxy"></a>配置反向代理
<a name="ConfigRP"> </a>

不应完全遵循以下步骤。 这是因为在该产品的以前版本中，我们已演示了配置威胁管理网关 (TMG) 例如，如果未使用该配置，则需要从该版本创建自己的版本。
  
TMG 不再由 Microsoft 作为产品提供，如果您仍然需要对其进行配置，您可以查看 [Lync Server 2013 步骤](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility)。 但是，以下信息更普遍有用，即使我们无法为上述每个反向代理提供特定的演练步骤。
  
我们需要考虑两个主要问题：
  
- 是否打算通过 HTTPS 服务器执行初始自动发现 (建议) ？
    
  - 如果你有 Web 发布规则，则需要对其进行修改。
    
  - 如果还没有 Web 发布规则，则需要创建它。
    
- 如果通过 HTTP 执行初始自动发现请求，则还需要创建或修改该规则。
    
> [!NOTE]
> **重要** 代理的退出值是因部署而异的数值。 您应监视部署并修改值，以获得最佳客户端体验。 你可以将该值设置为低至 200。 如果要在环境中支持 Lync 移动客户端，则应该将值设置为 960，以允许从 Office 365 发送推送通知的退出时间，其退出值为 900。 很可能您必须增加退出值以避免在值太低时客户端断开连接，或者，如果通过代理的连接没有断开连接但在客户端断开连接后清除，则减少此数目。 监视和确定环境常规情况是确定此值的适当设置的唯一准确方法。
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>修改外部自动发现 SAN 和 URL 的现有 Web 发布规则

1. 打开反向代理接口。
    
2. 你需要找到 Web 发布规则，并选择"编辑"选项 (它可能位于菜单或选项卡上，具体取决于反向代理配置) 。
    
3. 应存在一个指出此 Web 发布规则所应用到的内容的区域。 您需要修改传入网站或网站请求的此规则。 你将添加新条目。 
    
4. 键入自动发现站点的名称 (我们将使用的示例是 lyncdiscover.contoso.com) ，并单击"确定"或"保存"，具体取决于反向代理的格式。 
    
5. 你可能有一个新证书，该证书中具有自动发现 SAN 条目。 这也需要进行安装，并配置为根据反向代理的设置使用。 确保在配置完成后保存所有内容。
    
6. 如果反向代理具有 **测试** 功能，请使用它，以确保一切正常。
    
7. 现在，如果您的环境中具有控制器或控制器池，您可能需要重复这些步骤 (这意味着您具有第二个规则) 。
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>为外部自动发现 URL 创建 Web 发布规则

1. 打开反向代理接口。
    
2. 你需要在界面中查找创建 Web 发布规则的位置，并选择"新建"或"创建"选项 (它可能位于菜单或选项卡上，具体取决于反向代理配置) 。 您正在寻找创建新 Web 发布规则的选项。
    
3. 通常，您需要输入以下信息：
    
   - **名称**：规则的名称
    
   - **规则** 操作：在这种情况下， **它是允许规则** ，你可以让某些内容通过反向代理。
    
   - 您 **选择的** 发布规则或选项将是单个 **网站或负载平衡器**。
    
   - 这应该是用于外部访问 **的 SSL，** 请选择该选项。
    
   - 您需要发布内部发布的路径，并输入前端池负载平衡器 (上的外部 Web 服务的 FQDN 或控制器池负载平衡器（如果有一个) ）的 FQDN，例如 sfb_pool01.contoso.local。
    
   - 应键入 _ 作为要发布的路径，但还需要 **/\\** _*转发原始主机头**。
    
   - 有一个公共或外部 **名称详细信息** 或信息的选项。 这是你可以输入的位置：
    
   - **接受请求**，但它应该用于域名。
    
   - 对于 **"名称**"，应输入 **lyncdiscover。** <sipdomain> (这是外部自动发现服务 URL) 。 现在，如果要为前端池上的外部 Web 服务 URL 创建规则，则需要为前端池上的外部 Web 服务键入 FQDN (例如，lyncwebextpool01.contoso.com) 。
    
   - 有一个 **Path** 选项，你需要在此处输入 **/\\** *。
    
   - 您需要使用最新的公共证书选择 **SSL** 侦听器。
    
   - **身份验证委派** 应设置为" **无委派"，** 但 **应允许直接客户端** 身份验证。
    
   - 该规则应设置为 **所有用户**。
    
   - 这应该是创建此规则所需的全部信息，并允许您继续操作。
    
4. 你将需要确保转发原始 **主机** 头。
    
5. **还需要设置 Web** 服务器端口，您需要执行以下操作：
    
   - **将请求重定向到 HTTP 端口**，端口号应为 **8080。**
    
   - **将请求重定向到 SSL 端口** ，端口号应为 **4443**。
    
6. 配置所有内容后，需要保存或应用它们，然后测试规则。
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>为端口 80 创建 Web 发布规则 (可选) 

1. 打开反向代理接口。
    
2. 你需要在界面中查找创建 Web 发布规则的位置，并选择"新建"或"创建"选项 (它可能位于菜单或选项卡上，具体取决于反向代理配置) 。 您正在寻找创建新 Web 发布规则的选项。
    
3. 通常，您需要输入以下信息：
    
   - **名称**：规则的名称
    
   - **规则** 操作：在这种情况下， **它是允许规则** ，你可以让某些内容通过反向代理。
    
   - 您 **选择的** 发布规则或选项将是单个 **网站或负载平衡器**。
    
   - 这应该是一 **个非安全连接，用于连接到已发布的 Web 服务器或服务器场**。
    
   - 您需要发布内部发布的路径，并输入前端池负载平衡器 VIP 地址的 FQDN，例如 sfb_pool01.contoso.local。 
    
   - 应键入 _ 作为要发布的路径，但还需要 **/\\** _*转发原始主机头**。
    
   - 有一个公共或外部 **名称详细信息** 或信息的选项。 这是你可以输入的位置：
    
   - **接受请求**，但它应该用于域名。
    
   - 对于 **"名称**"，应输入 **lyncdiscover。** <sipdomain> (这是外部自动发现服务 URL) 。
    
   - 有一个 **Path** 选项，你需要在此处输入 **/\\** *。
    
   - 你需要选择一个 Web 侦听器，或允许反向代理创建一个。
    
   - **身份验证委派** 应设置为" **无委派"，** 但 **不允许直接客户端** 身份验证。
    
   - 该规则应设置为 **所有用户**。
    
   - 这应该是创建此规则所需的全部信息，并允许您继续操作。
    
4. **需要设置 Web** 服务器端口，需要执行以下操作：
    
   - **将请求重定向到 HTTP 端口**，端口号应为 **8080。**
    
   - **将请求重定向到 SSL 端口** ，端口号应为 **4443**。
    
5. 配置所有内容后，需要保存或应用它们，然后测试规则。
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>使用混合部署配置移动性自动发现
<a name="ConfigAutoD"> </a>

Skype for Business Server 中的混合环境是组合本地和 O365 环境的环境。 当你让 Skype for Business Server 在混合环境中工作时，自动发现服务需要能够从其中任一环境中查找用户。
  
若要让移动客户端发现用户所在的位置，需要将自动发现服务配置为使用新的统一资源定位器 (URL) 。 步骤如下：
  
1. 打开 Skype for Business Server 命令行管理程序。
    
2. 运行以下代码，获取 Skype for Business Server 环境的属性 **ProxyFQDN** 的值：
    
   ```powershell
   Get-CsHostingProvider
   ```

3. 然后，仍在 shell 窗口中运行：
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    其中 [identity] 使用共享 SIP 地址空间的域名替换。
    
## <a name="test-your-mobility-deployment"></a>测试移动部署
<a name="TestMobility"> </a>

部署 Skype for Business Server Mobility Service 和 Skype for Business Server 自动发现服务后，你需要运行测试事务，以确保你的部署正常工作。 可以运行 **Test-CsUcwaConference** 来测试两个用户创建、加入会议以及参加会议进行通信的能力。 你需要两个用户 (真实或测试) 及其完整凭据来执行此测试。 此命令适用于 Skype for Business 客户端和 Lync Server 2013 客户端。
  
对于 Skype for Business Server 2015 上的 Lync Server 2010 客户端，你需要运行 **Test-CsMcxP2PIM** 进行测试。 Lync Server 2010 用户仍将是实际用户或预定义的测试用户，并且您需要其密码凭据。

> [!NOTE]
> Skype for Business Server 2019 (MCX) Mobility Service 不再提供对旧版移动客户端的支持。 所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>测试 Skype for Business 和 Lync 2013 移动客户端的会议

1. 以 **CsAdministrator** 角色成员登录到安装了 Skype for **Business Server** 命令行管理程序和 **Ocscore** 的任何计算机上。
    
2. 启动 **Skype for Business Server** 命令行管理程序 (在搜索中键入名称或转到"所有程序"并选择它) 。
    
3. 在命令行中输入：
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   还可以在脚本中设置凭据，然后将它们传递到测试 cmdlet。 我们在下面有一个示例。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>测试 Lync 2010 移动客户端的会议

> [!NOTE]
> Skype for Business Server 2019 (MCX) Mobility Service 不再提供对旧版移动客户端的支持。 所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。

1. 以 **CsAdministrator** 角色成员登录到安装了 Skype for **Business Server** 命令行管理程序和 **Ocscore** 的任何计算机上。
    
2. 启动 **Skype for Business Server** 命令行管理程序 (在搜索中键入名称或转到"所有程序"并选择它) 。
    
3. 在命令行中输入：
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   还可以在脚本中设置凭据，然后将它们传递到测试 cmdlet。 我们在下面有一个示例。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

若要进一步查看命令过程，可以查阅 [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) 和 [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。
  
## <a name="configure-for-push-notifications"></a>配置推送通知
<a name="ConfigPush"> </a>

即使 Skype 或 Lync 应用处于非活动状态，也可以向移动设备发送推送通知（形式为锁屏提醒、图标或警报）。 但是什么是推送通知？ 它们是事件警报，如新的或错过的 IM 邀请，或接收的语音邮件。 Skype for Business Server Mobility Service 会向基于云的 Skype for Business Server 推送通知服务发送这些通知，该服务随后会向 Windows Phone 用户的 Microsoft 推送通知服务 (MSNS) 发送通知。
  
此功能与 Lync Server 2013 不同，但如果你有 Skype for Business Server，你将希望执行以下操作：
  
- 对于 Skype for Business Server 边缘服务器，添加一个新的宿主提供商 Microsoft Skype for Business Online，然后在组织与 Skype for Business Online 之间设置宿主提供商联盟。
    
- 通过运行 **Set-CsPushNotificationConfiguration** cmdlet 启用推送通知。 默认情况下，推送通知已关闭。
    
- 测试联合配置和推送通知。
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>为 Skype for Business 边缘服务器配置推送通知

1. 使用 **CsAdministrator** 角色成员帐户登录到安装了 **Skype for Business Server** 命令行管理程序和 **Ocscore** 的计算机。
    
2. 启动 **Skype for Business Server 命令行管理程序**。
    
3. 添加 Skype for Business Server 联机托管提供商。
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   例如：
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 不能与单个宿主提供商建立多个联盟关系。 因此，如果你已设置与 sipfed.online.lync.com 建立联盟关系的宿主提供商，请不要为它添加其他宿主提供商，即使宿主提供商的标识不是 SkypeOnline。 
  
4. 在 Skype for Business Online 上设置组织与推送通知服务之间的宿主提供商联盟。 在命令行中，你需要键入：
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>启用推送通知

1. 使用 **CsAdministrator** 角色成员帐户登录到安装了 **Skype for Business Server** 命令行管理程序和 **Ocscore** 的计算机。
    
2. 启动 **Skype for Business Server 命令行管理程序**。
    
3. 启用推送通知：
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. 启用联盟：
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>测试联合和推送通知

1. 使用 **CsAdministrator** 角色成员帐户登录到安装了 **Skype for Business Server** 命令行管理程序和 **Ocscore** 的计算机。
    
2. 启动 **Skype for Business Server 命令行管理程序**。
    
3. 测试联盟配置：
    
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

你能够使用 Skype for Business Server 来确定谁可以使用你的移动服务、通过工位呼叫、IP 语音 (VoIP) 或视频，以及 VoIP 或视频是否需要 WiFi。 通过工号呼叫可让移动用户在拨打和接听电话时使用工作电话号码，而不是其移动电话号码。 线路另一端的用户不会看到移动用户的移动电话号码，这样移动用户就不会产生传出呼叫费用。 设置 VoIP 和视频后，用户可以接听并拨打 VoIP 电话和视频。 WiFi 使用情况的设置确定是否需要用户的移动设备才能通过手机数据网络使用 WiFi 网络。
  
默认情况下，移动功能、通过工电话呼叫以及 VoIP 和视频功能全部启用。 禁用 VoIP 和视频需要 WiFi 的设置。 管理员能够全局、按站点或按用户更改此内容。
  
为了能够使用移动功能和通过工位呼叫功能，用户需要：
  
- 为 Skype for Business Server 启用
    
- 启用企业语音。
    
- 分配了将 **EnableMobility** 选项设置为 True 的移动 **策略**。
    
若要使用户能够使用通过工位呼叫功能，他们还需要：
  
- 分配了已选中"启用 **电话同时响铃"选项的** 语音策略。
    
- 分配了 **EnableOutsideVoice** 设置为 True 的移动 **策略**。
    
> [!NOTE]
> 未启用 企业语音 的用户可以使用其移动设备拨打 Skype 到 Skype VoIP 呼叫，或在移动设备上使用"单击加入"链接加入会议（如果为与其关联的语音策略设置了适当的选项）。 规划主题中更详细地介绍。 
  
### <a name="modify-global-mobility-policy"></a>修改全局移动策略

1. 使用 **CsAdministrator** 角色成员帐户登录到安装了 **Skype for Business Server** 命令行管理程序和 **Ocscore** 的计算机。
    
2. 启动 **Skype for Business Server 命令行管理程序**。
    
3. 通过键入：
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > 你可以关闭通过工电话呼叫功能，而无需关闭对移动功能的访问。 但是，如果不同时关闭通过工位呼叫，你无法关闭移动功能。 
  
    有关详细信息，请查看 [Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-site"></a>按站点修改移动策略

1. 使用 **CsAdministrator** 角色成员帐户登录到安装了 **Skype for Business Server** 命令行管理程序和 **Ocscore** 的计算机。
    
2. 启动 **Skype for Business Server 命令行管理程序**。
    
3. 你可以创建站点级别的策略、关闭 VoIP 和视频、按站点启用"IP 音频需要 WiFi"和"IP 视频需要 WiFi"。 类型：
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    有关详细信息，请通过 [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)了解。
    
### <a name="modify-mobility-policy-by-user"></a>按用户修改移动策略

1. 使用 **CsAdministrator** 角色成员帐户登录到安装了 **Skype for Business Server** 命令行管理程序和 **Ocscore** 的计算机。
    
2. 启动 **Skype for Business Server 命令行管理程序**。
    
3. 创建用户级别的移动策略，并按用户关闭移动和通过工位呼叫功能。 类型：
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    示例数据的进一步示例：
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > 你可以关闭通过工电话呼叫功能，而无需关闭对移动功能的访问。 但是，如果不同时关闭通过工位呼叫，你无法关闭移动功能。 
