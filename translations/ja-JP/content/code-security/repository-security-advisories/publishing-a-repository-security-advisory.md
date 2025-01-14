---
title: リポジトリ セキュリティ アドバイザリの公開
intro: プロジェクト内のセキュリティ脆弱性についてコミュニティにアラートするため、セキュリティアドバイザリを公開できます。
redirect_from:
- /articles/publishing-a-maintainer-security-advisory
- /github/managing-security-vulnerabilities/publishing-a-maintainer-security-advisory
- /github/managing-security-vulnerabilities/publishing-a-security-advisory
- /code-security/security-advisories/publishing-a-security-advisory
versions:
  fpt: '*'
  ghec: '*'
type: how_to
topics:
- Security advisories
- Vulnerabilities
- CVEs
- Repositories
shortTitle: Publish repository advisories
ms.openlocfilehash: f3e3bfdb6b44ec1c86bb903c66271b854f4fb041
ms.sourcegitcommit: fcf3546b7cc208155fb8acdf68b81be28afc3d2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2022
ms.locfileid: "145119381"
---
<!--Marketing-LINK: From /features/security/software-supply-chain page "Publishing a security advisory".-->

セキュリティアドバイザリの管理者権限を持つユーザは、セキュリティアドバイザリを公開できます。

{% data reusables.security-advisory.repository-level-advisory-note %}

## 前提条件

セキュリティアドバイザリを公開したり、CVE の ID 番号をリクエストしたりする前に、セキュリティアドバイザリのドラフトを作成し、セキュリティの脆弱性の影響を受けるプロジェクトのバージョンに関する情報を提供する必要があります。 詳細については、「[リポジトリ セキュリティ アドバイザリの作成](/code-security/repository-security-advisories/creating-a-repository-security-advisory)」を参照してください。

セキュリティアドバイザリを作成したが、セキュリティの脆弱性が影響を与えるプロジェクトのバージョンに関する詳細をまだ入力していない場合は、セキュリティアドバイザリを編集できます。 詳細については、「[リポジトリ セキュリティ アドバイザリの編集](/code-security/repository-security-advisories/editing-a-repository-security-advisory)」を参照してください。

## セキュリティアドバイザリの公開について

セキュリティアドバイザリを公開すると、セキュリティアドバイザリが指定するセキュリティの脆弱性についてコミュニティに通知します。 セキュリティアドバイザリを公開すると、コミュニティがパッケージの依存関係を更新し、セキュリティの脆弱性の影響を調査しやすくなります。

{% data reusables.repositories.security-advisories-republishing %}

セキュリティアドバイザリを公開する前に、一時的なプライベートフォークで、脆弱性を修正するため非公式でコラボレートできます。 詳細については、「[一時的なプライベート フォークで、リポジトリのセキュリティ脆弱性を解決するためにコラボレートする](/code-security/repository-security-advisories/collaborating-in-a-temporary-private-fork-to-resolve-a-repository-security-vulnerability)」を参照してください。

{% warning %}

**警告**: 可能な限り、アドバイザリを公開する前に、セキュリティ アドバイザリに修正バージョンを追加する必要があります。 そうしない場合、アドバイザリは修正バージョンなしで公開され、{% data variables.product.prodname_dependabot %} は、更新する安全なバージョンを提供することなく、問題についてユーザに警告します。

このような状況では、次のステップを行うことをお勧めします。

- 修正バージョンが利用可能な場合、可能であれば、修正の準備ができたときに問題を開示するのを待ちます。
- 修正バージョンが開発中でまだ利用できない場合は、アドバイザリにその旨を記載し、公開後にアドバイザリを編集します。
- 問題を修正する予定がない場合は、ユーザが修正時期を問い合わせることがないよう、アドバイザリに明示します。 この場合、ユーザが問題を軽減するときに使えるステップを含めると便利です。

{% endwarning %}

パブリックリポジトリからドラフトアドバイザリを公開すると、すべてのユーザが次のことを確認できます。

- アドバイザリデータの現在のバージョン。
- クレジットされたユーザが受け入れたアドバイザリクレジット。
  
{% note %}

**注**: 一般ユーザーは、アドバイザリの編集履歴にアクセスすることはできず、公開されたバージョンのみを見ることができます。

{% endnote %}

セキュリティアドバイザリの URL は、セキュリティアドバイザリの公開後も公開前と同じままです。 リポジトリへの読み取りアクセス権を持つユーザは、セキュリティアドバイザリを閲覧することができます。 セキュリティアドバイザリのコラボレータは、管理者権限を持つユーザがコラボレータをセキュリティアドバイザリから削除しない限り、セキュリティアドバイザリでコメントストリーム全体を含む過去の会話を引き続き表示できます。 

公開したセキュリティアドバイザリの情報をアップデートまたは修正する必要がある場合は、セキュリティアドバイザリを編集できます。 詳細については、「[リポジトリ セキュリティ アドバイザリの編集](/code-security/repository-security-advisories/editing-a-repository-security-advisory)」を参照してください。

## セキュリティアドバイザリを公開する

セキュリティアドバイザリを公開すると、セキュリティアドバイザリの一時的なプライベートフォークが削除されます。

{% data reusables.repositories.navigate-to-repo %} {% data reusables.repositories.sidebar-security %} {% data reusables.repositories.sidebar-advisories %}
4. [Security Advisories] のリストから、公開するセキュリティアドバイザリをクリックします。
  ![リスト内のセキュリティ アドバイザリ](/assets/images/help/security/security-advisory-in-list.png)
5. ページの下部にある **[アドバイザリの公開]** をクリックします。
  ![[アドバイザリの公開] ボタン](/assets/images/help/security/publish-advisory-button.png)
  
## 公開されたセキュリティアドバイザリの {% data variables.product.prodname_dependabot_alerts %}

{% data reusables.repositories.github-reviews-security-advisories %}

## CVE 識別番号をリクエストする (省略可能)

{% data reusables.repositories.request-security-advisory-cve-id %} 詳細については、「[リポジトリの {% data variables.product.prodname_security_advisories %} について](/code-security/repository-security-advisories/about-github-security-advisories-for-repositories#cve-identification-numbers)」を参照してください。

{% data reusables.repositories.navigate-to-repo %} {% data reusables.repositories.sidebar-security %} {% data reusables.repositories.sidebar-advisories %}
4. [Security Advisories] のリストから、CVE 識別番号をリクエストするセキュリティアドバイザリをクリックします。
  ![リスト内のセキュリティ アドバイザリ](/assets/images/help/security/security-advisory-in-list.png)
5. **[アドバイザリの公開]** ドロップダウン メニューを使用して、 **[CVE の要求]** をクリックします。
  ![ドロップダウンの [CVE の要求]](/assets/images/help/security/security-advisory-drop-down-request-cve.png)
6. **[CVE の要求]** をクリックします。
  ![[CVE の要求] ボタン](/assets/images/help/security/security-advisory-request-cve-button.png)

## 参考資料

- 「[リポジトリ セキュリティ アドバイザリの撤回](/code-security/repository-security-advisories/withdrawing-a-repository-security-advisory)」
