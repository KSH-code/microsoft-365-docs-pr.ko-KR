---
title: Microsoft 365 그룹에 대 한 Azure Active Directory 분류 및 민감도 레이블
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
description: 이 문서에서는 기존 Azure Active Directory 분류 및 민감도 레이블에 대해 설명 합니다.
ms.openlocfilehash: 38a3dbe727f3d0759d427944016ae98440f2686f
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308175"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Microsoft 365 그룹에 대 한 Azure Active Directory 분류 및 민감도 레이블

이 문서에서는 기존 Azure Active Directory 분류 및 민감도 레이블에 대해 설명 합니다.

민감도 레이블은 [이러한 서비스](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#support-for-the-sensitivity-labels)에서 지원 됩니다.

민감도 레이블에 대 한 자세한 내용은 [민감도 레이블에 대](sensitivity-labels.md)한 정보를 참조 하십시오.

사이트 및 Microsoft 365 그룹의 민감도 레이블 및 해당 동작에 대 한 자세한 내용은 [Microsoft 팀, microsoft 365 그룹 및 SharePoint 사이트의 콘텐츠 보호에 민감도 레이블 사용](sensitivity-labels-teams-groups-sites.md)을 참조 하십시오.

클래식 AAD 분류에서 민감도 레이블로 마이그레이션할 때의 모범 사례를 확인 하려면 다음 시나리오를 참조 하십시오.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>시나리오 1: 테 넌 트가 문서 및 전자 메일에 대 한 클래식 AAD 분류 또는 민감도 레이블을 사용 하지 않음

- 테 넌 트 관리자는 AAD powershell cmdlet을 통해 테 넌 트 플래그 "EnableMIPLabels"를 true로 설정 하 여 그룹에 대 한 민감도 레이블을 사용할 수 있도록 합니다.
- 테 넌 트 관리자는 [Microsoft 365 준수 센터](https://compliance.microsoft.com)에서 민감도 레이블을 만듭니다.
    - 테 넌 트 관리자는 암호화 및 watermarking 같은 파일 및 전자 메일 관련 작업을 선택할 수 있습니다.
    - 테 넌 트 관리자는 민감도 레이블에 Microsoft 365 그룹 및 SharePoint Online 사이트 관련 작업을 선택할 수 있습니다.
- 테 넌 트 관리자가 정책을 게시 합니다.
- **호환 되는 작업 부하** 민감도 레이블 표시 민감도 레이블을 사용 하 여 그룹을 만들 수 있습니다. 호환 되는 작업은 민감도 레이블을 지 원하는 서비스입니다.
- **호환 되지 않는 작업** 은 아직 민감도 레이블을 지원 하지 않는 서비스입니다. 그러나 그룹을 만들 수는 있지만 호환 되지 않는 작업을 통해 민감도 레이블과 연결할 수는 없습니다. 이러한 그룹을 민감도 레이블과 연결 하기 위해 테 넌 트 관리자는 PowerShell cmdlet을 실행할 수 있습니다.

표 1. 호환 및 호환 되지 않는 작업의 동작-그룹 만들기, 편집 또는 삭제

|작업량|그룹 창에서 사용자에 게 표시 되는 레이블 목록은 무엇입니까?|새 그룹 만들기 |그룹 편집 |그룹 삭제 |
|:-------|:-------|:--------|:--------|:--------|   
|호환   |민감도 레이블 |동작이 변경 되지 않습니다. |동작이 변경 되지 않습니다. |동작이 변경 되지 않습니다. |
|호환 되지 않는 |민감도 레이블이 표시 되지 않습니다. |사용자는 민감도 레이블을 선택 하지 않고 그룹을 만들 수 있습니다. <br><br> 참고로 관리자는 cmdlet을 실행 하 여 민감도 레이블을 배경에 적용할 수 있습니다. |**사례 1**: 이전에 민감도 레이블이 선택 되지 않았습니다. 사용자가 그룹을 편집할 수 있습니다.<br><br> **사례 2**: cmdlet을 사용 하 여 이전에 적용 된 민감도 레이블입니다. 사용자가 레이블과 관련 하 여 사용자가 잘못 된 개인 정보 설정 조합을 선택 하는 경우를 제외 하 고 그룹을 성공적으로 편집할 수 있습니다. |동작이 변경 되지 않습니다.|

> [!NOTE]
> Outlook 데스크톱 클라이언트 (Win 32)의 경우, 관리자가 테 넌 트의 민감도 레이블을 사용 하도록 설정 하 고 사용자는 이전 버전의 Outlook 데스크톱 클라이언트 (Win 32)에 있습니다.
> - 사용자에 게는 Outlook 데스크톱 클라이언트의 이전 버전에 민감도 레이블이 표시 됩니다.
> - 그러나 사용자가 그룹을 편집 하 고 민감도 레이블과 함께 그룹을 저장 하면 선택한 개인 정보 설정이 적용 된 민감도 레이블의 개인 정보 설정에 의해 재정의 됩니다.
> 이전 버전의 Outlook 클라이언트에 대 한 사용자가 최신 버전으로 업그레이드 하는 것이 좋습니다.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>시나리오 2: 테 넌 트가 이미 클래식 AAD [분류](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell) 를 사용 하 고 있습니다.

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>사례 A: 테 넌 트가 문서 및 전자 메일에 대 한 민감도 레이블을 사용 하지 않음

1. [Microsoft 365 준수 센터](https://compliance.microsoft.com)에서는 기존 클래식 Azure AD 레이블과 이름이 같은 민감도 레이블을 만드는 것이 좋습니다.
2. PowerShell cmdlet을 사용 하 여 이러한 민감도 레이블을 이름 매핑을 사용 하 여 기존 Microsoft 365 그룹 및 SharePoint 사이트에 적용 합니다.
3. 관리자는 기본 Azure AD 레이블을 삭제 하도록 선택할 수 있습니다.
    - 호환 되는 작업 부하 표시 이러한 민감도 레이블 및 그룹을 사용 하 여 만듭니다.
    - 호환 되지 않는 작업 부하는 그룹을 만들 때 작동 하지만 민감도 레이블은 첨부 되지 않습니다.
4. 관리자는 PowerShell cmdlet을 실행 하 여 레이블 없이 이러한 그룹에 민감도 레이블을 적용할 수 있습니다.
    - 또는 관리자가 기본 Azure AD 레이블을 유지 하도록 선택할 수 있습니다.
        - 호환 작업은 이러한 민감도 레이블을 표시 하며, 그룹을 통해 그룹이 만들어집니다. 호환 되는 작업은 민감도 레이블을 지 원하는 서비스입니다.
        - 호환 되지 않는 작업은 그룹을 만들 때 작업을 수행 하 고 클래식 Azure AD 레이블을 표시 합니다. 이러한 클래식 Azure AD 레이블은 호환 되지 않는 작업을 통해 만들어지는 이러한 그룹에 연결 됩니다.
5. 관리자는 PowerShell cmdlet을 실행 하 여 클래식 Azure AD 레이블을 사용 하 여 이러한 그룹에 민감도 레이블을 적용 하는 것이 좋습니다.

표 2. 호환 및 호환 되지 않는 작업의 동작-그룹 만들기, 편집 또는 삭제

|작업량|그룹 창에서 사용자에 게 표시 되는 레이블 목록은 무엇입니까?|새 그룹 만들기 |그룹 편집 |그룹 삭제 |
|:-------|:-------|:--------|:--------|:--------|   
|호환   |민감도 레이블 |동작이 변경 되지 않습니다. |동작이 변경 되지 않습니다. |동작이 변경 되지 않습니다. |
|호환 되지 않는 |이전 클래식 AAD 레이블입니다. |사용자가 클래식 Azure AD 레이블이 선택 된 그룹을 만들 수 있습니다. <br><br>참고로 관리자는 cmdlet을 실행 하 여 민감도 레이블을 배경에 적용할 수 있습니다. |**사례 1**: 이전에 민감도 레이블이 선택 되지 않았습니다. 사용자가 그룹을 편집할 수 있습니다.<br><br> **사례 2**: 이전에 클래식 AAD 레이블을 선택 했습니다. 사용자가 그룹을 편집할 수 있습니다.<br><br> **사례 3**: 이전에 cmdlet을 사용 하 여 적용 한 민감도 레이블입니다. 사용자가 레이블과 관련 된 개인 정보 설정의 잘못 된 조합을 선택 하는 경우를 제외 하 고 그룹을 편집할 수 있어야 합니다. |사용자가 그룹을 삭제할 수 있습니다. |

> [!NOTE]
> Outlook 데스크톱 클라이언트 (Win 32)의 경우, 관리자가 테 넌 트의 민감도 레이블을 사용 하도록 설정 하 고 사용자는 이전 버전의 Outlook 데스크톱 클라이언트 (Win 32)에 있습니다.
> - 사용자에 게는 Outlook 데스크톱 클라이언트의 이전 버전에 민감도 레이블이 표시 됩니다.
> - 그러나 사용자가 그룹을 편집 하 고 민감도 레이블과 함께 그룹을 저장 하면 선택한 개인 정보 설정이 적용 된 민감도 레이블의 개인 정보 설정에 의해 재정의 됩니다.
> 이전 버전의 Outlook 클라이언트에 대 한 사용자가 최신 버전으로 업그레이드 하는 것이 좋습니다.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>사례 B: 문서 및 전자 메일에 대 한 테 넌 트 사용 민감도 레이블

1. 관리자가 테 넌 트 플래그 ' EnableMIPLabels '를 true로 설정 하 여 테 넌 트의 민감도 레이블 기능을 사용 하도록 설정한 즉시 그룹/사이트/팀에서 문서 및 전자 메일 민감도 레이블 만들기 및 편집 대화 상자가 나타납니다.
2. 관리자는 동일한 문서 및 전자 메일 민감도 레이블을 사용 하 여 관련 그룹 설정을 지정 하 여 그룹/사이트/팀에 대 한 개인 정보 및 외부 사용자 액세스를 적용할 수 있습니다.
    1. [Microsoft 365 준수 센터](https://compliance.microsoft.com)에서 **사이트 및 그룹** 탭을 선택 합니다.
    2. 문서 또는 전자 메일 민감도 레이블을 편집 합니다.

## <a name="sample-script"></a>예제 스크립트

클래식 AAD 레이블이 있는 그룹을 민감도 레이블로 마이그레이션하기 위한 샘플 스크립트는 [클래식 AZURE AD 그룹 분류](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)를 참조 하세요.

