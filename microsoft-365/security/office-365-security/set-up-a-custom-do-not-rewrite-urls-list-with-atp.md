---
title: ATP 안전한 링크를 사용하여 사용자 지정 문서 다시 작성 방지 URL 목록 설정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 ATP 안전한 링크 정책에서 사용자 그룹에 대한 사용자 지정 차단URL 및 재작성 안 함 URL 목록을 설정방법을 알아봅니다.
ms.openlocfilehash: 9ec9c92e038aee33c716405916df009e3f4c60c5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825236"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a>ATP 안전한 링크를 사용하여 사용자 지정 문서 다시 작성 방지 URL 목록 설정

> [!IMPORTANT]
> 이 문서는 [Office 365 Advanced Threat Protection](office-365-atp.md)이 있는 비즈니스 고객을 대상으로 합니다. Outlook의 안전한 링크에 대한 정보를 찾고 있는 홈 사용자는 고급 [연결 Outlook.com 감사를 참조하세요.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

[Office 365 ATP(Advanced Threat Protection)를](office-365-atp.md) 사용하는 경우, 조직에서 사용자의 전자 메일 메시지나 특정 Office 문서에서 웹 주소(URL)를 클릭할 때 사용자가 해당 URL로 이동할 수 없는 등의 차단된 URL을 사용할 수 있습니다. [custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md) 또한 조직의 특정 그룹에 대해 사용자 지정 "재작성 안 함"목록을 포함할 수도 있습니다. "다시 쓰지 않음" 목록을 사용하면 일부 사용자가 [Office 365에서 ATP 안전한 링크를 통해 차단한 URL을 방문할 수 있습니다.](atp-safe-links.md)

이 문서에서는 ATP 안전한 링크 검사에서 제외되는 URL 목록 및 고려해야 할 몇 가지 중요한 사항을 명시합니다.

> [!NOTE]
> 조직에서 안전 링크 정책을 사용하는 경우 타사 피싱 테스트에 "재작성 안 함" 목록만 지원됩니다.

## <a name="set-up-a-do-not-rewrite-list"></a>"재작성 안 함" 목록 설정

ATP 안전한 링크 보호는 조직의 차단된 URL 목록과 예외를 위해 "재쓰지 않음" 목록 등의 여러 목록을 사용합니다. 필요한 권한이 있는 경우 사용자 지정 "다시 쓰지 않습니다"라는 목록을 설정할 수 있습니다. 이는 조직의 특정 받는 사람에게 적용되는 안전 링크 정책을 추가하거나 편집할 때 수행합니다.

ATP 정책을 편집하거나 정의하려면 적절한 역할을 할당해야 합니다. 다음 표에 몇 가지 예제가 나와 있습니다. 자세한 내용은 보안 서비스 [및 준수 센터의 사용 & 참조하십시오.](permissions-in-the-security-and-compliance-center.md)

|역할|할당된 위치/방법|
|---|---|
|전역 관리자|기본적으로 Microsoft 365를 시작하기 위해 등록하는 사람은 전역 관리자입니다. [(자세한 내용은 Microsoft 365 관리자 역할](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 정보를 참조하세요.)|
|보안 관리자|Azure Active Directory 관리 [https://aad.portal.azure.com](https://aad.portal.azure.com) 센터()|
|Exchange Online 조직 관리|Exchange 관리 [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) 센터( <br>또는 <br>  PowerShell [cmdlet(Exchange Online PowerShell 참조)](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

> [!TIP]
> 역할 및 사용 권한에 대한 자세한 내용은 보안 [센터의 보안 그룹& 참조하세요.](permissions-in-the-security-and-compliance-center.md)

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>사용자 지정 "재작성 안 함" URL 목록을 보거나 편집하려면

1. 이동하여 [https://protection.office.com](https://protection.office.com) 회사 또는 학교 계정으로 로그인합니다.

2. 왼쪽 탐색 창에 **위협 관리 정책** \> **안전** 링크 \> **아래.**

3. 특정 받는 **사람에게 적용되는 정책** 섹션에서 새로 만들기(새 단추는 더하기 기호( )와 유사함)을 **New** **+** 선택하여 새 정책을 만듭니다. 또는 기존 정책을 편집할 수 있습니다.<br/>![새로 만들기 선택하여 특정 메일 받는 사람에 대한 안전 링크 정책 추가](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. 정책의 이름과 설명을 지정합니다.

5. 따라서 **ON** 사용자가 링크를 클릭할 때 알려진 악성 링크 목록과 관련하여 URL이 다시 작성되고 확인됩니다.

6. 다음 **URL을 다시 쓰지 않는 URL 섹션에서** 유효한 URL 입력 상자를 선택하고 **URL을** 입력한 후에 더하기 기호(+)를 선택합니다.

7. 적용 **대상 섹션에서** 받는 **사람이 구성원인지**확인한 다음 정책에 포함할 그룹을 선택합니다. **추가를**선택한 후 확인을 **선택합니다.**

8. When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.

> [!NOTE]
> 조직의 차단된 URL 목록을 검토해야 합니다. [ATP 안전한 링크를 사용하여 차단된 사용자 지정 URL 목록을 설정하는 방법을 참조하세요.](set-up-a-custom-blocked-urls-list-atp.md)

## <a name="important-points-to-keep-in-mind"></a>주의해야 할 중요 사항

- "다시 쓰지 않습니다"목록에 지정하는 URL은 지정된 받는 사람에 대한 ATP 안전한 링크 검사에서 제외됩니다.

- 사용자 환경을 개선하기 위해 일반적으로 사용되는 내부 URL을 "재작성 안 함" 목록에 추가하는 것이 좋습니다. 예를 들어 비즈니스용 Skype, Sharepoint 등의 온-프레미스 서비스가 있는 경우 목록에 해당 URL을 추가하여 검사에서 제외할 수 있습니다.

- "다시 쓰지 않는" 목록에 이미 URL 목록이 있는 경우 해당 목록을 검토하고 와일드카드를 적절히 추가해야 합니다. 예를 들어 기존 목록에 입력문자가 있고 정책에 하위 경로를 포함하려면 항목에 `https://contoso.com/a` `https://contoso.com/a/b` 와일드카드를 `https://contoso.com/a/*` 추가합니다.

- ATP 안전한 링크 정책에 "재작성 안 함" 목록을 지정할 때는 최대 3개의 와일드카드()를 포함할 수 \* 있습니다. 와일드카드에는 접두사 또는 하위 도메인이 명시적으로 포함됩니다. 예를 들어, 사용자가 지정한 도메인의 하위 도메인 및 경로를 방문할 `contoso.com` `*.contoso.com/*` 수 `*.contoso.com/*` 있도록 하므로 항목이 같지 않습니다.

다음 표에는 입력할 수 있는 항목과 입력 항목의 영향에 대한 예제가 나와 있습니다.

****

|예제 항목|속성 기능|
|---|---|
|`contoso.com`|받는 사람이 하위 도메인 또는 경로와 `https://contoso.com` 같은 사이트만 방문할 수 있습니다.|
|`*.contoso.com/*`|받는 사람이 , 또는 와 같은 도메인, 하위 도메인 및 경로를 `https://www.contoso.com` `https://www.contoso.com` 방문할 `https://maps.contoso.com` 수 `https://www.contoso.com/a` 있습니다. <br/><br/> 이 항목은 사기성이 있는 사이트가 포함되어 있거나 같지 않을 때보다 `*contoso.com*` 본질적으로 더 `https://www.falsecontoso.com` 좋습니다. `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|특정 받는 사람이 사이트(예: 하위 `https://contoso.com/a` 경로는 제외)를 방문할 수 있습니다. `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|특정 받는 사람이 사이트(예: `https://contoso.com/a``https://contoso.com/a/b`|
|
