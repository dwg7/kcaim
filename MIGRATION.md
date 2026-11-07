# miso への移行表(段階5の準備)

状態: **草稿**。合意前。**何も切り替えていない。**名前の背景は `BRAND.md`、進め方は下の「順序」を参照。

## 命名の規則(案)

| 接頭辞 | 意味 | 扱い |
|---|---|---|
| `miso-*` | 単一の Markdown のインスタンス、およびその実装(旧 `kcaim-*`) | 移行の対象 |
| `kcai-*` | KCAI(共有地の踏み跡)のリポジトリ(例: `kcai-terrio`、`kcai-un-docs`、`kcai-survey-training`) | **変えない** |
| `kcai` | KCAI のコンセプトのリポジトリ | **変えない** |

kcaim への言及が見つかったリポジトリは、下の表のとおり。`kcai`、`kcai-terrio`、`kcai-un-docs` の README には、kcaim への言及がない(2026-11-07 に確認)。

## 方針: 遡らず、新陳代謝で塗り替える(hfu の方針案。2026-11-07。まだ決定ではない)

- **遡って直さない。**既存のものは、名前を変えない(リポジトリ、ファイル名、キー、URL、クエリパラメータ、スクリプト)。リンクを切らず、他の担当に作業を強いない。
- **新しいものから miso にする。**新しいリポジトリ、ファイル、文書、機能は、miso(`miso-*`、`miso_format` など)を使う。
- **読むときは両方、書くときは新名。**ツールは、旧名と新名の両方を、**期限を決めずに**受理し、新しく作るものには新名を使う。
- **手を入れたときに、ついでに直す。**ファイルや機能を、実質的に改訂・置換するときに、新名にする。そのとき、旧名の案内(一行の記載、または薄いラッパー)を残す。
- **旧称を消さない。**README と CONCEPT.md の冒頭に、kcaim = miso と書いてある。古い成果物の見出しに「(現在の名前: miso)」の一行を足すのは、手を入れたときでよい。
- **混在の期間が長くなる**ので、旧名と新名が同じものを指すことを、この文書と README に保つ。
- **この方針で、決めなくてよくなるもの**: 同日の一斉の切り替え、例のファイル名の変更(universe の `EXTERNAL.md` のリンク)、Pages の公開 URL(kcaim-geo)、クエリパラメータ(kcaim-geo)、universe の `kcaim/` とキー、kcai-survey-training の変換の仕組み。
- **残る判断**: `dwg7/kcaim` リポジトリそのものの改名。GitHub が旧 URL を転送し、依存先がほぼ無い(実測)ので、**新陳代謝を待たずに行える**。行うか、旧名のまま新陳代謝に任せるか。

### 混在期間の運用(kcaim-geo の所見。2026-11-07。自己報告)

1. **指示の置き場所**: 新しい担当(エージェント)は、各リポジトリの AGENTS.md だけを読んで動くことが多い。そこに方針の一段落がないと、勝手に一斉置換するか、いつまでも直さないかに振れる。**貼れる標準の一段落**を、下に用意した。各リポジトリの AGENTS.md の編集は、**hfu の承認と、各担当の判断**による(こちらからは編集しない)。
2. **「ついでに直す」の範囲**: 名前の置換を、内容の変更と同じ差分に混ぜると、レビューしにくい。「ついで」は、**編集している行に限り**、できれば**別のコミット**にする。生成物(ビルド済みの JS など)の差分と混ぜない。
3. **「期限なしで両方受理」の検証**: 旧名の受理は、誰も使わなくなると黙って壊れる。「新旧の両方で動く」ことを、確認項目として一行残す(受け入れテスト、または起動時の確認。薄いラッパーも同様)。
4. **旧称の案内の置き場**: README の冒頭の一行(旧称 kcaim)。GitHub のリポジトリの説明やトピックにも、新旧の両方の語を置くと、検索で迷わない。
5. **新しいインターフェースの名前**: パラメータ名など、外から見える契約を新しく決めるときは、**ブランド名を含まない中立な名前**(例: `src`)が望ましい。名前を含めると、改称のたびに同じ移行を繰り返す。決めるのは hfu。
6. **外部 URL の利用の確認**: raw コンテンツや Pages の URL を、他の担当が使っていないかは、各担当に確認する。**実測(2026-11-07)**: `dwg7` 配下のコード検索で、`raw.githubusercontent.com/dwg7/kcaim` を含むファイルは 0 件。universe の作業ツリーに、`raw.githubusercontent.com/dwg7/kcaim` と `dwg7.github.io/kcaim` の記載は 0 件(`EXTERNAL.md` は、通常のウェブ URL)。

### AGENTS.md に貼れる標準の一段落(案)

> **名前について(miso)。**このプロジェクトの親にあたる方法の呼び名は miso(旧称 kcaim / KCAIM)で、同じものを指す。**既存の名前(リポジトリ、ファイル名、キー、URL、パラメータ、スクリプト)は、遡って変えない。**新しく作るものは、miso の名前を使う。ツールは、旧名と新名の**両方を受理**し、書くときは新名を使う。ファイルや機能を実質的に改訂するときは、**編集している行に限り**、名前を新名にしてよい(別のコミットにする)。一斉の置換はしない。判断が分かれるときは、hfu に確かめる。詳しくは、`dwg7/kcaim` の `MIGRATION.md` を参照。

以下の移行表は、「いつ変えるか」の目安ではなく、**何が旧名を持っているかの一覧**として読む。「時期」の列の「段階6」は、新陳代謝の方針では、「手を入れたとき」に読み替える。

## 移行表

| # | 対象 | 現在 | 移行後(案) | 担当 | 時期 | 備考 |
|---|---|---|---|---|---|---|
| 1 | GitHub リポジトリ | `dwg7/kcaim` | `dwg7/miso` | この作業(kcaim セッション) | 段階6 | `dwg7/miso` は未使用(404 を確認)。旧 URL は自動で転送される(下記) |
| 2 | リポジトリの説明文 | 「エンタープライズCopilotが持ち歩く業務宇宙 Markdown ファイルの概念」 | 「人とAIが、時間をかけて醸す知識。」 | この作業 | 段階5〜6(低リスク。単独で先に可) | topics は現在なし |
| 3 | 例のファイル名 | `examples/kcaim-sonshi.md`、`kcaim-bird-yezo.md` | `miso-sonshi.md`、`miso-bird-yezo.md` | この作業 | 段階6 | 本文中の自己参照も同時に置き換える |
| 4 | 例のファイル名(他の担当が作成) | `examples/kcaim-scala.md` | `miso-scala.md` | **要確認**(作成者) | 段階6 | 私が作ったものではない。作成者の了承を得る |
| 5 | 起動指示の一行プロンプト | 「添付の kcaim があなたの作業文脈です。…」 | 「添付の miso があなたの作業文脈です。…」 | この作業 | 段階5(先に可) | `examples/agent-contract-template.md`、`examples/kcaim-sonshi.md`。利用者が実際に打つ文なので、名前を合わせたほうが自然 |
| 6 | `dwg7/kcaim-geo` | リポジトリ名、`AGENTS.md`、`package.json`(+lock)、`README.md`、`DECISIONS.md`、`scripts/check_kcaim.py` | `dwg7/miso-geo`、`scripts/check_miso.py`、各文書の名称 | kcaim-geo のセッション | 各自の判断(段階6のあと) | 2026-11-07 に実測。`package.json` の名前の変更は、依存の確認が要る |
| 7 | `hfu/universe` | ディレクトリ `kcaim/`(3つのインスタンス)、front matter のキー `kcaim_format`、`README.md`、`EXTERNAL.md`、`CATALOG.md`、`AGENTS.md`、`DECISIONS.md`、`scripts/build_catalog.py`、`scripts/check_universe.py` | `miso/`、`miso_format`(移行期間は**両方を受理**) | universe のセッション | 各自の判断 | 検査器がキーの値を見ず、有無だけを見るため、移行は比較的軽い |
| 8 | `dwg7/kcai-survey-training`(private) | `scripts/kcai_to_kcaim/`(変換の仕組み。`sections/*.md`、`BRIEF.md`、`core.py`、`build.py`)、`scripts/kcaim_check.py`、`scripts/kcaim_roundtrip_check.py`、`README.md`、`DECISIONS.md`、`TODO.md` | `kcai_to_miso/`、`miso_check.py` など | 当該リポジトリのセッション(**未起動**) | 各自の判断 | **最も参照が多い**。kcai の踏み跡から、単一ファイルのインスタンスを生成する仕組みがある。生成物(契約文など)に名前が入る。名前を変えるなら、生成物の再生成が要る |
| 9 | `kcaim-actual-finland`(MS Copilot で作成。外部) | 名前、CONCEPT.md の草稿の写し、`/system-record/kcaim-concept-and-agent-contract` | 名前(案: `miso-actual-finland`)、写しの更新、`concept-version` の宣言 | **hfu** | 各自の判断 | 約6,000行の単一ファイル。写しは、更新しないと、ずれる |
| 10 | ローカルのディレクトリ | `/Users/hfu/kcaim`(と、その下の worktree) | **当面そのまま** | — | — | Claude のセッションのパスや、プロジェクトのメモリ(`~/.claude/projects/-Users-hfu-kcaim`)に影響する。リポジトリ名を変えても、ローカルの名前は変えなくてよい。変えるなら別途、慎重に |
| 11 | 各ローカルクローンの `origin` | `…/dwg7/kcaim` | `…/dwg7/miso` | 各クローンの持ち主 | 段階6のあと | 転送で動くが、更新するのがよい |
| 12 | 私のメモリ(この作業の) | `kcaim-direct-main-push.md`(対象を `dwg7/kcaim` と記す) | 対象を `dwg7/miso`(旧称 kcaim)に更新 | この作業 | 段階6 | 直接コミット・pushの許可の対象を正しく保つため |

## 現状(実測。2026-11-07)

- `dwg7/kcaim`: public。stars・forks・watchers 0、open issue 0。Webhook 0、Actions 0、`.github` なし、Pages なし、topics なし。
- 他のリポジトリから `dwg7/kcaim` への言及: `dwg7/kcai-survey-training`(private)の `README.md`、`DECISIONS.md`、`TODO.md` ほか。
- 本リポジトリ内の kcaim への言及: `CONCEPT.md`(冒頭と改訂履歴など)、`README.md`、`BRAND.md`、`examples/` の4ファイル。

## 転送(リダイレクト)の確認

- GitHub は、リポジトリ名を変更すると、旧 URL(Web、git の clone・fetch・push)を新しい名前へ転送する(GitHub の一般的な仕様)。**この移行では、まだ実際に確かめていない。**
- 切り替えの直後に確かめる項目: 旧 URL で Web ページが開く。旧 URL に対して `git ls-remote` が通る。旧 Issue のリンク(`…/dwg7/kcaim/issues/1`)が開く。
- 転送が切れる条件: 旧名(`kcaim`)で、新しいリポジトリを作る、または別のリポジトリを旧名へ移す。**旧名は、再利用しない。**
- 現状では、Webhook、Actions、Pages がないため、転送以外に壊れるものは、ほとんどない。

## 順序(段階6の案)

1. 各担当に照会し、**反対や懸念がない**ことを確かめる(下の「照会」)。
2. この移行表を、hfu が承認する。
3. このリポジトリを GitHub で `dwg7/miso` に改名する。ローカルの `origin` を更新する。
4. ファイル名と本文の置き換えを、**別のコミット**で行う(表の #3〜#5)。置き換えの前後で、参照切れを検査する。
5. 旧称を、README と CONCEPT.md の冒頭に、**恒久的に**残す。
6. ほかのリポジトリは、**各自の判断**で、自分の側を変える。移行期間は、旧名と新名の両方を受理する(キー名、スクリプト名など)。
7. 各ローカルクローンの `origin` を更新する(#11)。私のメモリを更新する(#12)。
8. **cafebabe に、切り替えが済んだことを知らせる**(cafebabe からの依頼。2026-11-07)。

止める条件: 反対や懸念が解けない、転送の確認が通らない、形式の議論が止まって名前が実態とずれる。

## 照会(各担当へ)

各担当には、次のことを、**自分の一次情報(リポジトリ、README、DECISIONS.md)で確かめて**、答えてもらう。編集・コミットは、しない。

1. あなたのリポジトリ・作業は、kcaim(KCAIM)に言及・依存しているか。どのファイルか。
2. 名前が miso に変わるとき、あなたの側で、変えるものと、その影響(生成物、検査器、キー、リンク)は何か。
3. 移行期間に、旧名と新名の両方を受理する必要があるものは何か。
4. 反対、または懸念はあるか。適切な時期は、いつか。

## ファイル名を変えるときの注意(universe の指摘から)

- **リポジトリ名の変更は、GitHub が旧 URL を転送するが、リポジトリ内の個々のファイル名の変更は、転送されない。**たとえば、`…/dwg7/kcaim/blob/main/examples/kcaim-sonshi.md` は、リポジトリ名の変更後は `…/dwg7/miso/blob/main/examples/kcaim-sonshi.md` に転送されるが、ファイルを `miso-sonshi.md` に変えると、**旧パスは 404 になる**。
- 既知の影響: `hfu/universe` の `EXTERNAL.md` が、`kcaim-sonshi`・`kcaim-bird-yezo` を、dwg7/kcaim の URL で指している。ほかに、利用者のブックマーク、貼り付けられたリンクがありうる。
- 選択肢:
  1. **既存の例のファイル名を、変えない**(歴史的な名前として残す)。新しい例から `miso-*` を使う。リンクは切れない。名前の不統一が残る。
  2. **リポジトリ名の変更と同じ日に、ファイル名も変え、既知の参照(universe の `EXTERNAL.md` など)を同時に直す。**未知のリンクは切れる。
  3. 旧名と新名の**両方のファイルを残す**(新名は本物、旧名は短い案内だけのファイル)。リンクが切れず、旧名で開いた人を新名へ案内できる。ファイルが増える。
- 私の推奨は、**1 または 3** です。例のファイルは、外部から参照されやすく、名前の統一より、リンクの安定のほうが価値が大きいと考えます。ただし、決めるのは hfu です。

## 命名の規則の補足(universe の確認への回答案)

- `miso-*` の接頭辞は、**単一の Markdown の、外部のインスタンスの名前**(リポジトリ名、`dwg7/miso` の `examples/` のファイル名)にだけ付ける案である。`hfu/universe` の id(ファイル名と一致。D-003)や、D-002(接頭辞を付けない)とは**衝突しない**。
- 「miso の universe」という言い方は、避けるのがよい。universe は「公開できる miso(旧 kcaim)のインスタンスを集めた目録」で、別の層の名前である(universe の名前は変えない)。
- D-010(説明文は、略語を避け、何をするものかで書く)は、README の一行「人とAIが、時間をかけて醸す知識。」が、何をするものかを書いているので満たす。miso は固有名で、略語(由来の一行)は、名前のあとに添えるだけにしている。

## 決めてほしいこと(hfu)

1. 命名の規則(`miso-*`、`kcai-*` は変えない)でよいか。
2. 例のファイル名(#3)でよいか。`kcaim-scala.md`(#4)は、作成者の了承を得てから。
3. 説明文の更新(#2)を、段階6を待たずに、先に行ってよいか。
4. 起動指示の一行プロンプト(#5)を、先に miso に直してよいか。
5. ローカルのディレクトリ(#10)は、当面そのままでよいか。
6. 例のファイル名(#3): 新陳代謝の方針では、**変えない(選択肢1)**。この方針でよいか。
7. universe の、ディレクトリ `kcaim/` とキー `kcaim_format`: 新陳代謝の方針では、**変えない**。新しいインスタンスだけ、新名(`miso_format`)を使うか。検査器は両方を受理する。
8. 同日の一斉の切り替え: 新陳代謝の方針では、**行わない**。
9. **`dwg7/kcaim` リポジトリそのものの改名**を、新陳代謝を待たずに行うか(転送があり、依存先はほぼ無い)。行うなら、`kcai-survey-training` の参照と、universe の `EXTERNAL.md` の URL を、あとから直せば足りる。
10. **命名の規則の対象**: kcaim-geo の指摘(道具+複数ファイルの見本は、単一インスタンスではない)を受けて、`miso-*` を、「miso の方法を使うリポジトリ・インスタンス(単一でも複数ファイルでも)」に広げるか。新陳代謝の方針では、kcaim-geo の改名は急がないので、今決めなくてもよい。

## 照会の記録(2026-11-07。回答は各セッションの自己報告)

| 宛先 | 状態 | 回答の要点 |
|---|---|---|
| bvmap-koicha(`dwg7/bvmap-koicha`) | 回答あり | **該当なし。**リポジトリ内(コード、README、CLAUDE.md、DECISIONS.md、docs/、style/、build/ ほか)とコミットメッセージを検索し、kcaim / KCAIM / kcai への言及・依存は 0 件。miso という語もない。変えるものも、影響もない。**反対・懸念なし。**時期は、kcaim 側の都合でよい。(参考: こちらは名前を濃茶の比喩で統一しており、miso の発酵食の比喩と混ざらないよう、文書では茶に統一する方針。内部の規則で、反対ではない) |
| snow-hokkaido(`dwg7/snow-hokkaido`) | 回答あり | **該当なし。**main、作業ブランチ、日次運用の実行用チェックアウトの追跡ファイル全体(コード、docs、Justfile、scripts、テスト、設定)を、kcaim・kcai で検索し(大文字小文字は区別しない)、言及・依存はない(データ類 ledger/publish/logs は対象外で、公開リポジトリに含まれない)。変えるものも、影響もない。**反対・懸念なし。**時期の制約もない |
| cafebabe | 回答あり | **該当なし。**追跡ファイル全体(PROJECTS.md、CLAUDE.md、patterns/、DECISIONS.md を含む)を、kcaim・kcai・miso の語で検索し、0 件。MD運用のパターンも kcaim を前提にしていない。変えるものはない。**反対・懸念なし。**時期の制約もない。**依頼: 段階6の切り替えが済んだら、一言知らせてほしい**(kcai 系のリポジトリを PROJECTS.md に登録するとき、切り替え後の名前で書くため) |
| kcaim-geo(`dwg7/kcaim-geo`) | 回答あり | **名前そのものへの反対なし。**懸念は3点。**実測は正しいが、不足があった**: `site/viewer.js`(14箇所。URL のクエリパラメータ名 `kcaim-geo`、計測用の mark 名 `kcaim-text-rendered` など)、`site/viewer.html`・`docs/viewer.html` の title、`docs/assets/viewer-*.js`(ビルド済みの生成物)、`vite.config.js` のコメント、`package.json` の name と lock の2箇所、`scripts/check_kcaim.py`(参照は AGENTS.md・README・DECISIONS に計6箇所)、親プロジェクトへの言及(AGENTS.md・README)、**公開 URL にリポジトリ名が入っている**(README の2リンクと DECISIONS D12 の `https://dwg7.github.io/kcaim-geo/…`、カスタムドメインの `dwg7.unopengis.org/kcaim-geo/`)。CI の設定、`docs/examples` の md には kcaim の語がない。**懸念**: ①**命名規則**: 「`miso-*` は単一 Markdown のインスタンス」を kcaim-geo に当てはめると合わない。kcaim-geo は、ビューア、検査器、複数ファイルの md を持つ道具+見本で、`miso-geo` と改名すると単一インスタンスと誤読される。規則の対象を広げるか、別の呼び名が要る。②**公開 URL**: プロジェクト Pages のパスはリポジトリ名なので、改名すると `…/kcaim-geo/` の URL が変わる。旧パスの転送は、確認していないし、期待もしない。③**順序**: リポジトリ名の変更は**最後**にする。ビューアの新旧パラメータの受理、文書の miso 表記、検査器の改名(旧名のラッパー付き)を先に行う。**本当の外部インターフェース**は、クエリパラメータ `kcaim-geo`(新旧の両方を受理する。例: `get('miso-geo') ?? get('kcaim-geo')`。新しい名前の決定は hfu)。mark 名と package.json の name は、いつ変えてもよい。**時期**: PR #5(ピンの名前の表示)が未マージなので、それが片付いてから。作業は kcaim-geo の PR として行う想定で、hfu の指示を待つ。この回答は、改称の承認の根拠にはならない |
| universe(`hfu/universe`) | 回答あり | **反対なし。懸念は2点。**実測は、ほぼ正しい(kcaim の語を含むファイルは一致。件数は、`kcaim/ipa-josh.md` が57、`hokkaido-small-towns.md` が27、`hokkaido.md` が12、`check_universe.py` が8、ほか)。**補足**: ①`kcaim_format: 0-draft` は3ファイルすべての front matter にあり、検査器の必須キー(10個)に入っている。②ディレクトリ名 `kcaim/` は、`check_universe.py` と `build_catalog.py` に**ハードコード**されている。`CATALOG.md` の各行のリンクも `kcaim/<id>.md` で、改名すると切れる。③`EXTERNAL.md` は、外部の `kcaim-sonshi`・`kcaim-bird-yezo` を、dwg7/kcaim の URL で指す手保守の表。**dwg7/kcaim 側のファイル名を `miso-*` に変えると、この2行が切れる**。④`DECISIONS.md` の D-002(kcaim は `kcaim/` 直下にフラット)の変更にあたる。D-010(リポジトリの description は略語を避け、何をするものかで書く)も関係する。`.github/workflows/check.yml` には kcaim の語はない。**変えるもの**: `kcaim/`(スクリプト2本と CATALOG のリンク)、キー `kcaim_format`(3ファイルと検査器)、README・AGENTS・EXTERNAL・DECISIONS の本文、各 kcaim 本文中の自己言及(約100件)。**ディレクトリとキーを変えるかは、universe が決めることではなく hfu の決定**。変えるなら、DECISIONS.md に新しい決定を足し、D-002 を置き換える。**意見**: キー名は機械が読むので、表示名と切り離す(`kcaim_format` を旧称のまま残す)ほうが安全かもしれない。**移行期間の併用**: 検査器は `kcaim_format` と `miso_format` の両方を受理、ディレクトリも `kcaim/` と `miso/` の両方を走査、目録生成は実際にあるディレクトリ名でリンクを出す、`EXTERNAL.md` は旧・新の URL を併記。**気づいたこと**: ①外来の hokkaido.md は、改称時にキーを誰が直すかを決める必要がある。②`universe` は、公開できる kcaim を集めた目録の名前で、miso とは別の層。「miso の universe」という言い方が、語の関係を曖昧にしないか確認したい。③id はファイル名と一致させる規則なので、`miso-*` 接頭辞は D-002(接頭辞を付けない)と衝突する。**単一 Markdown の外部インスタンスにだけ付ける案、という理解でよいか確認したい**。**時期**: dwg7/kcaim の切り替え(段階6)と、universe 側を、**同じ日に揃える**のが安全。universe 側の変更は、hfu の指示があるまでしない。 |
| kcai-survey-training(private) | セッション停止中。未送信 | 参照が最も多い(#8)。優先して照会したい |
