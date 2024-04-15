---
layout: col-sidebar
title: OWASP Top 10 Risks for Open Source Software
level: 2
type: documentation
tags: top-10, open source, security, operations
pitch: Top-10 security and operational risks related to using OSS. 
---

![top 10 oss risks](https://raw.githubusercontent.com/OWASP/www-project-open-source-software-top-10/main/assets/images/top10.png)

## はじめに

ソフトウェアサプライチェーンにおいて OSS への依存度が高いにもかかわらず、業界には OSS のリスクを理解し測定するための一貫した方法がありません。OSS のリスクマネジメントはライセンスマネジメントから始まり、CVE へと進化してきましたが、セキュリティ、法律、運用の側面を包含する OSS リスクマネジメントへの総合的なアプローチが依然としてありません。このドキュメントで、業界の専門家やリーダーと協力して、まさにそれを作成できることに私たちは喚起しています。

OSS に依存してきた過去十年、既知の脆弱性が CVE として捕捉され、セキュリティの重要な指標として浮上してきました。既知の脆弱性は重要なシグナルですが、一般的には善意の開発者が犯した間違いを捕捉しています。これらの間違いは攻撃者に悪用される可能性があるため修正すべきですが、OSS への依存が含むリスクの全範囲を網羅しているわけではありません。

古いままのソフトウェアやメンテナンスされていないソフトウェアによってもたらされるようなものや、名前混乱攻撃などの次世代のサプライチェーン攻撃などの運用リスクは、CVE では捕捉できません。Synopsys が最近発表した [Open Source Security and Risk Analysis report](https://www.synopsys.com/content/dam/synopsys/sig-assets/reports/rep-ossra-2023.pdf) でハイライトしているように、これらのリスクは重大です。

- コードベースの 89% には 4 年以上古い OSS が含まれています
- コードベースの 91% には 2 年以上新しい開発が行われていないコンポーネントが含まれています

[The State of Dependency Management](https://endorlabs.webflow.io/learn/state-of-dependency-management) で、Endor Labs の Station 9 研究チームは、脆弱性の 95% が推移的依存関係 (開発者が選択して OSS によって自動的に取り込まれるソフトウェアパッケージ) に存在することを明らかにしました。そして、そのうちの多くは実際には到達できないか、アップデートされたとしても互換性がないという壊滅的な波及効果を引き起こすでしょう。20 人以上の CISO および CTO が査読と貢献を行ったこのリストで、チームは運用とセキュリティの両面でセキュリティチームと開発チームが備える必要がある主要なリスクを見つけ出そうとしました。

Top 10 OSS リスクは以下のとおりです。

- [OSS-RISK-1](./0-1-risks/OSS1-Known-Vulnerabilities.md) 既知の脆弱性 (Known Vulnerabilities): コンポーネントのバージョンには開発者が誤って導入した脆弱なコードが含まれている可能性があります。脆弱性の詳細は CVE、GitHub Security Advisories、その他の非公式なコミュニケーションチャネルなどを通じて、一般に公開されます。エクスプロイトやパッチは利用できることもできないこともあります。
- [OSS-RISK-2](./0-1-risks/OSS2-Compromise-Legitimate-Package.md) 正規パッケージの侵害 (Compromise of Legitimate Package): 攻撃者は、たとえば、正規のプロジェクト管理者のアカウントをハイジャックしたり、パッケージリポジトリの脆弱性を悪用することで、既存の正規プロジェクトやディストリビューションインフラストラクチャの一部であるリソースを侵害して、コンポーネントに悪意のあるコードを注入する可能性があります。
- [OSS-RISK-3](./0-1-risks/OSS3-Name-Confusion-Attack.md) 名前混乱攻撃 (Name Confusion Attacks): 攻撃者は正規のオープンソースやシステムのコンポーネントの名前に似た名前のコンポーネントを作成したり (typo-squatting)、信頼できる作成者を示唆したり (brand-jacking)、さまざまな言語やエコシステムで一般的な命名パターンを利用 (combo-squatting) する可能性があります。
- [OSS-RISK-4](./0-1-risks/OSS4-Unmaintained-Software.md) メンテナンスされていないソフトウェア (Unmaintained Software): コンポーネントやコンポーネントバージョンは今後積極的に開発されない可能性があります。そのため、機能的および非機能的なバグに対するパッチが元のオープンソースプロジェクトによってタイムリーに (またはまったく) 提供されない可能性があります。
- [OSS-RISK-5](./0-1-risks/OSS5-Outdated-Software.md) 古いままのソフトウェア (Outdated Software): プロジェクトは (新しいバージョンが存在しますが) 古いままのバージョンのコンポーネントを使用している可能性があります。
- [OSS-RISK-6](./0-1-risks/OSS6-Untracked-Dependencies.md) 追跡されていない依存関係 (Untracked Dependencies): プロジェクト開発者はコンポーネントへの依存関係を全く認識していない可能性があります。たとえば、アップストリームコンポーネントの SBOM の一部ではない、SCA ツールが実行されていないか検出されていない、依存関係がパッケージマネージャを使用して確立されていない、などの理由です。
- [OSS-RISK-7](./0-1-risks/OSS7-License-Regulatory-Risks.md) ライセンスのリスク (License Risk): コンポーネントやプロジェクトにはライセンスがまったくないことや、使用目的にそぐわないライセンスや、要件を満たしていないまたは満たすことができないライセンスである可能性があります。
- [OSS-RISK-8](./0-1-risks/OSS8-Immature-Software.md) 未成熟なソフトウェア (Immature Software): オープンソースプロジェクトは開発のベストプラクティスを適用していない可能性があります。たとえば、標準的なバージョニングスキームを使用していない、回帰テストスイート、レビューガイドライン、ドキュメントがないなどです。その結果、コンポーネントは信頼性や安全性が機能しない可能性があります。
- [OSS-RISK-9](./0-1-risks/OSS9-Unapproved-Change.md) 未承認の変更 (Unapproved Change): コンポーネントは開発者がそのような変更に気付いたり、レビューしたり、承認することができないまま、変更される可能性があります。たとえば、ダウンロードリンクがバージョン管理されていないリソースを指している、バージョン管理されているリソースが安全でないデータ転送で改変や改竄されている、などの理由です。
- [OSS-RISK-10](./0-1-risks/OSS10-UnderOversized-Dependency.md) 過小または過大な依存関係 (Under/over-sized Dependency): コンポーネントはほとんど機能がない (rpm マイクロパッケージなど) のこともあれば、多くの機能 (そのうち一部しか使用されないかもしれません) を提供することもあります。

## 著者および貢献者

![Authors](https://raw.githubusercontent.com/OWASP/www-project-open-source-software-top-10/main/assets/images/authors.png)

## 依存関係マネジメント入門

このようなリスクが私たちにどのような影響を及ぼすかをよりよく理解するために、簡単な例を使用して依存関係マネジメントの基本概念をいくつかさっと説明してみましょう。依存関係マネジメントに精通しているのであれば、このセクションはスキップしてください。

以下に表示されている依存関係グラフのルートノードは例のプロジェクトを表しています。ルートの子ノードはプロジェクトが「直接」依存する 9 つのオープンソースコンポーネントを表します。しかし、これらのコンポーネントは他のコンポーネントにも依存しており、トップレベルのプロジェクトから見るとそのすべてが「推移的」または「間接的」な依存関係になります。

直接の依存関係は、たとえば package.json (Node.js/npm) や pom.xml (Java/Maven) ファイルなどのマニフェストファイルでの宣言を通じて、プロジェクト開発者によって意識的に選択されます。パッケージマネージャはサードパーティのパッケージリポジトリから開発者のワークステーションや CI/CD システムに直接の依存関係のダウンロードとインストールを行います。その際、パッケージマネージャは推移的依存関係も特定し、潜在的なバージョンの競合を解決してローカルにインストールします。言い換えると、たくさんのコンポーネントを自動化された方法でダウンロードし、例のプロジェクト (およびその他) に必要なすべてのコードが開発者のマシンに存在することを確認します。

![Dependency Graph for Graph Maven Plugin](https://raw.githubusercontent.com/OWASP/www-project-open-source-software-top-10/main/assets/images/deptree.png)

この高度な自動化が今日のソフトウェア開発におけるオープンソースコンポーネントの再利用を後押ししました。その結果、現代のソフトウェアの大部分はあるアプリケーション向けに特別に開発されたものではなく、一般的なオープンソースプロジェクトから派生しています。依存関係グラフをもう一度見てみると、プロジェクト自体 (ルートノード) 向けに書かれたコードとオープンソースコンポーネントのコードの比率が 1:4 以下であることは驚くことではありません。また、IDE やビルドツールなどについても触れていません。
