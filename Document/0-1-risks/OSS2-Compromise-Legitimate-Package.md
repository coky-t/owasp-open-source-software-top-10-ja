## OSS-RISK-2 : 正規パッケージの侵害 (Compromise of Legitimate Package)

**説明:**

攻撃者は、たとえば、正規のプロジェクト管理者のアカウントをハイジャックしたり、パッケージリポジトリの脆弱性を悪用することで、既存の正規プロジェクトやディストリビューションインフラストラクチャの一部であるリソースを侵害して、コンポーネントに悪意のあるコードを注入する可能性があります。

悪意のあるコードはエンドユーザーシステム上や、依存するソフトウェアを開発や運用する組織に属するシステム (ビルドシステムや開発ワークステーションなど) 上で実行される可能性があります。システムおよびそのうえで処理や保存されるデータの機密性、完全性、可用性がリスクにさらされます。

**事例:**

1. [Event-stream](https://blog.npmjs.org/post/180565383195/details-about-the-event-stream-incident): 正規のコンポーネントに対するこの攻撃は Copay Bitcoin ウォレットのユーザーを標的としていました。
2. [SolarWinds Cyber-Attack](https://www.cisecurity.org/solarwinds)

**対応:**

侵害されたパッケージの取り込みを検出して防止するための単一の対策はありません。組織は Secure Supply Chain Consumption Framework (S2C2F) などの新しい標準やフレームワークを参考にして、考えられるセーフガードについて情報を得ます。個々のセキュリティ要件やリスク選好に応じて、選択と優先順位付けを行う必要があります。

対応例を以下に示します。
1. SLSA に従ってコンポーネントの来歴を検証します
2. ソース (自分自身または信頼できるサードパーティ) からコンポーネントをビルドします
3. 手動や自動でコードをレビューします
4. 安全な内部ストア (このようなバイナリリポジトリは自作バイナリをホストし、外部バイナリをミラーリングします) からすべてのコンポーネントを取得します

**参照:**

1. [Secure Supply Chain Consumption Framework](https://www.microsoft.com/en-us/securityengineering/opensource) (S2C2F)
2. [Risk Explorer for Software Supply Chains](https://riskexplorer.endorlabs.com/) Subvert Legitimate Package (AV-001)
3. [Supply chain Levels for Software Artifacts](https://slsa.dev/) (SLSA)
4. MITRE ATT&CK [T1195.001 Compromise Software Dependencies and Development Tools](https://attack.mitre.org/techniques/T1195/001/)
5. OWASP Top 10 CI-CD Security Risks [CICD-SEC-3: Dependency Chain Abuse](https://owasp.org/www-project-top-10-ci-cd-security-risks/CICD-SEC-03-Dependency-Chain-Abuse)
6. OWASP Software Component Versification Standard (SCVS) [V6 Pedigree and Provenance](https://owasp-scvs.gitbook.io/scvs/v6-pedigree-and-provenance)
