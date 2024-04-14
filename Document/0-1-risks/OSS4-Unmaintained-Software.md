## OSS-RISK-4 : メンテナンスされていないソフトウェア (Unmaintained software)

**説明:**

コンポーネントやコンポーネントバージョンは今後積極的に開発やサポートされない可能性があります。つまり、新機能やセキュリティバグに対するパッチが開発されない可能性があります。

そのため、パッチの開発は、影響を受けるコンポーネントに関する経験や知識が潜在的に少ないダウンストリーム開発者が行う必要があるかもしれません。

この結果、作業量が増大し、解決に要する時間が長くなる可能性があります。その間、継続的な露出を避けるために、システムへのアクセスや機能を制限する必要があるかもしれません。

**事例:**

1. [core-js](https://www.theregister.com/2020/03/26/corejs_maintainer_jailed_code_release) (npm, 2020)
2. [Gorilla Web Toolkit](https://www.chainguard.dev/unchained/a-tale-of-two-software-security-risks) (Go, 2022)
3. [minimist](https://twitter.com/ljharb/status/1579610392414007299?lang=en) (npm, 2022)

**対応:**

1. プロジェクトの活性と健全性の指標をチェックします。

    ただし、アクティビティが少ないことが成熟の証となる可能性もあることに注意してください。機能が完成し成熟したとみなされるプロジェクトは活発に開発が行われているプロジェクトよりもアクティビティが少なくなりますが、問題が発生した場合には依然としてタイムリーにパッチを受け取ることができます。

    指標の例:

    - 最近のイシューとコミットアクティビティはプロジェクトがアクティブであることを意味します。
    - 外部貢献者によってオープンされたイシューの比率が高いことはプロジェクトがアクティブであることを示しています。
    - 企業関連アカウントからのアクティビティはプロジェクトが信頼できる支援とサポートを得られることを示しています。
    - 信頼できるアカウントからのアクティビティはリポジトリが適切に維持されていることを示しています。
    - 頻繁にリリースされているリポジトリはコードベースのメンテナンスとサポートへのコミットメントを示しています。


2. プロジェクトのメンテナンスやサポート戦略に関する情報 (長期サポート (LTS) バージョンの有無や日付など) を検索します。

    Spring プロジェクトは [サポート期間](https://spring.io/projects/spring-boot#support) をドキュメント化している優れた事例です。
3. プロジェクトページをチェックして、アーカイブされているかどうか、プロジェクトのメンテナンスステータスに関する明示的な記述があるかどうかを確認します。

**参照:**

1. OWASP Top 10:2021 [A06:2021 - Vulnerable and Outdated Components](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)
2. [Bus factor](https://en.wikipedia.org/wiki/Bus_factor)
3. Common Weakness Enumeration (CWE) [CWE-1104: Use of Unmaintained Third Party Components](https://cwe.mitre.org/data/definitions/1104.html)
4. [CWE-1329: Reliance on Component That is Not Updateable](https://cwe.mitre.org/data/definitions/1329.html)
5. [Adoptoposs](https://github.com/adoptoposs/adoptoposs)
6. [Jazzband](https://jazzband.co/)
