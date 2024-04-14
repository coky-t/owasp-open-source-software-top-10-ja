## OSS-RISK-5 : 古いままのソフトウェア (Outdated software)

**説明:**

プロジェクトは (新しいバージョンが存在しますが) 古いままのバージョンのコンポーネントを使用している可能性があります。

依存関係の最新リリースから遅れすぎると、使用中のバージョンに脆弱性が明らかになった場合など、緊急事態においてタイムリーにアップデートを実行することが困難になる可能性があります。また、古いリリースは、特に脆弱性の影響を受けているかどうかといった、最新のバージョンと同じレベルのセキュリティ評価を受けられないかもしれません。新しいバージョンが使用中の現在のバージョンと構文的または意味的に互換性がない場合、アプリケーション開発者は非互換性を解決するために大幅なアップデートや移行作業が必要になるかもしれません。

**事例:**

1. [Spring Boot サポート期間](https://spring.io/projects/spring-boot#support)
2. Apache Tomcat に影響する脆弱性は ["8.0.x ブランチに対してチェックされず修正されないでしょう"](https://tomcat.apache.org/security-8.html)

**対応:**

1. 依存関係のアップデートを繰り返し行うバックログアイテムを作成します
2. アップデートの発見と提案を、たとえば、マージやプルリクエストを通じて、自動化します
3. 変更影響解析ツールを通じて導入や重大な変更を検出します

**参照:**

1. OWASP Top 10:2021 [A06:2021 - Vulnerable and Outdated Components](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)
2. 新しいバージョンが利用可能かどうかをチェックするツール:
    - [Versions Maven Plugin](https://www.mojohaus.org/versions/versions-maven-plugin/index.html)
3. 重大な変更を検出するツール:
    - [AexPy](https://github.com/StardustDL/aexpy)
