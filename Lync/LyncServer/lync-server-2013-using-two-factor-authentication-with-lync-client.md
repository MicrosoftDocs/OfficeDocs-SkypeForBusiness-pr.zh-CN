---
title: Lync Server 2013：将双重身份验证与 Lync 客户端结合使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90dd3c40267f0994e7f41eabb689c869182cea7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508639"
---
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>对 Lync 客户端和 Lync Server 2013 使用双重身份验证

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-11_

本主题介绍了如何利用 Lync 2013 客户端的双重身份验证。

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>首次登录到 Lync 2013

在安装 Lync 2013 时，通常会自动配置你的 Lync 登录信息。 但首次使用 Lync 时，您可能必须手动启动客户端。

**首次登录 Lync**

1.  登录到您的组织的网络。

2.  选择 " **启动** \> **所有程序** \> **Microsoft Lync \> lync 2013**"。
    
    您应该会看到 Lync 登录屏幕。
    
      - 如果已填写 "登录地址" 框，请确认显示的地址正确无误。
    
      - 如果不正确，或者如果该框为空，请输入你的 Lync 登录地址 (这通常与您的电子邮件地址) 相同。
    
      - 如果显示 "空密码" 框，请添加您的密码。

3.  选择 **"登录"**。

</div>

<div>

## <a name="sign-out-of-lync"></a>注销 Lync

使用 Lync 完成后，可以从 "文件" 菜单中关闭 "显示"、"注销会话" 或 "退出程序"。 下表说明了这些选项之间的差异。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>选项</th>
<th>功能</th>
<th>如何执行</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>关闭</p></td>
<td><p>关闭你的 Lync 显示，但允许使用你的用户 ID 标识的 Lync 会话继续运行。 这样，你就可以继续获取通知并与其他人进行交互。</p>
<p>您可以通过单击任务栏上的 Lync 图标或屏幕底部的通知区域随时获取显示。</p></td>
<td><p>在 "Lync 主" 窗口中，执行下列操作之一：</p>
<ol>
<li><p>选择 " <strong>选项</strong> " 按钮，然后选择 " <strong>文件</strong> &gt; <strong>关闭</strong>"。</p></li>
<li><p>单击窗口右上角 (X) 中的 " <strong>关闭</strong> " 按钮。</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>注销</p></td>
<td><p>结束与您的用户 ID 关联的 Lync 会话，但 Lync 将继续在后台运行。 当您注销时，将会出现登录窗口。</p>
<div>

> [!TIP]  
> 在注销时选择 " <STRONG>删除我的登录信息</STRONG> "，从计算机中删除您的登录 ID 和密码记录。 这样做可能会使支持人员更轻松地解决登录问题。 它还可以通过让未经授权的用户难以使用您的凭据登录，从而帮助确保您的登录信息更安全。


</div></td>
<td><p>在 "Lync 主" 窗口中，选择 " <strong>选项</strong> " 按钮，然后选择 " <strong>文件</strong> &gt; <strong>注销</strong>"。</p></td>
</tr>
<tr class="odd">
<td><p>Exit</p></td>
<td><p>结束 Lync 会话并关闭计算机上的 Lync。 退出后，如果要重新启动 Lync，请选择 " <strong>启动</strong> &gt; <strong>所有程序</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>lync 2013</strong>"。</p></td>
<td><p>在 "Lync 主" 窗口中，选择 " <strong>选项</strong> " 按钮，然后选择 " <strong>文件</strong> &gt; <strong>退出</strong>"。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>使用智能卡登录 Lync

有些组织现在使用一个称为双重身份验证的多步骤登录过程来提高 Lync 2013 用户的安全性。 如果您希望使用此选项，则需要 "智能卡" 才能登录 Lync。 智能卡分为两种种类，物理和虚拟：

  - **物理**    关于信用卡的大小。 您在登录时将其插入到智能卡读取器中。

  - **虚拟**    不是物理对象，而是写入计算机上的特殊芯片的电子标识符，这实际上是将智能卡构建到计算机中的。 仅可用于包含 TPM (受信任的平台模块) 芯片的 Windows 8 计算机。

<div>

## <a name="enroll-your-smart-card"></a>注册智能卡

在使用智能卡登录之前，必须对卡进行 "注册"，即您的用户凭据必须用卡片标识。 无论是物理卡还是虚拟卡都是如此。 此过程可能已被你的 Lync Server 管理员执行。 如果你不确定是否已完成，请与他们进行检查。

<div>


> [!NOTE]  
> 由于每个虚拟智能卡仅与安装它的设备相关联，因此需要为您使用的每个 Windows 8 计算机注册一个单独的卡。



</div>

**手动注册智能卡**

1.  登录到您将在其上运行 Lync 的计算机。

2.  使用 Internet Explorer，浏览到您的组织的 "证书颁发机构 Web 注册" 页。
    
    如果你还没有此资源的 web 地址，请向你的 Lync Server 管理员咨询。 该 URL 将如下所示： https://MyCA.\ [yourcompanyname \] /certsrv。
    
    <div>
    

    > [!NOTE]  
    > 如果您使用的是 Internet Explorer 10，则可能需要在兼容模式下查看此网站。

    
    </div>

3.  当系统提示您登录到 "证书" 页时，请使用您的域帐户登录 (而不是作为计算机的管理员) 。

4.  在 "网站" "欢迎" 页上，选择 " **申请证书**"。

5.  选择 " **高级请求**"。

6.  选择 " **创建并向此 CA 提交一个请求**"，然后单击 " **下一步**"。

7.  现在，你将看到一个名为 "智能卡注册站" 的页面。 批准安装 ActiveX 控件的请求，然后完成 "高级证书请求" 表单，如下所示：
    
    1.  从 "**证书模板**" 下拉列表中选择 "**智能卡用户**"。
    
    2.  选择 " **创建新密钥集**"。
    
    3.  查找智能卡标签上的制造商信息，并从 **CSP** 下拉列表中选择该制造商。
    
    4.  选择 " **CSP** " 作为请求格式（如果尚未选中）。
    
    5.  从 "哈希算法" 下拉列表中选择 " **sha1** " （如果尚未选中）。
    
    6.  为您的证书指定一个名称，然后单击 " **提交**"。

8.  现在，将空白智能卡插入到连接到注册站的读卡器中，然后单击 " **注册**"。

9.  出现提示时，请输入您的个人识别码 (PIN) ，然后单击 **"确定"**。
    
    <div>
    

    > [!NOTE]  
    > 如果你的技术支持人员未向你提供用于注册智能卡的专用 PIN，请使用默认智能卡 PIN 值为12345678。

    
    </div>

10. 选择此选项可强制用户在首次使用智能卡时) 更改 PIN (。

11. 现在，将空白智能卡插入到连接到注册站的读卡器中，然后单击 " **注册**"。

12. 出现提示时，请输入您的个人识别码 (PIN) ，然后单击 **"确定"**。
    
    <div>
    

    > [!NOTE]  
    > 如果你的技术支持人员未向你提供用于注册智能卡的专用 PIN，请使用默认智能卡 PIN 值为12345678。

    
    </div>

13. 选择此选项可强制用户在首次使用智能卡时) 更改 PIN (。

14. 单击 **"确定** " 以确认显示的证书是否包含您的信息。

15. 在发现证书已颁发的情况下，单击 " **安装此证书** " 以完成注册过程。

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>使用智能卡凭据登录到 Lync

在首次使用智能卡之前，建议您在 Lync 登录页面上单击 " **删除我的登录信息** "。 执行此操作将清除存储在计算机上的任何登录凭据，并消除可能的错误源。

**使用智能卡凭据登录 Lync**

1.  启动 Lync 客户端。

2.  在 "登录" 屏幕上，在 " **登录地址** " 框中键入您的登录用户帐户名，然后单击 " **登录**"。

3.  如果使用的是虚拟智能卡，请跳过此步骤。
    
    如果使用的是物理智能卡，请将智能卡插入智能卡读卡器中，并提示您执行此操作，然后在检测到卡时单击 **"确定"** 。

4.  键入您的智能卡的 PIN 号码，然后单击 **"确定"**。
    
    <div>
    

    > [!NOTE]  
    > 如果你的支持人员未向你分配智能卡 PIN 号码，请使用默认值12345678。

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

