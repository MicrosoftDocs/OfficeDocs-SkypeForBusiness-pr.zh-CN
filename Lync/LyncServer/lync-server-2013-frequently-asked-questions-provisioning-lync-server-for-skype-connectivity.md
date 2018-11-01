---
title: Lync Server 2013：常见问题：为 Lync Server 设置 Skype 连接
TOCTitle: 常见问题：为 Lync Server 设置 Skype 连接
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn440172(v=OCS.15)
ms:contentKeyID: 59602818
ms.date: 12/29/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 常见问题：为 Lync Server 2013 设置 Skype 连接

 

_**上一次修改主题：** 2016-12-27_

**问：Microsoft Lync 和 Skype 之间支持哪些功能？**

**答：**Skype 现在已成为 Microsoft 家族的一部分，为将统一通信方案扩展到使用 Skype 的亿万用户带来了新的可能性。此组合使用 Lync 客户能够与供应商、客户和合作伙伴保持联系并展开协作，这归功于 Lync 的丰富功能和 Skype 的广泛运用。

  - 即时消息以及音频和视频呼叫 - Lync 和 Skype 用户之间联盟的音频和视频呼叫以及即时消息传递

  - 状态共享 - 在联盟联系人之间交换状态信息

  - 简单的管理 - 设置和控制，遵照贵组织的策略和标准配置联盟通信

**问：怎么做才能有资格将我的 Lync 部署与 Skype 进行连接？**

**答：**如果您具有以下各项，那么您已获得 Skype 连接授权：

  - 面向您的组织中将连接到 Skype 的用户和/或设备的 Lync Server（2010 或 2013）与 Lync Server 标准版客户端访问许可证（"CAL"；2010 或 2013）。

  - Lync Online（作为独立的许可证或者作为 Office 365 套件的一部分）。但是，此服务 (pic.lync.com) 仅用于设置 Lync Server 与 Lync Server 和 Lync Online 混合部署。Lync Online PIC 设置在 Lync Online 控制面板 (LOCP) 中执行。

**问：Lync 最终用户必须执行什么操作才能连接到 Skype 联系人？**

**答：**在激活域并由组织的 Lync 管理员启用功能之后，Lync 用户可以将 Skype 联系人添加到 Lync 客户端中的联系人列表。

**问：Skype 最终用户必须执行什么操作才能连接到 Lync 联系人？**

**答：**所有希望连接到 Lync 用户的 Skype 用户必须具有与其 Skype ID 相关联的 Microsoft 帐户并使用该 Microsoft 帐户进行登录。这可以在 Skype 客户端中启用。

**问：与 Windows Live 的联盟是否仍然可用？**

**答：**自 2012 年 10 月开始，Microsoft 开始帮助 Windows Live Messenger (WLM) 用户迁移到 Skype，打算最终弃用 WLM。只要 WLM 仍在市场中使用，Lync 就会继续支持与 WLM 的联盟，但是不允许激活任何其他的 Windows Live 域。WLM 用户迁移由 Mac 版和 Windows 版（2012 年 10 月 25 日发布）Skype 6.0 提供支持，允许使用 Microsoft 帐户（即与 WLM 相同的凭据）登录。简单地登录到 Skype 之后，WLM 联系人列表会自动填充到 Skype 中，用户可以利用 Skype 扩展的通信功能，例如，呼叫座机和手机、屏幕共享、组视频呼叫以及对各种各样的设备的支持。而且，WLM 用户的联盟 Lync 联系人将与其余联系人列表一起迁移到 Skype 中，这些联系人在 Skype 和 Lync 之间进行的 IM 将立即可用。Lync 客户无需执行任何操作即可继续使用服务。

**问：与 Yahoo\! 或 AOL 的联盟是否仍然可用？**

**答：**对于 Lync 和 Office Communications Server 的客户，与 Yahoo\! 和 AOL 的联盟即将结束。Microsoft 之所以能够提供这些服务离不开 Yahoo\! 和 AOL 的支持，但这些支持的基础协议正在逐步终止。对于 Yahoo\! 和 AOL，服务将在 2014 年 6 月截止。

  - Yahoo：服务将在 2014 年 6 月截止，客户继续需要通过 Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL") 获得许可。自 2012 年 9 月 1 日起，新订或续订合同不能再购买 PIC USL。在此日期之前购买了许可证的客户能够继续与 Yahoo\! 联盟直至服务关闭日期或许可证到期（以较早者为准）。协议上的 PIC 许可证日期超过 2014 年 6 月 30 日的客户将按照付款金额的比例享受折扣优惠（涵盖 2014 年 6 月 30 日之后的时间段）。

  - AOL：2014 年 6 月 30 日，Lync 的 IM 连接 ("PIC") 服务不再可用。为了限制服务结束时出现的客户中断，我们已停止设置其他客户域。在 2014 年 6 月 30 日之前，客户无需执行任何操作来继续支持与 AIM 的联盟通信。如果超出此日期（或者对于同时想要设置其他域的客户），替换服务可直接从 AOL 使用。有关 AOL 的新服务的详细信息，请参阅 <http://aimenterprise.aol.com/pic.php>（在 AOL.com 上打开新页）。

**问：我是否可以在购买 Lync 之前试用 Skype 连接？**

**答：**Skype 连接不提供试用。替代试用版，鼓励具有合格的许可证的 Lync 客户简单地注册服务以测试。

**问：设置需要哪些信息？**

**答：**要在合格的许可证下提交设置请求，您需要以下内容：

  - Microsoft 协议编号:
    
      - Microsoft 批量许可支持：Microsoft 批量许可协议编号
    
      - Microsoft 合作伙伴网络：总部合作伙伴 ID
    
      - 服务提供商许可协议：初始注册编号
    
      - 大量服务：产品注册编号

  - 访问边缘服务的完全限定的域名 (FQDN)
    
      - 至少需要一个访问边缘服务的 FQDN。
    
      - 如果您的组织有多台服务器运行访问边缘服务，请指定每个访问边缘服务的 FQDN。重要：如果您以前指定了访问边缘服务的 FQDN，而希望更改它，更改的设置可能需要数天才能完成，可能会导致服务中断。为防止服务中断，建议您维护以前指定的访问边缘服务 FQDN。

  - 会话初始协议 (SIP) 域。这是用户当前用于即时消息传递的 SIP URI 的域后缀。如果您的组织有多个 SIP 域，请为用于即时消息传递的每个域指定域后缀。例如，对于 user1@contoso.com，请为 SIP 域指定 contoso.com；对于 user1@example.fabrikam.com，请将 example.fabrikam.com 指定为 SIP 域。
    
    > [!NOTE]  
    > 仅指定 SIP 域的域后缀。不要为 SIP 域指定任何 FQDN（包括访问边缘服务的 FQDN）。
    


  - 联系信息。为您指定的每个 SIP 域的管理员指定电子邮件地址。

**问：在拆分域方案中如何启用 Lync-Skype 连接？**

**答：**如果您有 Lync Online 2013 和 Lync Server 内部部署拆分域方案（使用相同 SIP 域的联机和内部部署用户），请通过按以下顺序执行这两个步骤来启用 Lync-Skype 连接

1.  按《PIC 设置指南》所述设置内部部署 Lync-Skype 连接。

2.  等待直至看到确认表明您的域已由 Microsoft 设置。

3.  看到确认后，请使用 Lync 管理中心启用"外部通信"。有关详细信息，请参阅 [http://office.microsoft.com/zh-cn/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/zh-cn/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

此顺序非常重要。在 Lync Online 中启用通信之前，您必须设置内部部署连接。如果顺序颠倒，在 <https://pic.lync.com> 中针对内部部署输入的信息将不适用。如果您已针对与此域的外部通信设置 Lync Online，则必须将其禁用，等待 24 小时，再次启动，首先在 <https://pic.lync.com> 处输入内部部署信息，然后为 Lync Online 启用外部通信。

**问：是否可以为 Skype 连接设置多个访问边缘服务 FQDN？**

**答：**通过每个设置请求，您最多可以设置 10 个访问边缘服务 FQDN。

**问：我是否可以获得您为请求设置的组织找到的 Microsoft 帐户电子邮件地址列表？**

**答：**不能。这些地址被视为个人身份信息，不进行共享。

**问：如何添加其 ID 包含非 Windows Live 支持的域的 Windows Live Messenger 联系人？**

**答：**如果添加其帐户或 ID 不是 Windows Live 域的 Windows Live Messenger 用户，请按以下格式输入地址：\<用户名\>(\<域名\>)@msn.com，其中，\<域名\> 是指用户的电子邮件地址中的域名。例如，如果希望添加 ted@contoso.com，请使用以下格式：ted(contoso.com)@msn.com。有关 Windows Live 管理的域列表，请参阅"安装 Live Communications Server Service Pack 1 之后公共即时消息出现的已知问题"的"支持的域"部分，网址为 http://support.microsoft.com/?kbid=897567。

**问：设置过程需要多长时间？**

**答：**设置最多需要 30 天。

**问：如何知道设置何时完成？**

**答：**设置完成时，Microsoft 将发送电子邮件通知。

**问：如何更新我提交的配置或联系详细信息？**

**答：**设置完成后，您可以在用于请求设置的相同网站上更新您的信息。输入您的协议编号，然后单击"更新服务"。

