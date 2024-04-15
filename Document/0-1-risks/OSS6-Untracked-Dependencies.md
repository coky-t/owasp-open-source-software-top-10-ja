## OSS-RISK-6 : 追跡されていない依存関係 (Untracked Dependencies)

**説明:**

プロジェクト開発者はコンポーネントへの依存関係を全く認識していない可能性があります。たとえば、アップストリームコンポーネントの SBOM の一部ではない、SCA ツールが実行されていないか検出されていない、依存関係がパッケージマネージャを使用して確立されていない、などの理由です。

誰も認識していないため、それぞれのコンポーネントに何か他の欠陥がないかチェックしたり監視することはできません。

**事例:**

1. アップストリームコンポーネントとして受け取ったり、SCA ツールによって生成された不完全な SBOM
2. 管理された (追跡された) 依存関係にサードパーティのコードの包含。例を以下に示します。
    - コードスニペット
    - ソースコードファイル (依存関係のソースにそのままコピーされ、"vendored" とも呼ばれます)
    - コンパイルされたコード (プラットフォーム固有のバイナリや、Java アーカイブ/クラスファイル、rebundling とも呼ばれます)
3. PIP や Maven などのパッケージマネージャのマニフェストファイルを通じて確立されていない依存関係。たとえば、brew や apt-get を通じて手動またはスクリプトでインストールしています。
4. IDE プラグイン、ビルドスクリプト、テスト依存関係、その他の開発者ツールは、依存ソフトウェア自体には含まれていませんが、依然としてセキュリティと運用上のリスクをもたらします。

**対応:**

1. 粗い粒度レベル (Maven や npm などのパッケージマネジメントツールの助けを借りて宣言された依存関係など) と細かい粒度レベル (「帯域外」つまりパッケージマネージャを使用せずに含まれる単一ファイルなどのアーティファクトなど) の両方で、正確な部品表を作成する機能に関して SCA ツールを評価及び比較します。

**参照:**

1. OWASP Software Component Versification Standard (SCVS) [V1 Inventory and V2 Software Bills of Materials](https://owasp-scvs.gitbook.io/scvs/v1-inventory)
2. rebundling の研究
    - Seth Larson: [Patching the libwebp vulnerability across the Python ecosystem](https://sethmlarson.dev/security-developer-in-residence-weekly-report-16) (2023)
    - J Rack, et al.: [Jack-in-the-box: An Empirical Study of JavaScript Bundling on the Web and its Security Implications](https://publications.cispa.saarland/4036/1/Bundlers_Study_Submission-camera-ready.pdf) (2023)
    - A Dann, et al.: [Identifying Challenges for OSS Vulnerability Scanners - A Study & Test Suite](https://www.bodden.de/pubs/dph+21identifying.pdf) (2021)
3. Anand Sawant: [Dependency Resolution in Python: Beware The Phantom Dependency](https://www.endorlabs.com/learn/dependency-resolution-in-python-beware-the-phantom-dependency) (2023)
