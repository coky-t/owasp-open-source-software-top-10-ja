## OSS-RISK-1 : 依存関係における既知の脆弱性 (Known vulnerabilities in dependencies)

**説明:**

コンポーネントのバージョンには開発者が誤って導入した脆弱なコードが含まれている可能性があります。脆弱性の詳細は CVE、GitHub Security Advisories、その他の非公式なコミュニケーションチャネルなどを通じて、一般に公開されます。エクスプロイトやパッチは利用できることもできないこともあります。

脆弱性はダウンストリームソフトウェアのコンテキストで悪用される可能性があり、それぞれのシステムやそのデータの機密性、完全性、可用性を脅かしたり、ターゲット環境でラテラルムーブメントを可能にしたり、その他の悪影響を及ぼす可能性があります。

**事例:**

1. [CVE-2017-5638](https://cwiki.apache.org/confluence/display/WW/S2-045) Apache Struts で [Equifax データ侵害](https://en.wikipedia.org/wiki/2017_Equifax_data_breach) の原因となりました
2. [CVE-2021-44228](https://logging.apache.org/log4j/2.x/security.html#CVE-2021-44228) Apache Log4j で [Log4Shell](https://en.wikipedia.org/wiki/Log4Shell) とも呼ばれています

**対応:**

1. 既知の脆弱性がある (直接的および推移的) オープンソースの依存関係の存在がないか、アプリケーション、コンテナ、システムを監視します。
2. たとえば、以下に基づいて分析と緩和に優先順位を付けます。
    - [CVSS](https://www.first.org/cvss/) や [EPSS](https://www.first.org/epss/) などのスコアやメトリクス
    - エクスプロイトコードの可用性や成熟度などの脅威インテリジェンス、あるいは CISA [KEV カタログ](https://www.cisa.gov/known-exploited-vulnerabilities-catalog) で提供されるような、実際に観測された攻撃に関する情報
    - DAST および SAST ツールで、脆弱なコードが依存するソフトウェアのコンテキストで実行可能かどうかを判断します

**参照:**

1. OWASP Top 10:2021 [A06:2021 - Vulnerable and Outdated Components](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)
