<table style="height: 115px;" width="466">
<tbody>
<tr>
<th style="text-align: center;" colspan="3"><strong>版本路线表</strong></th>
</tr>
<tr>
<td><strong>版本号</strong></td>
<td><strong>更新日期</strong></td>
<td><strong>重要改动备注</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.10</span></strong></td>
<td><strong><span style="color: #008000;">20141102</span></strong></td>
<td><strong>创建</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.11</span></strong></td>
<td><strong><span style="color: #008000;">20141104</span></strong></td>
<td><strong>容错性与友好性</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.12</span></strong></td>
<td><strong><span style="color: #008000;">20141105</span></strong></td>
<td><strong>友好性</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.13</span></strong></td>
<td><strong><span style="color: #008000;">20141116</span></strong></td>
<td><strong>友好性</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.20</span></strong></td>
<td><strong><span style="color: #008000;">20141117</span></strong></td>
<td><strong>功能：集中打包下载</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.21</span></strong></td>
<td><strong><span style="color: #008000;">20141120</span></strong></td>
<td><strong>容错性与友好性</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.22</span></strong></td>
<td><strong><span style="color: #008000;">20141123</span></strong></td>
<td><strong>bug fix</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.30</span></strong></td>
<td><strong><span style="color: #008000;">20141125</span></strong></td>
<td><strong>功能：参考文献格式生成</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.31</span></strong></td>
<td><strong><span style="color: #008000;">20141126</span></strong></td>
<td><strong>功能扩展</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.32</span></strong></td>
<td><strong><span style="color: #008000;">20150113</span></strong></td>
<td><strong>功能扩展</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.40</span></strong></td>
<td><strong><span style="color: #008000;">20150321</span></strong></td>
<td><strong>功能扩展:RIS解析</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.41</span></strong></td>
<td><strong><span style="color: #008000;">20150402</span></strong></td>
<td><strong>容错性:新文章命名</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.42</span></strong></td>
<td><strong><span style="color: #008000;">20150403</span></strong></td>
<td><strong>bug fix: ris结尾解析</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.43</span></strong></td>
<td><strong><span style="color: #008000;">20150424</span></strong></td>
<td><strong>bug fix: ris关键词解析</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.44</span></strong></td>
<td><strong><span style="color: #008000;">20150519</span></strong></td>
<td><strong>bug fix: Journal short解析
</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.50</span></strong></td>
<td><strong><span style="color: #008000;">20150714</span></strong></td>
<td><strong>重要功能扩展
</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.51</span></strong></td>
<td><strong><span style="color: #008000;">20150728</span></strong></td>
<td><strong>功能扩展； bug fix: record尸体处理
</strong></td>
</tr>
<tr>
<td><strong><span style="color: #3366ff;">v0.52</span></strong></td>
<td><strong><span style="color: #008000;">20150918</span></strong></td>
<td><strong>功能扩展: ref line
</strong></td>
</tr>

</tbody>
</table>
早就有计划做一个服务器端的文献管理、共享和备份的资料库，由于最近要开始大量阅读文献，再也受不了随意乱放的pdf。终于被逼做这件事情了，花了一整天的时间完成v0.01，距离最终理想目标还太远太远，但v0.01已经能够实现最基本的核心功能，只写了四个php文件加一个期刊简写的ascii文件，数据仓储直接用目录+enw实现，毕竟重要的还是文件名归类和云端备份，这两点都实现了。

目前实现的功能：
<ol>
	<li><strong>上传google生成的endnote导入enw文件</strong></li>
	<li><strong>解析enw文件结构，生成唯一标志的文件名</strong></li>
	<li><strong>在enw文件中写入url及label，直接打开导入endnote</strong></li>
	<li><strong>上传对应的pdf文件</strong></li>
	<li><strong>采用唯一标志的文件名命名enw文件与pdf文件于仓储目录</strong></li>
</ol>
测试：

1.从google获得enw导入文件


2.上传enw文件到Lab服务器


3.solve_enw.php解析enw文件并生成唯一标志的文件名，写url和label信息进入enw文件，并提供重新导出：


4.上传对应pdf文件，并命名唯一化，唯一化命名可以在本地同样使用：


5.enw和pdf命名唯一化后放入仓库：


6.可以直接通过endnote中的url打开Lab服务器的在线文件：

毕竟是v0.01，输入没有做合法性检查，美工几乎没有，距离自动通过doi进行解析下载以及引文信息生成还差太远。将来如果要实现类似endnote那种方便的查询增删功能，而且如果要共享涉及到账户用户权限的问题，不用关系数据库是不可能的，目前这种单纯用目录组织数据结构肯定行不通，可是mySQL一窍不通，我还是太水了，有空闲下来再慢慢玩吧，现在功能对我个人基本够用:-)

<strong><span style="color: #008000;">#Up to 20141102#</span></strong>

<strong>【注】文件名唯一标志：</strong>

<span style="color: #00ccff;"><strong>%A1-%J-%V_%N_%Ps-%Pe</strong></span>

<span style="color: #00ccff;"><strong>第一作者-期刊（简写）-卷号_期号_起始页-终了页</strong></span>

<span style="color: #00ccff;"><strong>Giannini-Science-2003-302_5647_1027-1030</strong></span>

<strong><span style="color: #008000;">#Up to 20141103#</span></strong>

考虑到工程量不大，决定重新命名版本号：
<ul>
	<li><strong>miner mod  (细微更改)</strong> 占用第二位小数，例如友好性提高</li>
	<li><strong>major mod  (重要更改)</strong> 占据第一位小数，例如功能添加</li>
	<li><strong>kernel mod (内核更改)</strong> 占据个位数字，例如新技术的引入（mySQL、R等），数据库结构调整，正式发布版本等。</li>
</ul>
目前最新版本为

<strong><em>v0.11</em></strong>

Miner Mods：
<ol>
	<li><strong>增加了对仓储的重复性检查，仓储数据列表位于list.dat中，提高容错性与健壮性</strong></li>
	<li><strong>考虑了对仅有vol编号或者doi编号的文献命名的，提高容错性与健壮性</strong></li>
	<li><strong>在个别页面增加了主页跳转链接，提高用户友好性</strong></li>
</ol>
<strong><span style="color: #008000;"> </span></strong>

今天花了一个多小时时间，上传了80多篇文献，命名全部归一化，enw全部生成完毕，随时可以导入endnote。比起之前第一次手工整理时的效率，还是提升了很多的。

<strong>考虑：加入以日期命名的enw生成目录，以便将来定期整理文献时方便导入endnote。</strong>

<strong><span style="color: #008000;">#Up to 20141104#</span></strong>

<strong><em>v0.12</em></strong>

今天增加了一些更为客户友好的操作，提高文献归库效率

Miner Mods：
<ol>
	<li><strong>增加按日期命名的record目录，方便用户集中下载当日整理过的enw文件导入endnote</strong></li>
	<li><strong>采用file_get_contents函数直接勾取google的enw文件，免除用户先下载后上传的麻烦</strong></li>
	<li><strong>采用file_get_contents函数直接勾取pdf文件，免除用户先下载后上传的麻烦</strong></li>
	<li><strong>在个别页面增加了主页跳转链接，提高用户友好性</strong></li>
</ol>
Show一张endnote导入后的截图


<strong><span style="color: #008000;">#Up to 20141105#</span></strong>

<strong><em>v0.13</em></strong>

增加更为客户友好的操作，提高文献归库效率

Miner Mod：
<ol>
	<li><strong>增加上传文献结束后直接进入文献的链接</strong></li>
</ol>
<strong><span style="color: #008000;">#Up to 20141116#</span></strong>

<em><strong>v0.20</strong></em>

用了一晚上的时间进行了Major mod，终于可以升级一级版本号啦。增加了文献打包下载的功能，php调用一堆系统函数实现，我真是弱爆了，数据量大的时候估计效率会是个问题，不过还好，个人使用的情况绝不会动辄几百篇文献地down吧，考虑版本公开后不允许批量下载pdf，只可以下载enw。目前计划公开版的版本本号为v1.xx

增加的文件：

<em>package.php</em>

<em>package_down.php</em>

打包页面示例：


Major Mod：
<ol>
	<li><strong>增加集中打包下载的功能</strong></li>
</ol>
（提醒：需要加入文献删除功能了）

<strong><span style="color: #008000;">#Up to 20141117#</span></strong>

<strong><em>v0.21</em></strong>

Miner Mods：
<ol>
	<li><strong>增加了文献名模糊匹配搜索（子串匹配，大小写不敏感），提高文献归库效率</strong></li>
	<li><strong>重复提交的文献提供旧文件链接，用户友好。</strong></li>
</ol>
<strong><span style="color: #008000;">#Up to 20141120#</span></strong>

<strong><em>v0.22</em></strong>

Miner Mods：
<ol>
	<li><strong>修正集中打包下载buffer bug</strong></li>
</ol>
<strong><span style="color: #008000;">#Up to 20141123#</span></strong>

<strong><em>v0.30</em></strong>

晚上画图，ncl出图太慢，间隙用来给paperhub加入文献格式生成的功能，加着加着就忘了画图了，索性今天搞定这个major mod。目前仅仅对 paper to be submitted to Climate Dynamics进行了设置。引入了1页php和一个针对CD的期刊名缩略库short_ref_cd.dat。每增加一个submit的期刊就要引入一个缩略库，目前在没有办法将数据封装到json或者用关系数据库的情况下只能这样，当然也只能作为个权宜之计，以后submit的文章多了（如果能办到的话～），一堆文件看着都头疼……寒假如果可以的话，学学R，把组织格式shift到json上。

Major Mods：
<ol>
	<li><strong>加入针对投稿期刊的参考文献样式自动生成，目前仅针对Climate Dynamics，考虑到中文名缩写问题，生成first name缩写与不缩写两种形式，正式写入文章时需要调整下
</strong></li>
</ol>
范例图

<pre><code>Chou Chia, Neelin J David (2004) Mechanisms of global warming impacts on regional tropical precipitation*. J Clim 17: 2688-2701.
Chou C, Neelin JD (2004) Mechanisms of global warming impacts on regional tropical precipitation*. J Clim 17: 2688-2701. </code></pre>
<strong><span style="color: #008000;">#Up to 20141125#</span></strong>

<strong><em>v0.31</em></strong>

Minor Mods：
<ol>
	<li><strong>加入针对JC的参考文献样式自动生成</strong></li>
</ol>
<strong><span style="color: #008000;">#Up to 20141126#</span></strong>

<strong><em>v0.32</em></strong>

Minor Mods：
<ol>
	<li><strong>加入文献本地pdf附件的链接</strong></li>
</ol>
<strong><span style="color: #008000;">#Up to 20150113#</span></strong>

<strong><em>v0.40</em></strong>

Major Mods：
<ol>
	<li><strong>加入对RIS格式记录的解析与支持，重写了solve_enw.php核心函数，加入对RIS标志字段识别与解析，默认存储格式取决于输入格式（RIS--&gt;RIS,enw--&gt;enw）</strong></li>
</ol>
<strong><span style="color: #008000;">#Up to 20150321#</span></strong>

<strong><em>v0.41</em></strong>

Minor Mods：
<ol>
	<li><strong>加入对online但未定vol/number/page文章的命名考虑，规则：
</strong></li>
</ol>
$author, $journal, strrev($year0)首字母ASCII码决定。范例：
<pre>Huang-GCB-2015-fv72_fn71_fp53.pdf</pre>
<strong><span style="color: #008000;">#Up to 20150402#</span></strong>

<strong><em>v0.42</em></strong>

Minor Mods：
<ol>
	<li><strong>BUG FIX: 修正了对RIS结尾标志符的判断问题</strong></li>
</ol>
<strong><span style="color: #008000;">#Up to 20150403#</span></strong>

<strong><em>v0.43</em></strong>

Minor Mods：
<ol>
	<li><strong>BUG FIX: 修正了对RIS某类期刊关键词标志符的判断问题</strong></li>
</ol>
<strong><span style="color: #008000;">#Up to 20150426#</span></strong>

<strong><em>v0.44</em></strong>

Minor Mods：
<ol>
	<li><strong>BUG FIX: 修正了对Nature子刊ris中对short term解析的问题
</strong></li>
</ol>
<strong><span style="color: #008000;">#Up to 20150519#</span></strong>

<strong><em>v0.50</em></strong>

要写文章，paperhub要更舒服才有动力！两天时间做了几处大改动。

Major Mods：
<ol>
	<li><strong>增加了对ris的参考文献格式生成</strong></li>
	<li><strong>增加了对多行记录的参考文件格式生成</strong></li>
	<li><strong>修改打包算法，按修改时间排序，直接在warehouse中选择操作，减少了record额外记录空间，并且能够精确定位文章</strong></li>
	<li><strong>增加warehouse下僵尸记录检测删除，每次打开index.php自动检测</strong></li>
</ol>
<strong><span style="color: #008000;">#Up to 20150714#</span></strong>

<strong><em>v0.51</em></strong>

Minor Mods：
<ol>
	<li><strong>BUG FIX: 修正了对upload_page.php 中对record尸体目录的操作
</strong></li>
	<li><strong>功能扩展：集中打包页面更改为管理页面，增加记录删除功能，列表增加&lt;a&gt;标签指向warehouse文献pdf</strong></li>
</ol>
<strong><span style="color: #008000;">#Up to 20150728#</span></strong>

<strong><em>v0.52</em></strong>

Minor Mods：
<ol>
	<li><strong>功能扩展：jc格式参考文献行内引用，ref_line，缩写完善；结果列表化
</strong></li>
	<li><strong>修改label传递为post方法</strong></li>
</ol>
<strong><span style="color: #008000;">#Up to 20150919#</span></strong>
