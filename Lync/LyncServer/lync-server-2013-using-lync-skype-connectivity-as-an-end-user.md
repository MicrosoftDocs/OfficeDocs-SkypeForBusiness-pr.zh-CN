---
title: Lync Server 2013：使用 Lync-Skype 连接作为最终用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5404a42b0d8e2052541ccb9f9178bf33408c2099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>在 Lync Server 2013 中使用 Lync-Skype 连接作为最终用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-12-27_

Lync-Skype 连接使 Skype 用户和 Lync 用户能够将彼此添加为联系人、交换即时消息和进行音频和视频通话。 当 Skype 用户添加 Lync 用户时，Skype 用户将在 Skype 中创建一个联系人，其中包含 Lync 用户的会话初始协议（SIP）统一资源标识符（URI）。 相反，当 Lync 用户添加 Skype 联系人时，Lync 用户将在 Lync 中创建一个联系人，其中将包含 Skype 用户的 Microsoft 帐户（MSA），而不是 Skype 用户名。

**什么是 MSA？** Skype 用户必须使用 Microsoft 帐户（以前称为 Windows Live ID）登录 Skype，才能与 Lync 联系人通信。Microsoft 帐户包含电子邮件地址和密码的组合，您也可以使用该地址和密码登录服务，例如 Microsoft OneDrive 存储技术、Windows Phone、Microsoft Xbox LIVE online 游戏服务和 Microsoft Outlook 消息和协作客户端（以前是基于 Microsoft Hotmail web 的电子邮件服务或 Windows Live Messenger）。如果您使用电子邮件地址和密码登录这些或其他服务，则您已经拥有 Microsoft 帐户。有关创建 Microsoft 帐户的详细信息，请参阅中的 Microsoft 帐户注册页面[https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)。 你可以通过各种应用程序和服务将现有 Skype 帐户与 Microsoft 帐户合并，以便进行单一登录。 帐户合并后，Skype 用户可以向 Lync 用户发送联系人请求。

<div>


> [!IMPORTANT]  
> 为了让 Lync 和 Skype 用户完全通信，必须满足以下要求： 
> <UL>
> <LI>
> <P>Skype 用户必须使用 Microsoft 帐户（MSA）登录到其 Skype 客户端。</P>
> <LI>
> <P>Lync 用户必须通过其 Lync 管理员启用公共 IM 连接。</P>
> <LI>
> <P>当 Skype 用户添加 Lync 联系人时，请验证 word Lync 是否显示在联系人姓名下方。 这表示已找到 Lync URI。</P>
> <LI>
> <P>当 Skype 用户添加 Lync 联系人，并且为该 Lync 域返回零个搜索结果时，PIC 设置过程可能尚未完成，或者 Lync 域尚未设置。</P>
> <LI>
> <P>根据 Lync 和 Skype 用户的隐私设置，IM、视频和联机状态可能不起作用，直到每位用户都接受新联系人。</P></LI></UL>



</div>

**将 Skype 联系人添加到 Lync 2013**

1.  从 Lync 中，单击 "**添加联系人"，添加不在我的组织中的联系人**。

2.  从可用的联系人提供商列表中，选择 " **Skype**"。

3.  在 " **IM 地址**" 字段中，输入 Skype 用户的 Microsoft 帐户（MSA）。

4.  在 "**添加到联系人组**" 下拉框中，选择要将用户添加到的联系人组。

5.  在 "**设置私人关系**" 下拉框中，选择相应的联系人设置，然后单击 **"确定"**。

6.  用户现在将在 Lync 中显示为联系人。 选择用户，右键单击用户名，然后单击 "**查看联系人卡片**" 以查看用户属性。 您现在可以与新添加的 Skype 用户建立音频或视频通话。

有关对联系人的支持的其他信息，请参阅[在 Lync 中添加联系人](https://support.office.com/en-us/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a)。

当 Skype 用户的 Microsoft 帐户使用自定义域名（如<strong>bob@contoso.com</strong> ）时，lync 用户可以通过两种方式将该 Microsoft 帐户添加到 Lync：

1.  使用 "**添加联系人**" 图标，或

2.  使用 "**查找联系人" 或 "会议室" 或 "拨打号码**" 字段。

在每个实例中，Lync 用户必须按以下格式输入 Skype 用户的电子邮件：<strong>用户（域名） @msn .com</strong> 。

<div>


> [!IMPORTANT]  
> 对于使用以下域名的 Microsoft 帐户，不需要执行此步骤： <STRONG>@live .com、@hotmail .com 或 @outlook .com</STRONG>。 有关受支持的自定义域名称的详细信息，请参阅<A href="https://support.microsoft.com/kb/897567">支持的公共 IM 域</A>。



</div>

**使用自定义域名时将 Skype 联系人添加到 Lync**

1.  从 Lync 中，单击 "**添加联系人"，添加不在我的组织中的联系人**。

2.  从可用的联系人提供商列表中，选择 " **Skype**"。

3.  在 " **IM 地址**" 字段中，在 "格式<strong>用户（域名）" @msn .Com</strong>中输入 Skype 用户的 Microsoft 帐户（MSA）。 因此对于用户 bob@contoso.com，该条目将是<strong>bob （contoso） @msn .com<strong> 。

4.  在 "**添加到联系人组**" 下拉列表框中，选择要将用户添加到的联系人组。

5.  在 "**设置私人关系**" 下拉列表框中，选择适当的联系人设置，然后单击 **"确定"**。

6.  Lync 用户还可以使用 "**查找某人或聊天室"，或者**在 Lync 中拨打号码域，并添加类似于以下<strong>用户（域名）的地址 @msn .com</strong> 。 因此对于 bob@contoso.com Microsoft 帐户，该条目将为<strong>bob （contoso） @msn .com</strong> 。

7.  按照此过程前面的步骤4和步骤5将联系人添加到联系人组并选择相应的私人关系。

**将 Lync 联系人添加到 Skype**

1.  登录 Skype。 Skype 用户必须使用 Microsoft 帐户（MSA）登录到其 Skype 客户端。

2.  选择 "添加联系人" 图标。

3.  输入 Lync 用户的 SIP URI。 例如，bob@contoso.com。

4.  当 Skype 在搜索结果中找到匹配项时，请在 Lync 用户的名称下方查找 word **lync** 。 这表示 Skype 已成功找到 Lync 客户端的 SIP URI。 单击名称。

5.  在窗口的右上角，单击 "添加到联系人"。

6.  新联系人现在已添加到您的联系人列表中，但在接受您的请求之前，您将看到一个问号，而不是状态图标。 当新联系人接受您的请求后，您将能够看到他们处于联机状态、启动 IM 对话以及进行音频和视频通话。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 管理员必须将 Lync 用户的策略设置配置为允许传入的请求。 如果不是，Lync 用户将不会收到来自 Skype 用户的联系人请求。 根据 Lync 用户策略设置的配置，添加 Skype 用户的请求将显示在 Lync 客户端的 "<STRONG>新建</STRONG>" 选项卡上。要开始与 Skype 用户通信，Lync 用户必须将 Skype 用户添加到 "收藏夹" 列表或联系人列表。 下图显示了<STRONG>新</STRONG>选项卡在 Lync 客户端中的位置。

    
    </div>

Lync 用户必须配置 Lync 警报，以确保从 Skype 用户发送的请求出现，并由 Lync 用户发现。 若要配置 Lync 通知，请完成下面的过程。

**配置 Lync 通知**

1.  在 Lync 客户端中，单击 "**选项**" 图标。

2.  选择 "**通知**"。

3.  在 "**常规通知**" 下，选中 "**当某人将我添加到其联系人列表时，请通知我**"。

4.  在 "**未使用 Lync 的联系人**" 下，选择 "**允许邀请"，但阻止所有其他通信**。

5.  单击 **"确定"** 关闭 "选项" 窗口。

</div>

<span> </span>

</div>

</div>

</div>

