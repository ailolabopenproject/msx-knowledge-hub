## MSX Knowledge Hub

​「MSX Knowledge Hub」は、レトロコンピューター「MSX」の機種、ハードウェア部品、信頼できる情報源（ソース）、そしてそれらの関係性を体系的に管理するためのオープンなナレッジベースです。
​本プロジェクトの最大の特徴は、AIによる自動情報収集・構造化（Bot）と、人間による堅牢な目視レビュー（Human-in-the-Loop）の協働体制にあります。最新のWeb情報や資料からAIがデータを抽出してYAMLの「候補（Candidate）」を生成し、
GitHubのプルリクエストを通じて人間が最終チェックを行うことで、データの正確性とメンテナンス性を両立させています。
​AIのスピードと人間の知見を融合させ、失われゆくレトロPCの技術的遺産を美しく正確に未来へと残すためのプロジェクトです。

## MSX Knowledge Hub （English information）

​MSX Knowledge Hub is a structured, open knowledge base designed to systematically catalog MSX retro computers, hardware components, reliable information sources, and their interrelations.
​At its core, the project leverages a collaborative Human-in-the-Loop workflow: an AI-driven bot handles automated information gathering and YAML structuring, while human reviewers validate the data through GitHub pull requests.
This ensures high data accuracy while minimizing maintenance overhead.
​By combining the speed of AI with human oversight, MSX Knowledge Hub preserves the technical legacy of vintage computing for the future.


## 📁 Directory Structure (ディレクトリ構成)

本リポジトリは、厳格なスキーマ検証と安全なデータ運用のために以下の構造で管理されています。

- `schema/` : データの構造を定義するJSONスキーマ (`msxkb.schema.json`) を格納しています。すべてのデータはこの設計図に従います。
- `data/` : 人間のレビューを通過した**承認済みの本番データ**が格納されるディレクトリです（機種、部品、ソース、関係性別）。
- `candidate/` : AI（更新Bot）が自動収集・構造化し、**レビュー待ちの一時データ（候補）**を置くためのスペースです。

---

## 🔄 Workflow (データの追加とレビューの流れ)

「MSX Knowledge Hub」では、AIと人間が協力してデータ品質を保つワークフローを採用しています。

1. **情報収集 & 構造化 (Bot)**
   - AI（更新Bot）がMSX関連の資料やWikiから情報を抽出し、定義されたスキーマに沿ったYAML形式のデータを生成します。
2. **候補の提出 (Pull Request)**
   - 生成されたデータは `candidate/` フォルダ配下に一時ファイルとして配置され、GitHubのプルリクエスト（PR）として提出されます。
3. **最終チェック & 承認 (Human)**
   - 人間がPRの差分（Diff）を確認し、内容に誤りがなければマージを実行します。
4. **本番反映**
   - マージされたデータは自動的に本番データとして組み込まれ、ナレッジベースがアップデートされます。

---

## 🛠️ How to Contribute (データ追加の手順)

新しい機種や部品のデータを手動、またはAIを使って追加する場合は、以下の手順に従ってください。

1. `schema/msxkb.schema.json` の定義を確認する。
2. 対象のデータをYAML形式で記述し、`candidate/` ディレクトリ内に配置する。
3. プルリクエストを作成し、レビューを経て本番環境へマージする。
