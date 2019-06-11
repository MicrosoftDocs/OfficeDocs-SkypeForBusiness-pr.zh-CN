---
title: 常见问题：为 Lync Server 设置 Skype 连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc06cda300945ccf4d7da9424b5615028c2e8f5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>常见问题：为 Lync Server 2013 设置 Skype 连接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2019-03-22_

从2019年4月起, 我们将停止通过 pic.lync.com 网站为 Skype Federation 预配的客户的联系人信息的收集和保留。 进行此更改是为了确保 pic.lync.com 预配系统遵守 Microsoft 隐私策略。 
 
此更改生效后, 我们将不再能够在挂起的预配更改上提供电子邮件更新。 PIC 预配更改通常在输入后的24-48 小时内完成。 如果你在提交预配请求后48小时仍遇到 Skype 联合身份验证问题, 请与 Microsoft 技术支持人员联系以进一步调查。

> [!IMPORTANT]
> 作为此更改的一部分, 所有以前输入的联系人信息将在2019年4月结束后从系统中清除。


**问: Microsoft Lync 和 Skype 支持哪些功能？**

**A:** Skype 现已成为 Microsoft 家庭的一部分, 新的新可能性可用于将统一通信方案扩展到数百个使用 Skype 的用户。 此组合将使 Lync 客户能够与供应商、客户和合作伙伴进行连接和协作, 依赖于 Lync 的丰富程度和 Skype 的范围。

  - 即时消息、音频和视频通话—— Lync 和 Skype 用户之间的联合音频和视频通话和即时消息

  - 联机状态共享-联盟联系人之间的 Exchange 状态信息

  - 简单的管理-根据组织的策略和标准配置联盟通信的设置和控件

**问: 如何有资格将 Lync 部署与 Skype 连接？**

**A:** 如果您有以下两种情况, 您将获得 Skype 连接许可:

  - Lync Server (2010 或 2013) + Lync Server 标准客户端访问许可证 ("Cal"; 2010 或 2013), 用于组织中将连接到 Skype 的用户和/或设备。 

  - Lync Online (作为独立许可证或 Office 365 套件的一部分)。但是, 此服务 (pic.lync.com) 仅用于设置 Lync Server 和混合 Lync 服务器以及 Lync Online 部署。在 Lync Online "控制面板" (LOCP) 中完成 lync Online PIC 预配。

**问: 什么人必须 Lync 最终用户才能连接到 Skype 联系人？**

**A:** 激活域并由组织的 Lync 管理员启用功能后, Lync 用户可以将 Skype 联系人添加到其在 Lync 客户端中的联系人列表。

**问: Skype 最终用户必须执行哪些操作才能连接到 Lync 联系人？**

**A:** 希望连接到 Lync 用户的所有 Skype 用户都必须拥有与他们的 Skype Id 相关联的 Microsoft 帐户, 并使用 Microsoft 帐户登录。这可以在 Skype 客户端中启用。

**问: 与 Windows Live 的联盟是否仍然可用？**

**A:** 从2012年10月开始, Microsoft 已开始帮助 Windows Live Messenger (WLM) 用户转到 Skype, 发送到 Skype, 以最终注销 WLM。只要 WLM 位于市场, Lync 将继续支持与 WLM 的联合身份验证, 但不允许其他任何 Windows Live 域激活。WLM 用户的移动由 Skype 6.0 for Mac 和 Windows 启用 (年10月 25 2012 日发布), 从而允许使用 Microsoft 帐户 (即与 WLM 相同的凭据) 登录。 只要登录到 Skype, WLM 好友列表就会自动填充到 Skype, 用户可以利用 Skype 的扩展通信功能, 如拨打座机和手机、屏幕共享、群组视频通话以及支持宽屏各种设备。此外, WLM 用户的联合 Lync 联系人关注的是通过联系人列表的其余部分切换到 Skype, 并且 Skype 和 Lync 之间的 IM 将立即可用。 Lync 客户无需执行任何操作即可启用此服务连续性。

**问: 是否有 Yahoo\!或 AOL 的联盟仍然可用？**

**A:** 不。 与 Yahoo 的联盟\! 和 AOL 的支持来自 Yahoo\! 和 AOL。对于这两个 Yahoo\! 并且 AOL 的服务在2014年6月30日结束。 

**问: 在购买 Lync 之前, 我是否可以试用 Skype 连接？**

**A:** 不会在试用版中提供 Skype 连接。 为了代替试用版, 鼓励具有符合条件的许可证的 Lync 客户只需注册服务即可进行测试。

**问: 预配需要哪些信息？**

**A:** 若要在合格的许可证下提交预配请求, 您需要具备以下条件:

  - Microsoft 协议号码:
    
      - Microsoft 批量许可支持: Microsoft 批量许可协议编号
    
      - Microsoft 合作伙伴网络: Headquarter 合作伙伴 ID
    
      - 服务提供商许可协议: 初始注册号码
    
      - 高容量服务: 产品注册号

  - 访问边缘服务的完全限定的域名 (Fqdn)。
    
      - 至少需要一个访问边缘服务的 FQDN。
    
      - 如果你的组织有多台服务器运行 "访问边缘" 服务, 请为每个额外的访问边缘服务指定 Fqdn。 重要提示: 如果你以前为访问边缘服务指定了 FQDN, 并且想要对其进行更改, 则为更改设置可能需要几天才能完成, 并且可能会导致服务中断。 为了防止服务中断, 我们建议你保留以前指定的访问边缘服务的 FQDN。

  - 会话初始协议 (SIP) 域。 这是用户当前用于即时消息的 SIP URI 的域后缀。 如果您的组织有多个 SIP 域, 请为用于即时消息的每个域指定域后缀。 例如, 对于 user1@contoso.com, 为 SIP 域指定 contoso.com;对于 user1@example.fabrikam.com, 将 example.fabrikam.com 指定为 SIP 域。
    
    <div>
    

    > [!NOTE]
    > 仅为 SIP 域指定域后缀。 不要为 SIP 域指定任何 Fqdn, 包括访问边缘服务的 FQDN。

    
    </div>

  - 联系信息。 为你指定的每个 SIP 域的管理员指定一个电子邮件地址。

**问: 如何在拆分域方案中启用 Lync-Skype 连接？**

**A:** 如果您有 Lync Online 2013 和 Lync Server 本地拆分域方案 (使用同一 SIP 域的在线和内部部署用户), 请按以下顺序执行以下两个步骤, 启用 Lync-Skype 连接

1.  按照 PIC 预配指南中的说明设置本地 Lync-Skype 连接。

2.  等待, 直到看到您的域已由 Microsoft 设置的确认。

3.  在您看到确认后, 请使用 Lync 管理中心打开 "外部通信"。 有关详细信息, 请参阅[http://office.microsoft.com/en-us/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/en-us/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

此顺序非常重要。在 Lync Online 中启用通信之前, 必须设置本地连接。 如果反转了顺序, 则输入的内部部署信息<https://pic.lync.com>将不会继续。 如果你已为与此域的外部通信设置 Lync Online, 则必须将其关闭, 等待24小时, 然后重新开始, 首先在<https://pic.lync.com>中输入本地信息, 然后启用 Lync Online 的外部通信。

**问: 是否可以为 Skype 连接设置多个访问边缘服务 Fqdn？**

**A:** 您只能为一个或多个域设置一个访问边缘 FQDN。 你可以设置多个访问边缘 Fqdn (每个请求最多10个) (如果它们具有不同的域)。

**问: 我是否可以获取针对组织请求预配所找到的 Microsoft 帐户电子邮件地址列表？**

**A:** 不。 这些地址被视为个人身份信息, 不会被共享。

**问: 如何添加 ID 包含 Windows Live 不支持的域的 Windows Live Messenger 联系人？**

**A:** 如果你要使用具有非 Windows Live 域的帐户或 ID 添加 Windows Live Messenger 用户, 请按以下格式输入地址\<: 用户名\>(\<域名\>) @msn .com, 其中\<的域名是\>用户电子邮件地址中的域名。 例如, 如果你想要添加 ted@contoso.com, 你可以使用以下格式: 李小明 (contoso) @msn .com。 有关由 Windows Live 管理的域的列表, 请参阅 "受支持的域" 部分 (在 "安装实时通信服务器服务包1的公共即时消息后出现的已知问题http://support.microsoft.com/?kbid=897567)" 部分中。

**问: 预配过程需要多长时间？**

**A:** 预配最多可能需要30天。

**问: 设置完成后如何知道？**

**A:** 设置完成后, Microsoft 将发送电子邮件通知。

**问: 如何更新我提交的配置或联系人详细信息？**

**A:** 完成预配后, 您可以在用于请求预配的同一网站上更新您的信息。 输入协议号码, 然后单击 "更新服务"。

</div>

<span> </span>

</div>

</div>

</div>

