# miso への移行表(段階5の準備)

状態: **草稿**。合意前。**何も切り替えていない。**名前の背景は `BRAND.md`、進め方は下の「順序」を参照。

## 命名の規則(案)

| 接頭辞 | 意味 | 扱い |
|---|---|---|
| `miso-*` | 単一の Markdown のインスタンス、およびその実装(旧 `kcaim-*`) | 移行の対象 |
| `kcai-*` | KCAI(共有地の踏み跡)のリポジトリ(例: `kcai-terrio`、`kcai-un-docs`、`kcai-survey-training`) | **変えない** |
| `kcai` | KCAI のコンセプトのリポジトリ | **変えない** |

kcaim への言及が見つかったリポジトリは、下の表のとおり。`kcai`、`kcai-terrio`、`kcai-un-docs` の README には、kcaim への言及がない(2026-11-07 に確認)。

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

## 決めてほしいこと(hfu)

1. 命名の規則(`miso-*`、`kcai-*` は変えない)でよいか。
2. 例のファイル名(#3)でよいか。`kcaim-scala.md`(#4)は、作成者の了承を得てから。
3. 説明文の更新(#2)を、段階6を待たずに、先に行ってよいか。
4. 起動指示の一行プロンプト(#5)を、先に miso に直してよいか。
5. ローカルのディレクトリ(#10)は、当面そのままでよいか。

## 照会の記録(2026-11-07。回答は各セッションの自己報告)

| 宛先 | 状態 | 回答の要点 |
|---|---|---|
| bvmap-koicha(`dwg7/bvmap-koicha`) | 回答あり | **該当なし。**リポジトリ内(コード、README、CLAUDE.md、DECISIONS.md、docs/、style/、build/ ほか)とコミットメッセージを検索し、kcaim / KCAIM / kcai への言及・依存は 0 件。miso という語もない。変えるものも、影響もない。**反対・懸念なし。**時期は、kcaim 側の都合でよい。(参考: こちらは名前を濃茶の比喩で統一しており、miso の発酵食の比喩と混ざらないよう、文書では茶に統一する方針。内部の規則で、反対ではない) |
| snow-hokkaido | 送信済み。回答待ち | |
| cafebabe | 回答あり | **該当なし。**追跡ファイル全体(PROJECTS.md、CLAUDE.md、patterns/、DECISIONS.md を含む)を、kcaim・kcai・miso の語で検索し、0 件。MD運用のパターンも kcaim を前提にしていない。変えるものはない。**反対・懸念なし。**時期の制約もない。**依頼: 段階6の切り替えが済んだら、一言知らせてほしい**(kcai 系のリポジトリを PROJECTS.md に登録するとき、切り替え後の名前で書くため) |
| kcaim-geo | セッション停止中。未送信 | 起こしていただければ、同じ照会を送る |
| universe | セッション停止中。未送信 | 同上 |
| kcai-survey-training(private) | セッション停止中。未送信 | 参照が最も多い(#8)。優先して照会したい |
