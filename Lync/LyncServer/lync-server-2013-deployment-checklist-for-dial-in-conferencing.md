---
title: Lync Server 2013 电话拨入式会议的部署清单
TOCTitle: 电话拨入式会议的部署清单
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412726(v=OCS.15)
ms:contentKeyID: 49313740
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的电话拨入式会议的部署清单

 

_**上一次修改主题：** 2015-03-09_

部署会议工作负荷时，将部署电话拨入式会议所需的组件。必须先部署 企业语音或 中介服务器以及公用电话交换网 (PSTN) 网关，然后才能配置电话拨入式会议。

用户必须先执行下表中的所有步骤，然后才能通过从 PSTN 拨号加入音频/视频会议。

> [!NOTE]  
> 如果要从 Office Communications Server 2007 R2 进行迁移，必须将最新更新应用于 Office Communications Server 2007 R2 环境，然后才能部署电话拨入式会议。



### 电话拨入式会议部署过程

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
<td><p><strong>创建包含会议工作负荷（包括 中介服务器和 PSTN 网关）的拓扑，并部署 前端池或 Standard Edition Server</strong></p></td>
<td><ol>
<li><p>运行 拓扑生成器以配置拓扑。配置拓扑时，请选择电话拨入式会议选项。</p></li>
<li><p>发布拓扑并部署 前端池或 Standard Edition Server。</p></li>
<li><p>如有必要，创建独立的 中介服务器并将其与 PSTN 网关相关联。</p>
<div>

> [!NOTE]  
> 仅当您没有部署 企业语音且没有将 中介服务器与 企业版前端服务器或 Standard Edition Server 并置时，才需要执行此步骤。如果部署了企业语音，则在企业语音部署过程中安装并配置中介服务器和 PSTN 网关。如果并置中介服务器，则在前端池或 Standard Edition Server 部署过程中安装并配置中介服务器。


</div></li>
</ol></td>
<td><p>Domain Admins</p>
<p>RTCUniversalServerAdmins</p>
<p>Administrator</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></p></li>
<li><p>创建独立的 中介服务器池： <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">在 Lync Server 2013 中部署中介服务器和定义对等方</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>配置拨号计划</strong></p></td>
<td><p>拨号计划是一组电话号码规范化规则，它将从特定位置拨打的电话号码转换为单一的标准 (E.164) 格式，以便进行电话授权和呼叫路由。从不同位置拨打的同一电话号码可以基于各自的拨号计划针对每个具体位置解析为不同的 E.164 号码。如果要部署 企业语音，请在部署过程中设置拨号计划，并且需要确保这些拨号计划还适用于电话拨入式会议。如果没有部署 企业语音，则需要为电话拨入式会议设置拨号计划。</p>
<p>使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序按如下所示设置拨号计划：</p>
<ol>
<li><p>创建一个或多个用于路由拨入访问电话号码的拨号计划。</p></li>
<li><p>为每个池分配一个默认的拨号计划。将“电话拨入式会议区域”设为应用拨号计划的地理位置。该区域会将拨号计划与拨入访问号码相关联。</p></li>
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
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">在 Lync Server 2013 中确保已为拨号计划分配区域</a></p></td>
</tr>
<tr class="even">
<td><p><strong>（可选）验证或修改用户个人标识号 (PIN) 要求</strong></p></td>
<td><p>使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序查看或修改会议“PIN 策略”。可以指定最小 PIN 长度、最大登录尝试次数、PIN 到期时间以及是否允许使用通用模式。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">（可选）在 Lync Server 2013 中验证 PIN 策略设置</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>配置会议策略以支持电话拨入式会议</strong></p></td>
<td><p>使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序配置“会议策略”设置。指定：</p>
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
<td><p><strong>配置拨入访问号码</strong></p></td>
<td><p>使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序设置拨入访问号码，用户通过呼叫该号码来拨入会议，并指定区域以将访问号码与相应的拨号计划相关联。组织者拨号计划指定的区域的前三个访问号码包含在会议邀请中。 电话拨入式会议设置页上提供了所有访问号码。</p>
<div>

> [!NOTE]  
> 创建拨入访问号码后，可以使用 <strong>Set-CsDialInConferencingAccessNumber</strong> cmdlet 修改 Active Directory 联系人对象的显示名称，以便用户可以更加轻松地识别正确的访问号码。


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
<td><p>使用 <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet 修改用于双音多频 (DTMF) 命令的键，参与者可使用这些命令控制会议设置（如静音和取消静音或锁定和解除锁定）。</p></td>
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
<td><p><strong>部署 Lync 2013 联机会议外接程序</strong></p></td>
<td><p>部署 Lync 2013 联机会议外接程序以便用户可以安排支持电话拨入式会议的会议。安装 Lync 2013 时，将自动安装 Lync 2013 联机会议外接程序。</p></td>
<td><p>Administrators</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">部署 Lync 2013 的联机会议加载项</a></p></td>
</tr>
<tr class="even">
<td><p><strong>配置用户帐户设置</strong></p></td>
<td><p>使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序将电话“线路 URI”配置为唯一的规范化电话号码（例如，tel:+14255550200）。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">在 Lync Server 2013 中配置用户帐户设置</a></p></td>
</tr>
<tr class="odd">
<td><p>（推荐）配置会议目录</p></td>
<td><p>使用 <strong>New-CsConferenceDirectory</strong> cmdlet 为池中的每 999 个用户创建一个会议目录。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">电话拨入式会议要求</a> <a href="recommended-create-conference-directories.md">（建议）创建会议目录</a></p></td>
</tr>
<tr class="even">
<td><p><strong>（可选）欢迎用户参加电话拨入式会议并设置初始 PIN</strong></p></td>
<td><p>使用 <strong>Set-CsPinSendCAWelcomeMail</strong> 脚本设置用户的初始 PIN，并发送包含初始 PIN 和指向 电话拨入式会议设置页的链接的欢迎电子邮件。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">（可选）在 Lync Server 2013 中欢迎用户参加电话拨入式会议</a></p></td>
</tr>
</tbody>
</table>

