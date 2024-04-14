## OSS-RISK-3 : 名前混乱攻撃 (Name Confusion Attacks)

**説明:**

攻撃者は正規のオープンソースやシステムのコンポーネントの名前に似た名前のコンポーネントを作成したり (typo-squatting)、信頼できる作成者を示唆したり (brand-jacking)、さまざまな言語やエコシステムで一般的な命名パターンを利用 (combo-squatting) する可能性があります。

悪意のあるコードはエンドユーザーシステム上や、依存するソフトウェアを開発や運用する組織に属するシステム (ビルドシステムや開発ワークステーションなど) 上で実行される可能性があります。システムおよびそのうえで処理や保存されるデータの機密性、完全性、可用性がリスクにさらされます。

**事例:**

1. [Colourama](https://bertusk.medium.com/cryptocurrency-clipboard-hijacker-discovered-in-pypi-repository-b66b8a534a8) (PyPI, 2018): 正規の Python パッケージ "colorama" に対するタイポスクワッティング攻撃により、ビットコインの送金を攻撃者の管理するウォレットにリダイレクトします。

**対応:**

コンポーネントをインストールや使用する前に:
1. コードの特定 (インストール前後のフック、エンコードされたペイロードなど) とプロジェクトの特性 (ソースコードリポジトリ、管理者アカウント、リリース頻度、ダウンストリームユーザーの数など) を主要なリスク指標でチェックします。

    一部のコンポーネントメタデータはパッケージリポジトリによって検証されていないため、攻撃者によって簡単に偽造される可能性があることに注意してください。

2. コンポーネントが信頼できる当事者からの署名を持っていることを検証します (署名をサポートや要求するエコシステムの場合)

**参照:**

1. [Secure Supply Chain Consumption Framework](https://www.microsoft.com/en-us/securityengineering/opensource) (S2C2F)
2. [Risk Explorer for Software Supply Chains](https://riskexplorer.endorlabs.com/) Create Name Confusion with Legitimate Package (AV-200)
3. [Supply chain Levels for Software Artifacts](https://slsa.dev/) (SLSA)
4. MITRE ATT&CK [T1195.001 Compromise Software Dependencies and Development Tools](https://attack.mitre.org/techniques/T1195/001/)
