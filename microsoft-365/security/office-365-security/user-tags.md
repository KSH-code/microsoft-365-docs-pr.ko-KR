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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft Defender for Office 365 계획 2에서 사용자 태그를 사용 하 여 특정 사용자 그룹을 식별 하는 방법을 확인할 수 있습니다. 태그 필터링은 태그가 지정 된 사용자를 빠르게 식별 하기 위해 Microsoft Defender for Office 365의 경고, 보고서 및 조사를 통해 제공 됩니다.
ms.openlocfilehash: 9c83a323a3116b3da61a133c7fb449978ca13841
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945321"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 사용자 태그

> [!NOTE]
> 사용자 태그 기능은 미리 보기에서 모든 사용자가 사용할 수 없으며 변경할 수 있습니다. 릴리스 일정에 대 한 자세한 내용은 [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap)를 참조 하세요.

사용자 태그는 [Microsoft Defender For Office 365](office-365-atp.md)의 특정 사용자 그룹에 대 한 식별자입니다. 사용자 태그에는 다음과 같은 두 가지 유형이 있습니다.

- **시스템 태그** : 현재 [우선 순위 계정만](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 시스템 태그 유형입니다.
- **사용자 지정 태그** : 이러한 사용자 태그를 직접 만듭니다.

조직에 Office 365 계획 2에 대 한 Defender가 있는 경우 (구독 또는 추가 기능에 포함 된 경우) priority accounts 태그를 사용 하는 것 외에 사용자 지정 사용자 태그를 만들 수 있습니다.

사용자에 게 시스템 태그나 사용자 지정 태그를 적용 한 후에는 경고, 보고서 및 조사에서 해당 태그를 필터로 사용할 수 있습니다.

- [보안 & 준수 센터의 알림](alerts.md)
- [위협 탐색기 및 실시간 검색](threat-explorer.md)
- [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)
- [캠페인 보기](campaigns.md)

이 문서에서는 보안 & 준수 센터에서 사용자 태그를 구성 하는 방법을 설명 합니다. 사용자 태그를 관리 하기 위한 보안 & 준수 센터에 cmdlet이 없습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **사용자 태그** 페이지로 직접 이동 하려면를 엽니다 <https://protection.office.com/userTags> .

- **사용자 지정 사용자 태그** 를 만들거나 수정 하거나 제거 하려면 보안 & 준수 센터에서 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다. 자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

- 우선 순위 계정 (시스템 태그)을 구성 하려면 [전역 관리자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 또는 [Exchange 관리자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)여야 합니다.

  Microsoft 365 관리 센터에서 우선 순위 계정을 관리 하 고 모니터링할 수도 있습니다. 자세한 내용은 [우선 순위 계정 관리 및 모니터링](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)을 참조 하십시오.

## <a name="use-the-security-center-to-create-user-tags"></a>보안 센터를 사용 하 여 사용자 태그 만들기

1. 보안 센터에서 **위협 관리** \> **사용자 태그로** 이동 합니다.

2. **사용자 태그** 페이지가 열리면 **태그 만들기** 를 클릭 합니다.

3. 새 플라이 아웃에서 **태그 만들기** 마법사가 열립니다. **태그 정의** 페이지에서 다음 설정을 구성 합니다.

   - **이름** : 태그에 대해 설명 하는 고유한 이름을 입력 합니다. 이 값을 보고 사용 하는 것이 좋습니다.

   - **설명** : 태그에 대 한 설명을 입력 합니다 (선택 사항).

   작업을 마친 후 **다음** 을 클릭합니다.

4. **사서함 할당** 페이지에서 다음 단계 중 하나를 수행 합니다.

   - **사서함 추가** 를 클릭 합니다. 즉시 표시 되는 다음 단계를 수행 하 여 개별 사용자 또는 그룹을 추가 합니다.

     - 상자를 클릭 하 고 목록을 스크롤하여 사용자 또는 그룹을 선택 합니다.
     - 상자를 클릭 하 고 입력을 시작 하 여 목록을 필터링 하 고 사용자 또는 그룹을 선택 합니다.
     - 값을 더 추가 하려면 상자에서 빈 영역을 클릭 합니다.
     - 상자에서 개별 항목을 제거 하려면 상자에서 **Remove** ![ ](../../media/scc-remove-icon.png) 사용자 또는 그룹에 대 한 제거 아이콘 제거를 클릭 합니다.
     - 상자 아래 목록에서 기존 항목을 제거 하려면 제거 아이콘 **제거** 를 클릭 ![ ](../../media/scc-remove-icon.png) 합니다.

     작업이 완료 되 면 **추가** 를 클릭 합니다.

   - **가져오기를** 클릭 하 여 사용자 또는 그룹의 전자 메일 주소가 포함 된 텍스트 파일을 선택 합니다. 텍스트 파일에 줄당 한 개의 항목이 포함 되어 있어야 합니다.

   작업을 마친 후 **다음** 을 클릭합니다.

5. **태그 검토** 페이지에서 설정을 검토 합니다. 변경 작업을 수행 하려면 특정 섹션에서 **편집** 을 클릭 하면 됩니다.

   작업이 완료 되 면 **제출을** 클릭 합니다.

## <a name="use-the-security-center-to-view-user-tags"></a>보안 센터를 사용 하 여 사용자 태그 보기

1. 보안 센터에서 **위협 관리** \> **사용자 태그로** 이동 합니다.

2. **사용자 태그** 페이지가 열리면 보려는 사용자 태그를 선택 합니다 (확인란을 클릭 하지 않음).

3. 읽기 전용 세부 정보가 표시 되 면 설정을 검토 합니다.

   작업을 마쳤으면 **닫기** 를 클릭합니다.

## <a name="use-the-security-center-to-modify-user-tags"></a>보안 센터를 사용 하 여 사용자 태그 수정

1. 보안 센터에서 **위협 관리** \> **사용자 태그로** 이동 합니다.

2. **사용자 태그** 페이지가 열리면 보려는 사용자 태그를 선택 하 고 **태그 편집** 을 클릭 합니다.

3. **편집 태그** 에서 즉시 정책 마법사가 열립니다. **다음** 을 클릭 하 여 설정을 검토 하 고 수정 합니다.

   작업이 완료 되 면 **제출을** 클릭 합니다.

## <a name="use-the-security-center-to-remove-user-tags"></a>보안 센터를 사용 하 여 사용자 태그 제거

**참고** : 기본 제공 **우선 순위 계정** 태그는 제거할 수 없습니다.

1. 보안 센터에서 **위협 관리** \> **사용자 태그로** 이동 합니다.

2. **사용자 태그** 페이지가 열리면 제거할 사용자 태그를 선택 하 고 **태그 삭제** 를 클릭 한 다음 표시 되는 경고에서 **예, 제거** 를 선택 합니다.
