# TargetRoasBiddingScheme [Non-BiddingStrategyService]
TargetRoasBiddingSchemeオブジェクトは、広告費用対効果の目標値の自動入札設定情報を表します。<br>
（BiddingStrategyService以外用のオブジェクトです。）

### Service
+ [AdGroupService](../../services/AdGroupService.md)

### Namespace
[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>get</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td colspan="8"><a href="BiddingScheme.md">BiddingScheme</a>(inherited)</td>
 </tr>
 <tr>
  <td>biddingStrategyType</td>
  <td>enum <a href="BiddingStrategyType.md">BiddingStrategyType</a></td>
  <td>自動入札タイプです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td colspan="8">TargetRoasBiddingScheme</td>
 </tr>
  <tr>
  <td>targetRoas</td>
  <td>xsd:double</td>
  <td>広告費用対効果の目標値です。<br>0.01 ～ 1000.00（1% ～ 100000%）の範囲内のみ 許容します。<br>※ROAS: Return On Advertising Spend</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>bidCeiling</td>
  <td>xsd:long</td>
  <td>入札価格の上限です。<br>※制限値：0 ～ 50000<br>※「0」が設定された場合、上限設定はありません。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>bidFloor</td>
  <td>xsd:double</td>
  <td>入札価格の下限です。<br>※ 設定を解除する場合は「0」を指定します。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
