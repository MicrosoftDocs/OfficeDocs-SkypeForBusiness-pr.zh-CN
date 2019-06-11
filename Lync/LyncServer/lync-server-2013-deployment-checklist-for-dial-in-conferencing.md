---
title: Lync Server 2013 电话拨入式会议的部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44591676d69b5fb4ac3d66ce0e18718389a0c189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的电话拨入式会议的部署清单

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-10-03_

部署会议工作负荷时, 将部署电话拨入式会议所需的组件。 在配置拨入式会议之前, 你需要部署企业语音或中介服务器以及公共交换电话网络 (PSTN) 网关。

必须先执行下表中的所有步骤, 然后用户才能从 PSTN 拨入以加入音频/视频会议。

<div>


> [!NOTE]  
> 如果从 Office 通信服务器 2007 R2 迁移, 则必须在部署电话拨入式会议之前将最新更新应用到 Office 通信服务器 2007 R2 环境。



</div>

### <a name="dial-in-conferencing-deployment-process"></a>电话拨入式会议部署过程

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>阶段</th>
<th>步骤</th>
<th>权限</th>
<th>部署文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>创建包括会议工作负荷的拓扑, 包括中介服务器和 PSTN 网关, 以及部署前端池或标准版服务器</strong></p></td>
<td><ol>
<li><p>运行拓扑生成器以配置拓扑。 配置拓扑时，请选择电话拨入式会议选项。</p></li>
<li><p>发布拓扑并部署前端池或标准版服务器。</p></li>
<li><p>如有必要, 请创建独立的中介服务器, 并将其与 PSTN 网关关联。</p>
<div>

> [!NOTE]  
> 仅当你不部署企业语音且不将中介服务器与 Enterprise EditionFront End Server 或 Standard Edition 服务器一起 collocate 时, 才需要执行此步骤。 如果部署企业语音, 则在企业语音部署中安装并配置中介服务器和 PSTN 网关。 如果您 collocate 中介服务器, 请将中介服务器作为前端池或标准版服务器部署的一部分进行安装和配置。


</div></li>
</ol></td>
<td><p>Domain Admins</p>
<p>RTCUniversalServerAdmins</p>
<p>Administrator</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></p></li>
<li><p>创建独立的中介服务器池:<a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">在 Lync server 2013 中部署中介服务器和定义对等</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Configure dial plans</strong></p></td>
<td><p>拨号计划是一组电话号码规范化规则，它将从特定位置拨打的电话号码转换为单一的标准 (E.164) 格式，以便进行电话授权和呼叫路由。 从不同位置拨打的同一电话号码可以基于各自的拨号计划针对每个具体位置解析为不同的 E.164 号码。 如果你部署企业语音, 请将拨号计划设置为该部署的一部分, 并且你需要确保拨号计划还能容纳电话拨入式会议。 如果不部署企业语音, 则需要设置电话拨入式会议的拨号计划。</p>
<p>使用 Lync Server 2013 控制面板或 Lync Server Management Shell 设置拨号计划, 如下所示:</p>
<ol>
<li><p>创建一个或多个用于路由拨入访问电话号码的拨号计划。</p></li>
<li><p>为每个池分配一个默认的拨号计划。将“<strong>电话拨入式会议区域</strong>”设为应用拨号计划的地理位置。该区域会将拨号计划与拨入访问号码相关联。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">在 Lync Server 2013 中配置电话拨入式会议的拨号计划</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>确保已为拨号计划分配区域</strong></p></td>
<td><p>运行 <strong>Get-CsDialPlan</strong> 和 <strong>Set-CsDialPlan</strong> cmdlet 确保已为所有拨号计划分配区域。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">确保拨号计划 Lync Server 2013 已分配区域</a></p></td>
</tr>
<tr class="even">
<td><p><strong>（可选）验证或修改用户个人标识号 (PIN) 要求</strong></p></td>
<td><p>使用 Lync Server 2013 控制面板或 Lync Server Management Shell 查看或修改会议<strong>PIN 策略</strong>。 可以指定最小 PIN 长度、最大登录尝试次数、PIN 到期时间以及是否允许使用通用模式。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">（可选）在 Lync Server 2013 中验证 PIN 策略设置</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>配置会议策略以支持电话拨入式会议</strong></p></td>
<td><p>使用 Lync Server 2013 控制面板或 Lync Server Management Shell 配置<strong>会议策略</strong>设置。 指定：</p>
<ul>
<li><p>是否启用 PSTN 会议拨入。</p></li>
<li><p>用户能否邀请匿名参与者。</p></li>
<li><p>未经身份验证的用户能否通过拨出式电话加入会议。通过拨出式电话，会议服务器会呼叫用户，用户接听电话即可加入会议。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">在 Lync Server 2013 中配置电话拨入式会议策略</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configure dial-in access numbers</strong></p></td>
<td><p>使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序设置拨入访问号码, 用户拨打该号码拨入到会议, 并指定将访问号码与相应的拨号计划相关联的区域。 组织者拨号计划指定的区域的前三个访问号码包含在会议邀请中。 "电话拨入式会议设置" 页面上提供了 "所有访问号码"。</p>
<div>

> [!NOTE]  
> 创建拨入访问号码后, 您可以使用<STRONG>CsDialInConferencingAccessNumber</STRONG> Cmdlet 修改 Active Directory 联系人对象的显示名称, 以便用户可以更轻松地识别正确的访问号码。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">在 Lync Server 2013 中配置电话拨入式会议访问号码</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>（可选）验证电话拨入式会议设置</strong></p></td>
<td><p>使用 <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet 搜索具有未被任何访问号码使用的电话拨入式会议区域的拨号计划，以及尚未分配区域的访问号码。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">（可选）在 Lync Server 2013 中验证电话拨入式会议设置</a></p></td>
</tr>
<tr class="even">
<td><p><strong>（可选）修改 DTMF 命令的键映射</strong></p></td>
<td><p>使用<strong>CsDialinConferencingDtmfConfiguration</strong> cmdlet 修改用于双声 MULTIFREQUENCY (DTMF) 命令的键, 参与者可以使用这些命令控制会议设置 (如静音和取消静音或锁定和解锁)。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">（可选）在 Lync Server 2013 中修改 DTMF 命令的键映射</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>（可选）修改会议加入和离开通知行为</strong></p></td>
<td><p>使用 <strong>Set-CsDialinConferencingConfiguration</strong> 更改参与者加入和离开会议时通知的工作方式。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">（可选）在 Lync Server 2013 中启用和禁用会议加入和离开通知</a></p></td>
</tr>
<tr class="even">
<td><p><strong>（可选）验证电话拨入式会议</strong></p></td>
<td><p>使用 <strong>Test-CsDialInConferencing</strong> cmdlet 测试指定池的访问号码是否正常工作。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">（可选）在 Lync Server 2013 中验证电话拨入式会议</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>部署 Lync 2013 的联机会议加载项</strong></p></td>
<td><p>为 Lync 2013 部署联机会议加载项, 以便用户可以安排支持电话拨入式会议的会议。 安装 Lync 2013 时, 将自动安装适用于 Lync 2013 的联机会议加载项。</p></td>
<td><p>管理员</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">部署 Lync 2013 的联机会议加载项</a></p></td>
</tr>
<tr class="even">
<td><p><strong>配置用户帐户设置</strong></p></td>
<td><p>使用 Lync Server 2013 控制面板或 Lync Server Management Shell 将电话<strong>线路 URI</strong>配置为唯一的、标准化的电话号码 (例如, 电话: + 14255550200)。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">在 Lync Server 2013 中配置用户帐户设置</a></p></td>
</tr>
<tr class="odd">
<td><p>（推荐）配置会议目录</p></td>
<td><p>使用 <strong>New-CsConferenceDirectory</strong> cmdlet 为池中的每 999 个用户创建一个会议目录。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 中的电话拨入式会议要求</a><a href="recommended-create-conference-directories.md">(推荐) 创建会议目录</a></p></td>
</tr>
<tr class="even">
<td><p><strong>（可选）欢迎用户参加电话拨入式会议并设置初始 PIN</strong></p></td>
<td><p>使用<strong>CsPinSendCAWelcomeMail</strong>脚本设置用户的初始引脚, 并发送包含初始 PIN 和指向电话拨入式会议设置页面的链接的欢迎电子邮件。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">（可选）在 Lync Server 2013 中欢迎用户参加电话拨入式会议</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

