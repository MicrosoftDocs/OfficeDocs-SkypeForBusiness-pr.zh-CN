---
title: Lync Server 2013：点对点语音和视频报告
TOCTitle: 点对点语音和视频报告
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615040(v=OCS.15)
ms:contentKeyID: 49314522
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的点对点语音和视频报告

 

_**上一次修改主题：** 2015-03-09_

点对点语音和视频报告提供了指定时间段的语音和视频呼叫分布的详细信息（例如，按小时的呼叫或按每天的呼叫）。该报告还为您提供查看所有执行的语音和视频呼叫的选项或仅查看成功或失败呼叫的选项。这些报告显示细分为下列组的呼叫信息：

  - 按池的呼叫

  - 按呼叫类型的呼叫（例如， Lync 到 Lync 的呼叫与 Lync 对 PSTN 网络上人员的呼叫）

  - 按访问类型的呼叫（登录到内部网络上的用户与登录到外部网络上的用户）

  - 按 中介服务器的呼叫

## 访问点对点语音和视频报告

只需打开点对点活动摘要报告，然后单击下列任意指标，即可访问点对点语音和视频报告：

  - 点对点音频会话总数

  - 点对点音频总分钟数

  - 点对点视频会话总数

  - 点对点视频总分钟数

## 更好地使用点对点语音和视频报告

有多种方法可供筛选点对点语音和视频报告。但是，默认情况下这些筛选选项处于隐藏状态，无法查看。要查看为您提供的筛选选项，请单击报告窗口右上角的“显示/隐藏参数”按钮。

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方法查看数据。下表列出了可用于点对点语音和视频报告的筛选器。

### 点对点语音和视频报告筛选器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>开始日期</strong></p></td>
<td><p>时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束日期</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>间隔</strong></p></td>
<td><p>时间间隔。选择下列选项之一：</p>
<ul>
<li><p>每小时（最多可显示 25 个小时）</p></li>
<li><p>每天（最多可显示 31 天）</p></li>
<li><p>每周（最多可显示 12 周）</p></li>
<li><p>每月（最多可显示 12 个月）</p></li>
</ul>
<p>如果开始日期和结束日期超出了所选间隔允许的最大时间长度，则仅显示最长数值（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</p></td>
</tr>
<tr class="even">
<td><p><strong>媒体类型</strong></p></td>
<td><p>指示会话中使用的媒体的类型。选择下列选项之一：</p>
<ul>
<li><p>两者</p></li>
<li><p>音频</p></li>
<li><p>视频</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫处置</strong></p></td>
<td><p>指示会话是成功还是失败。选择下列选项之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>成功的呼叫</p></li>
<li><p>失败的呼叫</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>报告依据</strong></p></td>
<td><p>指示要在报告中使用的值。选择下列选项之一：</p>
<ul>
<li><p>会话计数</p></li>
<li><p>呼叫分钟数</p></li>
</ul></td>
</tr>
</tbody>
</table>


## 按池列出的点对点语音和视频活动的指标

下表列出了每个池的点对点语音和视频报告中提供的信息。

### 按池列出的点对点语音和视频活动的指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>池</strong></p></td>
<td><p>否</p></td>
<td><p>用于呼叫的 注册器池或 边缘服务器的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>进行呼叫的日期和时间段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>总计</strong></p></td>
<td><p>否</p></td>
<td><p>会话总数或消息总数。</p></td>
</tr>
</tbody>
</table>


## 按呼叫类型列出的点对点语音和视频活动的指标

下表列出了发起的每种呼叫类型的点对点语音和视频报告中提供的信息。

### 按呼叫类型列出的点对点语音和视频活动的指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>呼叫类型</strong></p></td>
<td><p>否</p></td>
<td><p>指示发起的呼叫类型。可以指定下列值之一：</p>
<ul>
<li><p>UC 到 UC</p></li>
<li><p>UC 到 PSTN</p></li>
<li><p>PSTN 到 UC</p></li>
<li><p>PSTN 到 PSTN</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>进行呼叫的日期和时间段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>总计</strong></p></td>
<td><p>否</p></td>
<td><p>会话总数或消息总数。</p></td>
</tr>
</tbody>
</table>


## 按访问类型列出的点对点语音和视频活动的指标

下表列出了每种网络访问类型的点对点语音和视频报告中提供的信息。

### 按访问类型列出的点对点语音和视频活动的指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>活动类型</strong></p></td>
<td><p>否</p></td>
<td><p>指示客户端在发起呼叫时已登录到内部网络还是外部网络。通常可指定下列值之一：</p>
<ul>
<li><p>内部</p></li>
<li><p>外部</p></li>
<li><p>混合</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>进行呼叫的日期和时间段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>总计</strong></p></td>
<td><p>否</p></td>
<td><p>会话总数或消息总数。</p></td>
</tr>
</tbody>
</table>


## 按中介服务器列出的点对点语音和视频活动的指标

下表列出了每台 中介服务器的点对点语音和视频报告中提供的信息。

### 按中介服务器列出的点对点语音和视频活动的指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>中介服务器</strong></p></td>
<td><p>否</p></td>
<td><p>中介服务器的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>进行呼叫的日期和时间段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>总计</strong></p></td>
<td><p>否</p></td>
<td><p>会话总数或消息总数。</p></td>
</tr>
</tbody>
</table>

