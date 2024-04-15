## OSS-RISK-9 : 未承認の変更 (変異) (Unapproved Change (Mutable))

**説明:**

コンポーネントは開発者がそのような変更に気付いたり、レビューしたり、承認することができないまま、変更される可能性があります。たとえば、ダウンロードリンクがバージョン管理されていないリソースを指している、バージョン管理されているリソースが安全でないデータ転送で改変や改竄されている、などの理由です。

異なる時点でダウンロードされた際に同一であることが保証されていないコンポーネントを使用することは、主にセキュリティ上のリスクになります。Codecov Bash Uploader などに対する攻撃は、ダウンロードされたスクリプトの完全性を事前にチェックせずに直接 bash にパイプするリスクを示しています。変異コンポーネントはソフトウェアビルドの安定性と再現性も脅かします。

**事例:**

1. CI/CD パイプラインにおけるバージョン管理されていないシェルスクリプトへの参照
    -  [Codecov bash uploader](https://about.codecov.io/security-update/) (2021)
2. コミット識別子のない Git リポジトリへの参照
3. パッケージレジストリへの安全でない HTTP リンク
    - [CVE-2021-26291](https://nvd.nist.gov/vuln/detail/CVE-2021-26291) in Apache Maven (2022)

**対応:**

1. 常に同じ不変のアーティファクトを指すことを保証する (あるいは少なくともある程度の保証がある) リソース識別子を使用します。
2. コンポーネントのダウンロード後、インストールや使用する前にダイジェストや署名を検証します。
3. MITM 攻撃を避けるために、接続や配布には安全なプロトコルを使用します。

**参照:**

1. SLSA [Immutable Reference](https://slsa.dev/spec/v0.1/requirements#immutable-reference)
2. [CWE-829: Inclusion of Functionality from Untrusted Control Sphere](https://cwe.mitre.org/data/definitions/829.html)
3. [CWE-830: Inclusion of Web Functionality from an Untrusted Source](https://cwe.mitre.org/data/definitions/830.html)
4. OWASP Top 10:2021 [A08:2021 - Software and Data Integrity Failures](https://owasp.org/Top10/A08_2021-Software_and_Data_Integrity_Failures/)
