---

copyright:
  years: 2014, 2018
lastupdated: "2018-08-01"

---
{:new_window: target="_blank"}

# スナップショット

スナップショットは、{{site.data.keyword.filestorage_full}} の機能です。 スナップショットは、特定の時点のボリュームの内容を表します。 スナップショットにより、パフォーマンスに影響を与えることなく、スペースの使用量を最小限に抑えながらデータを保護できます。スナップショットは、データ保護のための第一線の防御と見なされます。 ユーザーが、ボリュームにある重要なデータを誤って変更したり、削除したりした場合でも、データをスナップショット・コピーから容易に、しかも迅速にリストアすることができます。

{{site.data.keyword.filestorage_short}}には、スナップショットを取得する方法が 2 つあります。

– 1 つ目は、ストレージ・ボリュームごとにスナップショット・コピーを自動的に作成、削除する構成可能なスナップショット・スケジュールを使用する方法です。 追加のスナップショット・スケジュールを作成したり、手動でコピーを削除したり、要件に応じてスケジュールを管理したりすることもできます。 
- 2 つ目は、手動でスナップショットを取得する方法です。

スナップショット・コピーとは、特定の時点のボリュームの状態をキャプチャーした、{{site.data.keyword.filestorage_short}}・ボリュームの読み取り専用イメージです。 スナップショット・コピーは、作成に要する時間とストレージ・スペースの両方の面で効率的です。 {{site.data.keyword.filestorage_short}}・スナップショット・コピーの作成には数秒しかかかりません。 ボリュームのサイズやストレージのアクティビティーのレベルに関係なく、通常 1 秒未満です。 スナップショット・コピーが作成された後、データ・オブジェクトに対する変更は、スナップショット・コピーが存在しないかのように、オブジェクトの現行バージョンに対する更新として反映されます。 この間は、データのコピーは安定したままです。 

スナップショットをコピーしてもパフォーマンスは低下しません。 ユーザーは、{{site.data.keyword.filestorage_short}}・ボリュームごとにスケジュールによるスナップショット 50 個と手動スナップショット 50 個までを簡単に保管できます。これらはすべて読み取り専用のオンライン・バージョンのデータとしてアクセス可能です。

スナップショットにより、以下が可能になります。 

- 中断せずにポイント・イン・タイム・リカバリー・ポイントを作成できます。
- ボリュームを過去の特定の時点に戻せます。

スナップショットを取得するためには、その前にまずそのボリューム用に一定量のスナップショット・スペースを購入する必要があります。 スナップショット・スペースは、最初の注文時に追加することも、後で**「ボリュームの詳細」**ページから追加することもできます。 スケジュールされたスナップショットと手動スナップショットは同じスナップショット・スペースを使用するので、十分のスナップショット・スペースを注文してください。 詳細およびガイダンスについては、[スナップショットの注文](ordering-snapshots.html)の記事を参照してください。

**スナップショットのベスト・プラクティス**

スナップショットの設計は、お客様の環境によって異なります。 以下の設計上の考慮事項は、スナップショット・コピーを計画および実装するために役立ちます。 
- 各ボリュームまたは LUN について、最大 50 個のスナップショットをスケジュールによって作成でき、最大 50 個を手動で作成できます。 
- スナップしすぎないように注意してください。 時間単位、日単位、または週単位のスナップショットをスケジュールすることで、スケジュールされたスナップショットの頻度が、RTO および RPO のニーズと、アプリケーションのビジネス要件を満たすようにします。 
- ストレージ消費量の増加を制御するために、スナップショット自動削除機能を使用できます。 <br/>
  >**注** - 自動削除のしきい値は 95% に固定されています。
    
スナップショットは、実際のオフサイト災害復旧レプリケーションや長期保存用バックアップの代わりにはなりません。
    
**スナップショットがディスク・スペースに与える影響**

スナップショット・コピーは、ファイル全体ではなく個々のブロックを保存することでディスク使用量を最小化します。 スナップショット・コピーは、アクティブ・ファイル・システム内のファイルが変更または削除された場合にのみ、追加のスペースを使用します。 この場合、オリジナルのファイル・ブロックはまだ 1 つ以上のスナップショット・コピーの中に保存されています。
アクティブ・ファイル・システム内では、変更されたブロックが、ディスク上の別の場所に再書き込みされたり、アクティブ・ファイル・ブロックとして完全に削除されたりします。 その結果、変更されたアクティブ・ファイル・システム内のブロックに使用されているディスク・スペースに加えて、元のブロックに使用されているディスク・スペースも、変更前のアクティブ・ファイル・システムの状況を表すために保持されます。

<table>
    <colgroup>
      <col style="width: 33.3%;"/>
      <col style="width: 33.3%;"/>
      <col style="width: 33.3%;"/>
    </colgroup>
      <tr>
        <th colspan="3" style="border: 0.0px;text-align: center;">スナップショット・コピーの前および後のディスク・スペース使用量</th>
     </tr>
     <tr>
        <td style="border: 0.0px;text-align: center;"><img src="/images/bfcircle1.png" alt="スナップショット・コピーの前"></td>
        <td style="border: 0.0px;text-align: center;"><img src="/images/bfcircle3.png" alt="スナップショット・コピーの後"></td>
        <td style="border: 0.0px;text-align: center;"><img src="/images/bfcircle2.png" alt="スナップショット・コピーの後の変更"></td>
     </tr>
     <tr>
        <td style="border: 0.0px;">スナップショット・コピーが作成される前は、アクティブ・ファイル・システムだけがディスク・スペースを使用しています。</td>
        <td style="border: 0.0px;">スナップショット・コピーが作成された後は、アクティブ・ファイル・システムとスナップショット・コピーが同じディスク・ブロックを指しています。 スナップショット・コピーは追加のディスク・スペースを使用しません。</td>
        <td style="border: 0.0px;"><i>myfile.txt</i> がアクティブ・ファイル・システムから削除された後、スナップショット・コピーにはまだそのファイルが含まれていて、そのディスク・ブロックを参照しています。 このため、アクティブ・ファイル・システム・データを削除しても、必ずしもディスク・スペースが解放されるわけではありません。</td>
      </tr>
</table>

スナップショット・スペースの使用量を表示するには、[スナップショットの管理](working-with-snapshots.html)という記事の説明に従ってください。
