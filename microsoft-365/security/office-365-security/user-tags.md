---
title: Microsoft Defender for Office 365의 사용자 태그
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft Defender for Office 365 계획 2에서 사용자 태그를 사용하여 특정 사용자 그룹을 식별하는 방법을 배울 수 있습니다. 태그 필터링은 Microsoft Defender for Office 365의 경고, 보고서 및 조사에서 사용할 수 있으며, 태그가 지정된 사용자를 빠르게 식별할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e5ddffad6405f48a9af55b5123729eb256064a7
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453648"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 사용자 태그

> [!NOTE]
> 사용자 태그 기능은 미리 보기에 있으며 모든 사용자가 사용할 수 있으며 변경될 수 있습니다. 릴리스 일정에 대한 자세한 내용은 [Microsoft 365 로드맵 을 참조하십시오.](https://www.microsoft.com/microsoft-365/roadmap)

사용자 태그는 [Office 365용 Microsoft Defender의](office-365-atp.md)특정 사용자 그룹에 대한 식별자입니다. 사용자 태그에는 다음 두 가지 유형이 있습니다.

- **시스템 태그:** 현재 [우선](../../admin/setup/priority-accounts.md) 순위 계정은 시스템 태그의 유일한 유형입니다.
- **사용자 지정 태그:** 이러한 사용자 태그를 직접 만들 수 있습니다.

조직에 Office 365 계획 2용 Defender가 있는 경우(구독 또는 추가 기능으로 포함) 우선 순위 계정 태그를 사용하는 것 외에도 사용자 지정 사용자 태그를 만들 수 있습니다.

사용자에게 시스템 태그 또는 사용자 지정 태그를 적용한 후 경고, 보고서 및 조사에서 이러한 태그를 필터로 사용할 수 있습니다.

- [보안 및 준수 & 알림](alerts.md)
- [위협 탐색기 및 실시간 검색](threat-explorer.md)
- [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)
- [캠페인 보기](campaigns.md)
- 우선 순위 계정의 경우 [](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) EAC(Exchange 관리 센터)의 우선 순위 계정 보고서에 대한 전자 메일 문제를 사용할 수 있습니다.

이 문서에서는 보안 및 준수 센터에서 사용자 태그를 & 설명합니다. 보안 및 준수 센터에는 사용자 태그를 & cmdlet이 없습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 사용자 태그 페이지로 직접 **이동하기** 위해 를 를 <https://protection.office.com/userTags> 니다.

- 이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.
  - 사용자 태그를 만들고 수정하고 삭제하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 **구성원이** 되거나 삭제해야 합니다.
  - 기존 사용자 태그에서 구성원을 추가 및 제거하려면 **조직** **관리,** 보안 관리자 또는 보안 운영자 역할 그룹의 **구성원이** 되거나,
  - 사용자 태그에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나 해야 합니다.

  자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

  **참고**:

  - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  - 사용자 태그 관리는 태그 판독기 및 **태그** 관리자 **역할에 의해** 제어됩니다.

- Microsoft 365 관리 센터에서 우선 순위 계정을 관리하고 모니터링할 수도 있습니다. 자세한 내용은 우선 순위 [계정 관리 및 모니터링을 참조하세요.](../../admin/setup/priority-accounts.md)

## <a name="use-the-security-center-to-create-user-tags"></a>보안 센터를 사용하여 사용자 태그 만들기

1. 보안 센터에서 위협 관리 **사용자** \> **태그로 이동합니다.**

2. 열 **수 있는 사용자 태그** 페이지에서 태그 **만들기 를 클릭합니다.**

3. 태그 **만들기 마법사가** 새 플라이아웃에서 열립니다. 태그 **정의 페이지에서** 다음 설정을 구성합니다.
   - **이름:** 태그를 설명하는 고유한 이름을 입력합니다. 이 값은 표시하고 사용할 수 있습니다.
   - **설명:** 태그에 대한 선택적 설명을 입력합니다.

   작업을 마친 후 **다음** 을 클릭합니다.

4. 사용자 **할당 페이지에서** 다음 단계 중 하나를 수행합니다.

   - 사용자 **추가를 클릭합니다.** 플라이아웃이 나타나면 다음 단계에 따라 개별 사용자 또는 그룹을 추가합니다.
     - 상자를 클릭하고 목록을 스크롤하여 사용자 또는 그룹을 선택합니다.
     - 상자를 클릭하고 입력을 시작하여 목록을 필터링하고 사용자 또는 그룹을 선택합니다.
     - 값을 더 추가하려면 상자의 빈 영역을 클릭합니다.
     - 상자에서 개별 항목을 제거하려면  상자의 사용자 또는 그룹에서 제거 아이콘 ![ ](../../media/scc-remove-icon.png) 제거를 클릭합니다.
     - 상자 아래의 목록에서 기존 항목을 제거하려면 항목 **제거** ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.

     작업을 마쳤으면 **추가** 를 클릭합니다.

   - 가져오기 **를** 클릭하여 사용자 또는 그룹의 전자 메일 주소가 포함된 텍스트 파일을 선택합니다. 텍스트 파일에 한 줄에 항목이 하나씩 포함되어 있는지 확인

   작업을 마친 후 **다음** 을 클릭합니다.

5. 태그 **검토 페이지에서** 설정을 검토합니다. 특정 섹션에서 **편집을** 클릭하여 변경할 수 있습니다.

   완료되면 제출을 **클릭합니다.**

## <a name="use-the-security-center-to-view-user-tags"></a>보안 센터를 사용하여 사용자 태그 보기

1. 보안 센터에서 위협 관리 **사용자** \> **태그로 이동합니다.**

2. 열 **수 있는 사용자** 태그 페이지에서 보하려는 사용자 태그를 선택합니다(확인란을 클릭하지 않습니다).

3. 나타나는 읽기 전용 세부 정보 플라이아웃에서 설정을 검토합니다.

   작업을 마쳤으면 **닫기** 를 클릭합니다.

## <a name="use-the-security-center-to-modify-user-tags"></a>보안 센터를 사용하여 사용자 태그 수정

1. 보안 센터에서 위협 관리 **사용자** \> **태그로 이동합니다.**

2. 열 **수 있는 사용자** 태그 페이지에서 보하려는 사용자 태그를 선택한 다음 태그 **편집을 클릭합니다.**

3. 정책 마법사가 태그  편집 플라이아웃에서 열립니다. **다음을** 클릭하여 설정을 검토하고 수정합니다.

   완료되면 제출을 **클릭합니다.**

## <a name="use-the-security-center-to-remove-user-tags"></a>보안 센터를 사용하여 사용자 태그 제거

**참고:** 기본 제공 우선 순위 계정 태그는 제거할 **수** 없습니다.

1. 보안 센터에서 위협 관리 **사용자** \> **태그로 이동합니다.**

2. 열 **수 있는 사용자** 태그 페이지에서 제거할 사용자 태그를 선택하고 태그 삭제를 클릭한 다음 **예,** 나타나는 경고에서 제거를 선택합니다.
