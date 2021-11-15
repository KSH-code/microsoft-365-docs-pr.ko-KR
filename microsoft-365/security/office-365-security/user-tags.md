---
title: Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
description: 관리자는 Plan 2용 Microsoft Defender에서 사용자 태그를 사용하여 특정 사용자 그룹을 식별하는 Office 365 있습니다. 태그 필터링은 Microsoft Defender의 경고, 보고서 및 조사에서 사용할 수 있으며, Office 365 사용자를 빠르게 식별할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: db06c2a60ddc0cfb4d6bb2efce4e030eed6386a5
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962690"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

> [!NOTE]
> 사용자 태그 기능은 미리 보기에 있으며 모든 사용자가 사용할 수 있으며 변경될 수 있습니다. 릴리스 일정에 대한 자세한 내용은 Microsoft 365 [로드맵을 참조하십시오.](https://www.microsoft.com/microsoft-365/roadmap)

사용자 태그는 에 대한 Microsoft [Defender의](defender-for-office-365.md)특정 사용자 그룹의 식별자 Office 365. 사용자 태그에는 다음 두 가지 유형이 있습니다.

- **시스템 태그:** 현재 [우선](../../admin/setup/priority-accounts.md) 순위 계정은 시스템 태그의 유일한 유형입니다.
- **사용자 지정 태그:** 이러한 사용자 태그를 직접 만들 수 있습니다.

조직에 Office 365 계획 2에 대한 Defender가 있는 경우(구독 또는 추가 기능으로 포함) 우선 순위 계정 태그를 사용하는 것 외에도 사용자 지정 사용자 태그를 만들 수 있습니다.

> [!NOTE]
> 현재 사서함 사용자에게만 사용자 태그를 적용할 수 있습니다.

사용자에게 시스템 태그 또는 사용자 지정 태그를 적용한 후 경고, 보고서 및 조사에서 이러한 태그를 필터로 사용할 수 있습니다.

- [경고](alerts.md)
- [사용자 지정 경고 정책](../../compliance/alert-policies.md#viewing-alerts)
- [위협 탐색기 및 실시간 검색](threat-explorer.md)
- [전자 메일 엔터티 페이지](mdo-email-entity-page.md#other-innovations)
- [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)
- [캠페인 보기](campaigns.md)
- [관리자 및 사용자 제출](admin-submission.md)
- 우선 순위 계정의 경우 [](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) EAC(Exchange 관리 센터)의 우선 순위 계정 보고서에 전자 메일 문제를 사용할 수 있습니다.

이 문서에서는 포털 에서 사용자 태그를 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">구성하는 Microsoft 365 Defender 설명합니다.</a> 사용자 태그를 관리하는 Microsoft 365 Defender cmdlet이 없습니다.

사용자 태그가 영향력이 큰 사용자 계정을 보호하는 데 도움이 되는 전략의 일부인 방법을 자세한 내용은 에서 우선 순위 계정에 [대한 보안 권장 사항을 Microsoft 365.](security-recommendations-for-priority-accounts.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 에서 Microsoft 365 Defender 포털을 열 수 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com/</a> 있습니다. 사용자 태그 페이지로 직접 **이동하기** 위해 를 를 <https://security.microsoft.com/securitysettings/userTags> 니다.

- 이 문서의 절차를 수행하려면 Microsoft 365 Defender 포털에서 사용 권한을 할당해야 합니다.
  - 사용자 태그를 만들고 수정하고 삭제하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 **구성원이** 되거나 삭제해야 합니다.
  - 기존 사용자 태그에서 구성원을 추가 및 제거하려면 **조직** **관리,** 보안 관리자 또는 보안 운영자 역할 그룹의 **구성원이** 되거나,
  - 사용자 태그에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나 해야 합니다.

  자세한 내용은 [Microsoft 365 Defender 포털 권한](permissions-microsoft-365-security-center.md)을 참조하세요.

  > [!NOTE]
  >
  > - Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 관리 센터 포털에서 필요한 사용 권한 및 Microsoft 365 Defender 포털의  다른 기능에 대한 사용 권한이 Microsoft 365. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  >
  > - 사용자 태그 관리는 태그 판독기 및 **태그** 관리자 **역할에 의해** 제어됩니다.

- 또한 사용자 계정에서 우선 순위 계정을 관리하고 모니터링할 Microsoft 365 관리 센터. 자세한 내용은 우선 순위 [계정 관리 및 모니터링을 참조하세요.](../../admin/setup/priority-accounts.md)

- 권한 있는 계정(관리자 계정)의 보안에 대한 자세한 내용은 이 [항목을 참조하세요.](/azure/architecture/framework/security/critical-impact-accounts) 

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a>Microsoft 365 Defender 포털을 사용하여 사용자 태그 만들기

1. Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">포털에서</a>설정 전자 메일  & \>  \> **사용자 태그로 이동하세요.**

2. 사용자 **태그 페이지에서** 태그 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **태그 만들기**.

3. 태그 **만들기 마법사가** 새 플라이아웃에서 열립니다. 태그 **정의 페이지에서** 다음 설정을 구성합니다.
   - **이름:** 태그를 설명하는 고유한 이름을 입력합니다. 이 값은 표시하고 사용할 수 있습니다. 태그를 만든 후 태그 이름을 다시 만들 수 없습니다.
   - **설명:** 태그에 대한 선택적 설명을 입력합니다.

   작업을 마친 후 **다음** 을 클릭합니다.

4. 구성원 **할당 페이지에서** 다음 단계 중 하나를 수행합니다.
   - 구성원 ![ 추가 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **구성원을 추가합니다.** 플라이아웃이 나타나면 다음 단계에 따라 개별 사용자 또는 그룹을 추가합니다.
     - 상자를 클릭하고 목록을 스크롤하여 사용자 또는 그룹을 선택합니다.
     - 상자를 클릭하고 입력을 시작하여 목록을 필터링하고 사용자 또는 그룹을 선택합니다.
     - 값을 더 추가하려면 상자의 빈 영역을 클릭합니다.
     - 개별 항목을 제거하려면 ![항목 아이콘을 제거합니다.](../../media/m365-cc-sc-remove-selection-icon.png) 상자의 항목 옆에 있습니다.
     - 모든 항목을 제거하려면 항목 제거 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-remove-selection-icon.png) 상자 **아래의 선택한 nn 사용자 및 nn** 그룹 항목

     작업을 마쳤으면 **추가** 를 클릭합니다.

     구성원 할당 **페이지에서** 삭제 아이콘을 클릭하여 항목을 제거할 ![ 수도 있습니다.](../../media/m365-cc-sc-delete-icon.png) 항목 옆의

   - 가져오기 **를** 클릭하여 사용자 또는 그룹의 전자 메일 주소가 포함된 텍스트 파일을 선택합니다. 텍스트 파일에 한 줄에 항목이 하나씩 포함되어 있는지 확인

   작업을 마친 후 **다음** 을 클릭합니다.

5. 태그 **검토** 페이지가 나타나면 설정을 검토합니다. 각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다. 또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.

   완료되면 제출을 **클릭하고** 완료를 **클릭합니다.**

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a>Microsoft 365 Defender 포털을 사용하여 사용자 태그 보기

1. Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">포털에서</a>설정 전자 메일  & \>  \> **사용자 태그로 이동하세요.**

2. 사용자 **태그 페이지에는** 사용자 태그 목록에 다음 속성이 표시됩니다.

   - **Tag**: 사용자 태그의 이름입니다. 여기에는 기본 제공 우선 순위 계정 **시스템 태그가** 포함됩니다.
   - **적용된 구성원** 수
   - **마지막으로 수정한 날짜**
   - **만든 날짜**

3. 이름을 클릭하여 사용자 태그를 선택하면 세부 정보가 플라이아웃에 표시됩니다.

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a>Microsoft 365 Defender 포털을 사용하여 사용자 태그 수정

1. Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">포털에서</a>설정 전자 메일  & \>  \> **사용자 태그로 이동하세요.**

2. 사용자 **태그 페이지에서** 목록에서 사용자 태그를 선택한 다음 태그 편집 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-edit-icon.png) **태그를 편집합니다.**

3. 나타나는 세부 정보 플라이아웃에서 이 문서 앞부분의 Microsoft 365 Defender [](#use-the-microsoft-365-defender-portal-to-create-user-tags) 포털을 사용하여 사용자 태그 만들기 섹션에 설명된 대로 동일한 마법사 및 설정을 사용할 수 있습니다.

   **참고:**

   - 태그 **정의 페이지는** 기본 제공 우선  순위 계정 시스템 태그에 사용할 수 없습니다. 따라서 이 태그의 이름을 바꾸거나 설명을 변경할 수 없습니다.
   - 사용자 지정 태그의 이름을 바꿀 수 없지만 설명을 변경할 수 있습니다.

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a>사용자 Microsoft 365 Defender 포털을 사용하여 사용자 태그 제거

> [!NOTE]
> 기본 제공 우선 순위 계정 시스템 태그는 **제거할** 수 없습니다.

1. Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">포털에서</a>설정 전자 메일  & \>  \> **사용자 태그로 이동하세요.**

2. 사용자 **태그 페이지에서** 목록에서 사용자 태그를 선택한 다음 태그 삭제 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-delete-icon.png) **태그를 삭제합니다.**

3. 나타나는 확인 대화 상자에서 경고를 읽은 다음 **예, 제거를 클릭합니다.**
