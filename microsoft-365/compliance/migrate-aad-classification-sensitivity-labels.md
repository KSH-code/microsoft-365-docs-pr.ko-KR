---
title: Azure Active Directory 그룹에 대한 분류 및 Microsoft 365 레이블 지정
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
description: 이 문서에서는 분류 및 Azure Active Directory 레이블에 대한 클래식 설명을 제공합니다.
ms.openlocfilehash: 0a8c12d3d133000a880c58366a9f2b13ed8cbf49
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203030"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Azure Active Directory 그룹에 대한 분류 및 Microsoft 365 레이블 지정

이 문서에서는 분류 및 Azure Active Directory 레이블에 대한 클래식 설명을 제공합니다.

민감도 레이블은 이러한 [서비스에서 지원됩니다.](./sensitivity-labels-teams-groups-sites.md)

민감도 레이블에 대한 자세한 내용은 민감도 레이블에 대한 [자세한 정보를 참조하세요.](sensitivity-labels.md)

사이트 및 Microsoft 365 그룹에 대한 민감도 레이블 및 해당 동작에 대한 자세한 내용은 민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트의 콘텐츠를 [보호합니다.를 참조하세요.](sensitivity-labels-teams-groups-sites.md)

클래식 AAD 분류에서 민감도 레이블로 마이그레이션할 때의 모범 사례는 다음 시나리오를 참조합니다.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>시나리오 1: 테넌트가 문서 및 전자 메일에 대해 클래식 AAD 분류 또는 민감도 레이블을 사용한 적이 없습니다.

- 테넌트 관리자는 AAD powershell cmdlet을 통해 테넌트 플래그 "EnableMIPLabels"를 true로 설정하여 그룹에 대해 민감도 레이블을 사용하도록 설정할 수 있습니다.
- 테넌트 관리자는 에 민감도 레이블을 [Microsoft 365 규정 준수 센터.](https://compliance.microsoft.com)
    - 테넌트 관리자는 암호화 및 워터마크와 같은 파일 및 전자 메일 관련 작업을 선택할 수 있습니다.
    - 테넌트 관리자는 그룹 및 Microsoft 365 레이블에 대한 온라인 SharePoint 작업을 선택할 수 있습니다.
- 테넌트 관리자가 정책을 게시합니다.
- **호환되는 워크로드에는** 민감도 레이블이 표시됩니다. 민감도 레이블을 사용하여 그룹을 만들 수 있습니다. 호환되는 작업은 민감도 레이블을 지원하는 서비스입니다.
- **호환되지 않는 작업은** 아직 민감도 레이블을 지원하지 않는 서비스입니다. 그러나 그룹은 호환되지 않는 워크로드를 통해 민감도 레이블과 연결될 수 없습니다. 이러한 그룹을 민감도 레이블과 연결하기 위해 테넌트 관리자는 PowerShell cmdlet을 실행할 수 있습니다.

표 1. 호환 및 호환되지 않는 작업의 동작 - 그룹 만들기, 편집 또는 삭제

|워크로드|그룹 창에 사용자에게 어떤 레이블 목록이 표시하나요?|새 그룹 만들기 |그룹 편집 |그룹 삭제 |
|:-------|:-------|:--------|:--------|:--------|   
|호환   |민감도 레이블. |동작이 변경되지 않습니다. |동작이 변경되지 않습니다. |동작이 변경되지 않습니다. |
|호환되지 않습니다. |민감도 레이블이 표시되지 않습니다. |사용자는 민감도 레이블을 선택하지 않고 그룹을 만들 수 있습니다. <br><br> 관리자는 cmdlet을 실행하여 백그라운드에서 민감도 레이블을 적용할 수 있습니다. |**사례 1:** 이전에 민감도 레이블을 선택하지 않았습니다. 사용자는 그룹을 편집할 수 있습니다.<br><br> **사례 2:** cmdlet을 사용하여 이전에 백그라운드에서 적용된 민감도 레이블입니다. 사용자가 레이블과 관련한 개인 정보 설정의 잘못된 조합을 선택하는 경우를 제외한 그룹을 성공적으로 편집할 수 있습니다. |동작이 변경되지 않습니다.|

> [!NOTE]
> 데스크톱 Outlook(Win 32)의 경우 관리자가 테넌트에서 민감도 레이블을 사용할 수 있도록 설정한 후 사용자가 이전 버전의 Outlook 데스크톱 클라이언트(Win 32)에 있습니다.
>
> - 이전 버전의 데스크톱 클라이언트에서 민감도 레이블이 Outlook 표시됩니다.
> - 그러나 사용자가 그룹을 편집하고 민감도 레이블로 그룹을 저장하면 선택한 개인 정보 설정이 적용된 민감도 레이블의 개인 정보 설정에 의해 의회됩니다.
>
> 이전 버전의 클라이언트를 최신 Outlook 업그레이드하는 것이 좋습니다.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>시나리오 2: 테넌트가 이미 클래식 AAD [분류를 사용하고 있습니다.](../enterprise/manage-microsoft-365-groups-with-powershell.md)

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>사례 A: 테넌트가 문서 및 전자 메일에 대해 민감도 레이블을 사용한 적이 없습니다.

1. 이 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)기존 Azure AD 레이블과 동일한 이름으로 민감도 레이블을 만드는 것이 좋습니다.
2. PowerShell cmdlet을 사용하여 이름 매핑을 사용하여 기존 Microsoft 365 및 SharePoint 레이블을 적용할 수 있습니다.
3. 관리자는 클래식 Azure AD 레이블을 삭제할 수 있습니다.
    - 호환되는 워크로드에는 이러한 민감도 레이블과 그룹이 생성됩니다.
    - 호환되지 않는 워크로드는 그룹을 만들 때 작동하지만 민감도 레이블이 그룹에 연결되지 않습니다.
4. 관리자는 PowerShell cmdlet을 실행하여 레이블이 없는 이러한 그룹에 민감도 레이블을 적용할 수 있습니다.
    - 또는 관리자는 클래식 Azure AD 레이블을 유지 하게 선택할 수 있습니다.
        - 호환되는 워크로드는 이러한 민감도 레이블을 표시하고 그룹이 함께 만들어집니다. 호환되는 작업은 민감도 레이블을 지원하는 서비스입니다.
        - 호환되지 않는 워크로드는 그룹을 만들 때 작동하고 클래식 Azure AD 레이블을 표시합니다. 이러한 클래식 Azure AD 레이블은 호환되지 않는 워크로드를 사용하여 만든 이러한 그룹에 연결됩니다.
5. 관리자는 PowerShell cmdlet을 실행하여 클래식 Azure AD 레이블을 사용하여 이러한 그룹에 민감도 레이블을 적용하는 것이 좋습니다.

표 2. 호환 및 호환되지 않는 작업의 동작 - 그룹 만들기, 편집 또는 삭제

|워크로드|그룹 창에 사용자에게 어떤 레이블 목록이 표시하나요?|새 그룹 만들기 |그룹 편집 |그룹 삭제 |
|:-------|:-------|:--------|:--------|:--------|   
|호환   |민감도 레이블. |동작이 변경되지 않습니다. |동작이 변경되지 않습니다. |동작이 변경되지 않습니다. |
|호환되지 않습니다. |이전 클래식 AAD 레이블 |사용자는 클래식 Azure AD 레이블이 선택된 그룹을 만들 수 있습니다. <br><br>관리자는 cmdlet을 실행하여 백그라운드에서 민감도 레이블을 적용할 수 있습니다. |**사례 1:** 이전에 민감도 레이블을 선택하지 않았습니다. 사용자는 그룹을 편집할 수 있습니다.<br><br> **사례 2:** 이전에 선택한 클래식 AAD 레이블입니다. 사용자는 그룹을 편집할 수 있습니다.<br><br> **사례 3:** cmdlet을 사용하여 백그라운드에서 이전에 적용된 민감도 레이블입니다. 사용자가 레이블과 관련한 개인 정보 설정의 잘못된 조합을 선택하는 경우를 제외한 그룹을 편집할 수 있습니다. |사용자는 그룹을 삭제할 수 있습니다. |

> [!NOTE]
> 데스크톱 Outlook(Win 32)의 경우 관리자가 테넌트에서 민감도 레이블을 사용할 수 있도록 설정한 후 사용자가 이전 버전의 Outlook 데스크톱 클라이언트(Win 32)에 있습니다.
>
> - 이전 버전의 데스크톱 클라이언트에서 민감도 레이블이 Outlook 표시됩니다.
> - 그러나 사용자가 그룹을 편집하고 민감도 레이블로 그룹을 저장하면 선택한 개인 정보 설정이 적용된 민감도 레이블의 개인 정보 설정에 의해 의회됩니다.
>
> 이전 버전의 클라이언트를 최신 Outlook 업그레이드하는 것이 좋습니다.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>사례 B: 테넌트가 문서 및 전자 메일에 민감도 레이블을 사용함

1. 관리자가 테넌트 플래그 'EnableMIPLabels'를 true로 설정하여 테넌트에서 민감도 레이블 기능을 사용하도록 설정하는 즉시 그룹/사이트/팀의 문서 및 전자 메일 민감도 레이블이 대화 상자를 만들고 편집합니다.
2. 관리자는 동일한 문서 및 전자 메일 민감도 레이블을 사용하여 그룹/사이트/팀에 대해 관련 그룹 설정을 지정하여 개인 정보 및 외부 사용자 액세스를 적용할 수 있습니다.
    1. 의 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)사이트 **및 그룹 탭을** 선택합니다.
    2. 문서 또는 전자 메일 민감도 레이블을 편집합니다.

## <a name="sample-script"></a>예제 스크립트

클래식 AAD 레이블이 있는 그룹을 민감도 레이블로 마이그레이션하는 샘플 스크립트는 [클래식 Azure AD 그룹 분류를 참조하세요.](./sensitivity-labels-teams-groups-sites.md#classic-azure-ad-group-classification)