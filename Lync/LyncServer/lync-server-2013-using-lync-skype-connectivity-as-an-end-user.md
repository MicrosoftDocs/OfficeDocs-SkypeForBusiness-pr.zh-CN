---
title: Lync Server 2013：使用 Lync-Skype 连接作为最终用户
TOCTitle: 使用 Lync-Skype 连接作为最终用户
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn440175(v=OCS.15)
ms:contentKeyID: 59602825
ms.date: 12/29/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中使用 Lync-Skype 连接作为最终用户

 

_**上一次修改主题：** 2016-12-27_

Lync-Skype 连接使 Skype 用户和 Lync 用户能够相互添加为联系人、交换即时消息和进行音频和视频呼叫。当 Skype 用户添加 Lync 用户时，Skype 用户将在 Skype 中创建一个联系人，其中包含 Lync 用户的会话初始协议 (SIP) 统一资源标识符 (URI)。相反，当 Lync 用户添加 Skype 联系人时，Lync 用户将在 Lync 中创建一个联系人，其中包含 Skype 用户的 Microsoft 帐户 (MSA)，而不是 Skype 用户名。

**什么是 MSA？** Skype 用户必须使用 Microsoft 帐户（以前称为 Windows Live ID）登录 Skype 才能与 Lync 联系人进行通信。Microsoft 帐户由电子邮件地址和密码的组合构成，您可以使用它们登录以下类似服务：Microsoft OneDrive 存储技术、Windows Phone、Microsoft Xbox LIVE 联机游戏服务和 Microsoft Outlook 消息和协作客户端（以前称为 Microsoft Hotmail 基于 Web 的电子邮件服务或 Windows Live Messenger）。如果您使用电子邮件地址和密码登录这些服务或其他服务，那么您已经有 Microsoft 帐户。有关创建 Microsoft 帐户的详细信息，请参阅 Microsoft 帐户注册页面，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=306061](http://go.microsoft.com/fwlink/p/?linkid=306061)。您可以将您的现有 Skype 帐户与 Microsoft 帐户进行合并，以便跨各种应用程序和服务实现单一登录。帐户合并后，Skype 用户就可以向 Lync 用户发送联系人请求。

> [!IMPORTANT]  
> 为了使 Lync 和 Skype 用户能够完全地相互通信，必须满足以下要求：
> <ul>
> <li><p>Skype 用户必须使用 Microsoft 帐户 (MSA) 登录其 Skype 客户端。</p></li>
> <li><p>Lync 管理员必须为 Lync 用户启用公共 IM 连接。</p></li>
> <li><p>当 Skype 用户添加 Lync 联系人时，请验证联系人姓名下方是否显示 Lync 字样。这表明已找到 Lync URI。</p></li>
> <li><p>当 Skype 用户添加 Lync 联系人，并且为该 Lync 域返回了零个搜索结果时，PIC 设置过程可能尚未完成，或者尚未设置 Lync 域。</p></li>
> <li><p>根据 Lync 和 Skype 用户的隐私设置，在每个用户接受新联系人之前，IM、视频和状态可能都无法正常工作。</p></li>
> </ul>


**将 Skype 联系人添加到 Lync 2013**

1.  从 Lync 中，单击“添加联系人”、“添加我的组织外部的联系人”。

2.  从可用的联系人提供商列表中，选择“Skype”，如下所示。
    
    ![Lync 客户端：显示如何添加 Skype 联系人](images/Dn440175.ac4e2f21-c1d9-47d8-b99e-d49fe4eb36d7(OCS.15).jpg "Lync 客户端：显示如何添加 Skype 联系人")

3.  在“IM 地址”字段中，输入 Skype 用户的 Microsoft 帐户 (MSA)。

4.  在“添加到联系人组”下拉框中，选择要将用户添加至的联系人组。

5.  在“设置私人关系”下拉框中，选择合适的联系人设置，然后单击“确定”。

6.  该用户将在 Lync 中显示为联系人。选择用户，右键单击用户名，然后单击“查看联系人卡片”以查看用户属性。如下所示，您也可以依次单击“呼叫”和“Lync 呼叫”以与新添加的 Skype 用户建立音频和视频呼叫。
    
    ![Lync 客户端：向联系人发起 Lync 呼叫](images/Dn440175.cd7cb21a-87f7-4bfa-b30c-980d4098d226(OCS.15).jpg "Lync 客户端：向联系人发起 Lync 呼叫")

有关联系人支持的其他信息，请参阅[在 Lync 中添加联系人](http://office.microsoft.com/zh-cn/office365-lync-online-help/add-a-contact-in-lync-ha102828922.aspx)和 [在 Lync 中添加外部联系人](http://office.microsoft.com/zh-cn/office365-lync-online-help/add-an-external-contact-in-lync-ha104038998.aspx?ctt=5%26origin=ha102828922)

当 Skype 用户的 Microsoft 帐户使用自定义域名（如 <strong>bob@contoso.com</strong>）时，Lync 用户可通过两种方式将该 Microsoft 帐户添加到 Lync：

1.  使用“添加联系人”图标或者

2.  使用“查找联系人或聊天室，或拨打号码”字段。

在每个实例中，Lync 用户必须按照以下格式输入 Skype 用户的电子邮件： <strong>用户(域名)@msn.com</strong>。

> [!IMPORTANT]
> 此帐户对于使用以下域名的 Microsoft 帐户不是必需的： <strong>@live.com、@hotmail.com 或 @outlook.com</strong>。有关支持的自定义域名的详细信息，请参阅 <a href="http://support.microsoft.com/kb/897567">支持的公共 IM 域</a>。


**使用自定义域名时将 Skype 联系人添加到 Lync**

1.  从 Lync 中，单击“添加联系人”、“添加我的组织外部的联系人”。

2.  从可用的联系人提供商列表中，选择“Skype”，如下所示。
    
    ![Lync 客户端：显示如何添加 Skype 联系人](images/Dn440175.ac4e2f21-c1d9-47d8-b99e-d49fe4eb36d7(OCS.15).jpg "Lync 客户端：显示如何添加 Skype 联系人")

3.  在“IM 地址”字段中，按照格式 <strong>用户(域名)@msn.com</strong> 输入 Skype 用户的 Microsoft 帐户 (MSA)。因此对于用户 bob@contoso.com，输入内容将是 <strong>bob(contoso.com)@msn.com</strong>，如下所示。
    
    ![Lync 客户端“新联系人”设置](images/Dn440175.422e69b5-2c0c-4260-858f-f10309af772f(OCS.15).jpg "Lync 客户端“新联系人”设置")

4.  在“添加到联系人组”下拉列表框中，选择要将用户添加至的联系人组。

5.  在“设置私人关系”下拉列表框中，选择合适的联系人设置，然后单击“确定”。

6.  Lync 用户也可以使用 Lync 中的“查找联系人或聊天室，或拨打号码”字段，并添加类似于 <strong>用户(域名)@msn.com</strong> 的地址。因此对于 Microsoft 帐户 bob@contoso.com，输入内容将是 <strong>bob(contoso.com)@msn.com</strong>，如下所示。
    
    ![在 Lync 客户端搜索联系人](images/Dn440175.69787db8-f9b9-49e5-b197-b90b10393301(OCS.15).jpg "在 Lync 客户端搜索联系人")

7.  按照此过程前面的步骤 4 和 5 将联系人添加到联系人组并选择合适的私人关系。

**将 Lync 联系人添加到 Skype**

1.  登录到 Skype。Skype 用户必须使用 Microsoft 帐户 (MSA) 登录其 Skype 客户端。
    
    ![Skype 客户端登录页面](images/Dn440175.b4fd7c5a-be35-4205-80c7-872863b7a91d(OCS.15).jpg "Skype 客户端登录页面")

2.  选择“添加联系人”图标。

3.  输入 Lync 用户的 SIP URI。例如 bob@contoso.com。

4.  当 Skype 在搜索结果中找到匹配项时，请在 Lync 用户名的下方查找 **Lync** 字样。这表明 Skype 已成功地找到 Lync 客户端的 SIP URI。单击名称。
    
    ![显示 Lync 联系人的 Skype 客户端](images/Dn440175.4e690a72-1a54-4442-89cf-0fb45ac5f56a(OCS.15).jpg "显示 Lync 联系人的 Skype 客户端")

5.  在窗口右上角，单击“添加到联系人”。

6.  新联系人现在将添加到您的联系人列表，但是在他们接受您的请求之前，您将看到一个问号而不是其状态图标。当新联系人接受您的请求时，您能够看到他们何时处于联机状态、启动 IM 对话和进行音频和视频呼叫。
    
    ![Skype 客户端与 Lync 联系人的 IM 对话](images/Dn440175.86ca6f81-4db9-45ba-8511-1f7541aaf066(OCS.15).jpg "Skype 客户端与 Lync 联系人的 IM 对话")
    
    > [!IMPORTANT]
    > Lync Server 管理员必须配置 Lync 用户的策略设置以允许传入请求。如果未配置，Lync 用户不会收到来自 Skype 用户的联系人请求。根据 Lync 用户的策略设置的配置，添加 Skype 用户这一请求将出现在 Lync 客户端的“新建”选项卡上。要开始与 Skype 用户进行通信，Lync 用户必须将 Skype 用户添加到其收藏夹列表或联系人列表。下图显示了 Lync 客户端中“新建”选项卡的位置。
    
    ![Lync 客户端“新联系人”页](images/Dn440175.b1cf8570-1401-47d9-ab14-b04f0d7e8a7a(OCS.15).jpg "Lync 客户端“新联系人”页")

Lync 用户必须配置 Lync 通知以确保发送自 Skype 用户的请求显示并且可由 Lync 用户发现。要配置 Lync 通知，请完成以下过程。

**配置 Lync 通知**

1.  从 Lync 客户端中，单击“选项”图标。

2.  选择“通知”。

3.  在“常规通知”下，选中“当某人将我添加到他/她的联系人列表时告诉我”。

4.  在“未使用 Lync 的联系人”下方，选择“允许邀请，但阻止所有其他通信”。

5.  单击“确定”关闭“选项”窗口。

![Lync 客户端“选项”对话框 - “通知”页](images/Dn440175.b36ed67f-f394-4f66-b60a-b74793001bfc(OCS.15).jpg "Lync 客户端“选项”对话框 - “通知”页")

