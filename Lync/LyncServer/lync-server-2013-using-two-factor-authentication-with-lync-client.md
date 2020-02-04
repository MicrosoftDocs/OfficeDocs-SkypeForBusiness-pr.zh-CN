---
title: Lync Server 2013：对 Lync 客户端使用双因素身份验证
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
ms.openlocfilehash: 25b5d3305c5d9825342c0293325c9afca96c5a97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>将双因素身份验证与 Lync 客户端和 Lync Server 2013 结合使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-07-11_

本主题介绍了如何利用 Lync 2013 客户端的双重身份验证。

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>第一次登录 Lync 2013

在安装 Lync 2013 时，通常会自动配置您的 Lync 登录信息。 但首次使用 Lync 时，您可能必须手动启动客户端。

**首次登录 Lync**

1.  登录到您的组织的网络。

2.  选择 "**启动** \> **所有程序** \> **" \> Microsoft Lync Lync 2013**。
    
    您应看到 Lync 登录屏幕。
    
      - 如果登录地址框已经填充，请确认显示的地址是否正确。
    
      - 如果不正确，或者如果该框为空，请输入您的 Lync 登录地址（这通常与您的电子邮件地址相同）。
    
      - 如果显示空密码框，请添加您的密码。

3.  选择“登录”****。

</div>

<div>

## <a name="sign-out-of-lync"></a>注销 Lync

使用完 Lync 后，您可以从 "文件" 菜单中关闭显示、注销会话或退出程序。 下表说明了这些选项之间的差异。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>选项</th>
<th>执行的结果</th>
<th>如何执行</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>关闭</p></td>
<td><p>关闭 Lync 显示，但让使用你的用户 ID 标识的 Lync 会话继续运行。 因此，您可以继续接收通知并与其他人互动。</p>
<p>你可以随时通过单击任务栏上的 Lync 图标或屏幕底部的通知区域来恢复显示。</p></td>
<td><p>在 Lync 主窗口中，执行下列操作之一：</p>
<ol>
<li><p>选择 "<strong>选项</strong>" 按钮，然后选择 "<strong>文件</strong> &gt; <strong>关闭</strong>"。</p></li>
<li><p>单击窗口右上角的“关闭”<strong></strong>按钮 (X)。</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>注销</p></td>
<td><p>结束与你的用户 ID 相关联的 Lync 会话，但 Lync 会继续在后台运行。 注销时，登录窗口将会出现。</p>
<div>

> [!TIP]  
> 注销时选择“删除我的登录信息”<STRONG></STRONG>以从计算机中删除您的登录 ID 和密码记录。这样做使支持人员可以更轻松地解决登录问题。还通过使未经授权的用户难以使用您的凭据登录来帮助确保您的登录信息更安全。


</div></td>
<td><p>在 Lync 主窗口中，选择 "<strong>选项</strong>" 按钮，然后选择 "<strong>文件</strong> &gt; <strong>注销"。</strong></p></td>
</tr>
<tr class="odd">
<td><p>退出</p></td>
<td><p>结束 Lync 会话并在计算机上关闭 Lync。 退出后，如果要重新启动 Lync，请选择 "<strong>启动</strong> &gt; <strong>所有程序</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>"。</p></td>
<td><p>在 Lync 主窗口中，选择 "<strong>选项</strong>" 按钮，然后选择 "<strong>文件</strong> &gt; <strong>退出</strong>"。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>使用智能卡登录 Lync

某些组织现在使用一个称为双因素身份验证的多步骤登录过程来提高其 Lync 2013 用户的安全性。 如果你希望使用此选项，则需要 "智能卡" 才能登录 Lync。 智能卡分为两种种类，物理和虚拟：

  - ****   有关信用卡大小的实物。 登录时请将其插入到智能卡读卡器中。

  - **虚拟**   非物理对象，而是写入计算机上的特殊芯片的电子标识符，其实质上是将智能卡构建到计算机中。 仅适用于包含 TPM （受信任的平台模块）芯片的 Windows 8 计算机。

<div>

## <a name="enroll-your-smart-card"></a>注册智能卡

在您可以使用智能卡登录之前，必须“注册”该卡，也就是说，必须使用卡识别您的用户凭据。 不管是物理智能卡还是虚拟智能卡都是如此。 此过程可能已由 Lync Server 管理员执行。 如果不确定是否已执行，请与他们确认。

<div>


> [!NOTE]  
> 由于每个虚拟智能卡仅与安装它的设备相关联，因此需要为你使用的每个 Windows 8 计算机注册一个单独的卡。



</div>

**手动注册智能卡**

1.  登录到您将运行 Lync 的计算机。

2.  使用 Internet Explorer，浏览到您的组织的“证书颁发机构 Web 注册”页面。
    
    如果尚不具备此资源的 web 地址，请询问您的 Lync Server 管理员。 URL 将如下所示： https://MyCA.\[公司名称\]/certsrv。
    
    <div>
    

    > [!NOTE]  
    > 如果您正在使用 Internet Explorer 10，则可能需要在兼容模式下查看此网站。

    
    </div>

3.  当系统提示您登录证书页面时，请使用您的域帐户（例如您的计算机的管理员）登录。

4.  在网站的“欢迎”页面上，选择“申请证书”****。

5.  单击“高级申请”****。

6.  选择“创建并向此 CA 提交一个申请”****，然后单击“下一步”****。

7.  现在，您将看到“智能卡注册站”页面。 批准申请以安装 ActiveX 控件，然后填写“高级证书申请”表单，如下所示：
    
    1.  从“证书模板”**** 下拉列表中选择“智能卡用户”****。
    
    2.  选择“创建新密钥集”****。
    
    3.  在智能卡标签上查找制造商信息，然后从“CSP”**** 下拉列表中选择该制造商。
    
    4.  选择“CSP”**** 作为申请格式（如果尚未选中）。
    
    5.  从“哈希算法”下拉列表中选择“sha1”****（如果尚未选中）。
    
    6.  为您的证书提供您将识别的名称，然后单击“提交”****。

8.  现在在连接到注册站的读卡器中插入空智能卡，然后单击“注册”****。

9.  出现提示时，输入您的个人标识号 (PIN)，然后单击“确定”****。
    
    <div>
    

    > [!NOTE]  
    > 如果您的技术支持人员未向您提供用于注册智能卡的特殊 PIN，请使用默认智能卡 PIN 值 12345678。

    
    </div>

10. 选择可在首次使用智能卡时强制用户（您）更改 PIN 的选项。

11. 现在在连接到注册站的读卡器中插入空智能卡，然后单击“注册”****。

12. 出现提示时，输入您的个人标识号 (PIN)，然后单击“确定”****。
    
    <div>
    

    > [!NOTE]  
    > 如果您的技术支持人员未向您提供用于注册智能卡的特殊 PIN，请使用默认智能卡 PIN 值 12345678。

    
    </div>

13. 选择可在首次使用智能卡时强制用户（您）更改 PIN 的选项。

14. 单击“确定”**** 以确认显示的证书包含您的信息。

15. 看到已颁发证书的通知后，单击“安装此证书”**** 以完成注册过程。

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>通过智能卡凭据登录 Lync

首次使用智能卡之前，建议在 Lync 登录页面上单击 "**删除我的登录信息**"。 这样做可清除您的计算机上存储的任何登录凭据，并消除可能的错误源。

**若要通过智能卡凭据登录 Lync**

1.  启动 Lync 客户端。

2.  在“登录”屏幕上，在“登录地址”**** 框中键入您的登录用户帐户名称，然后单击“登录”****。

3.  如果您正在使用虚拟智能卡，请跳过此步骤。
    
    如果您正在使用物理智能卡，请在出现提示时在您的智能卡读卡器中插入智能卡，然后当检测到卡时单击“确定”****。

4.  为您的智能卡键入 PIN 号码，然后单击“确定”****。
    
    <div>
    

    > [!NOTE]  
    > 如果您的支持人员未向您提供智能卡 PIN 号码，请使用默认值 12345678。

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

