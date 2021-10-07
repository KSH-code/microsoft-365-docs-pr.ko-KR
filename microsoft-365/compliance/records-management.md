---
title: Microsoft 365의 레코드 관리하기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Microsoft 365의 레코드 관리를 사용하여 보존 일정을 파일 플랜에 적용하여 보존, 레코드 선언, 처리를 관리할 수 있습니다.
ms.openlocfilehash: 410fa890e159d18e3aacedbf08be44ee047ee189
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60158169"
---
# <a name="learn-about-records-management-in-microsoft-365"></a>Microsoft 365의 레코드 관리하기에 대해 알아보기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

모든 유형의 조직에는 회사 데이터 전체의 규정, 법률 및 비즈니스에 중요한 레코드를 관리하기 위한 레코드 관리 솔루션이 필요합니다. Microsoft 365의 레코드 관리는 조직이 법적인 의무를 관리하는 데 도움이 되고, 규정 준수를 입증하는 기능을 제공하며, 비즈니스 목적에 대해 더 이상 보존할 필요가 없거나, 더 이상 가치가 없거나, 사용하지 않는 항목을 정기적으로 처리하여 효율성을 높입니다.

Microsoft 365에서 다음 기능을 사용하여 레코드 관리 솔루션을 지원합니다.

- **레코드로 콘텐츠에 레이블 지정**. 콘텐츠를 사용자가 적용하거나 중요한 정보, 키워드 또는 콘텐츠 유형을 식별하여 자동으로 적용할 수 있는 [레코드](#records)로 표시하는 보존 레이블을 작성하고 구성합니다.

- **파일 요금제를 사용하여 보존 요구 사항을 마이그레이션하고 관리합니다**. [파일 요금제](file-plan-manager.md)를 사용하여 기존 보존 요금제를 Microsoft 365로 가져오거나 향상된 관리 기능을 위해 새로운 보존 요금제를 구축할 수 있습니다.

- **보존 레이블로 보존 및 삭제 설정을 구성합니다**. 마지막으로 수정되거나 생성된 날짜를 포함하는 다양한 요소를 기반으로 하는 보존 기간 및 작업으로 [보존 레이블](retention.md#retention-labels)을 구성합니다.

- [이벤트 기반 보존 **을 사용하여** 이벤트가 발생하는 경우 다른 보존 기간을 시작](event-driven-retention.md)합니다.

- [처리 검토](disposition.md#disposition-reviews) 및 [레코드 삭제](disposition.md#disposition-of-records) 검사를 통해 **처리를 검토하고 확인** 합니다.

- [내보내기 옵션](disposition.md#filter-and-export-the-views)으로 **모든 처리된 항목에 대한 정보를 내보냅니다**.

- 조직 레코드 관리자 기능의 **특정 권한을 설정** 하여 [올바른 액세스 권한을 보유](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)합니다.

해당 기능을 사용하면 조직의 보존 일정 및 요구 사항을 보존, 레코드 선언 및 처리를 관리하여 콘텐츠의 전체 라이프 사이클을 지원하는 레코드 관리 솔루션에 통합할 수 있습니다.

온라인 설명서 외에도 레코드 관리를 위해 [웨비나 레코드](https://aka.ms/MIPC/Video-RecordsManagementWebinar)를 청취하고 [FAQ와 함께 제공되는 데크](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)를 다운로드하는 것이 유용할 수 있습니다.

## <a name="records"></a>레코드

콘텐츠가 레코드로 선언된 경우:

- 항목에는 [허용 또는 차단되는 작업](#compare-restrictions-for-what-actions-are-allowed-or-blocked)에 대한 제한 사항이 적용됩니다.

- 항목에 대한 추가 활동이 기록됩니다.

- 보존 기간 종료 시에 항목이 삭제되는 경우 처리 증명을 가집니다.

[보존 레이블](retention.md#retention-labels)을 사용하여 콘텐츠를 **레코드** 혹은 **규제 레코드** 로 표시 이 두 개의 차이점은 다음 섹션에서 설명합니다. 사용자 및 관리자가 콘텐츠에 직접 적용할 수 있도록 해당 레이블을 게시하거나 레코드 혹은 규제 레코드로 표시하기를 원하는 콘텐츠에 해당 레이블을 자동으로 적용할 수 있습니다.

보존 레이블을 사용하여 레코드를 선언하면 Microsoft 365 환경에서 일관된 단일 레코드 관리 전략을 구현할 수 있습니다.

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>허용 또는 차단되는 작업에 대한 제한 사항 비교

다음 표를 사용하여 표준 보존 레이블을 적용한 결과로 콘텐츠에 가해지는 제한 사항과 콘텐츠를 레코드 혹은 규제 레코드로 표시하는 보존 레이블에 가해지는 제한 사항을 확인합니다.

표준 보존 레이블에는 보존 설정 및 작업이 포함되나 콘텐츠를 레코드 혹은 규제 레코드로 표시하지 않습니다.

> [!NOTE]
> 자세한 내용을 제공하기 위해 표에는 SharePoint 및 OneDrive에는 적용되지만 Exchange에는 적용되지 않는 잠긴 레코드와 잠금이 해제된 레코드에 대한 열이 포함되어 있습니다. 레코드를 잠그거나 잠금 해제하는 기능은 Exchange 항목에서는 지원되지 않는 [레코드 버전 관리](record-versioning.md)를 사용합니다. 따라서 레코드로 표시되는 모든 Exchange 항목의 경우 해당 동작이 **레코드 - 잠금** 열에는 해당되지만 **레코드 - 잠금 해제됨** 열은 해당되지 않습니다.


|작업| 보존 레이블 |레코드 - 잠금| 레코드 - 잠금 해제됨| 규제 레코드 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|콘텐츠 편집|허용됨 | **차단됨** | 허용됨 | **차단됨**|
|속성 편집(이름 바꾸기 포함)|허용됨 |허용됨 | 허용됨| **차단됨**|
|삭제|허용됨<sup>1</sup> |**차단됨** |**차단됨**| **차단됨**|
|복사|허용됨 |허용됨 | 허용됨| 허용됨|
|컨테이너 내에서 이동<sup>2</sup>|허용됨 |허용됨 | 허용됨| 허용됨|
|컨테이너 간에 이동<sup>2</sup>|허용됨 |잠금이 해제되지 않은 경우 허용됨 | **차단됨** | **차단됨**|
|열기/읽기|허용됨 |허용됨 | 허용됨| 허용됨|
|레이블 변경|허용됨 |허용됨 - 컨테이너 관리자 전용 | 허용됨 - 컨테이너 관리자 전용| **차단됨**
|레이블 제거|허용됨 |허용됨 - 컨테이너 관리자 전용 | 허용됨 - 컨테이너 관리자 전용| **차단됨**

각주:

<sup>1</sup> 복사본이 안전한 위치에 유지되지만 SharePoint에 의해 차단되므로 OneDrive 및 Exchange에서 지원됩니다.

문서 첨부 파일이 있는 목록 항목에 보존 레이블을 적용하면 해당 문서는 보존 설정을 상속하지 않으므로 목록 항목에서 삭제할 수 있습니다. 이와 비교하여 해당 목록 항목이 보존 레이블과 함께 레코드로 선언된 경우, 문서 첨부파일은 보존 설정을 상속하므로 삭제할 수 없습니다.

<sup>2</sup> 컨테이너에는 SharePoint 문서 라이브러리, OneDrive계정과 Exchange 사서함이 포함됩니다.

> [!IMPORTANT]
> 규제 기록에서 가장 중요한 차이는 콘텐츠에 적용한 후에는 이를 아무도, 심지어 전역 관리자도 레이블을 제거할 수 없다는 점입니다.
>
> 규정 레코드에 대해 구성된 보존 레이블에는 다음과 같은 관리자 제한 사항도 있습니다.
>
> - 레이블을 저장한 후 보존 기간을 단축 하는 작업은 할 수 없고 확장만 수행할 수 있습니다.
> - 이러한 레이블은 자동 레이블 지정 정책에서 지원되지 않으며 [보존 레이블 정책](create-apply-retention-labels.md)을 사용하여 적용해야 합니다.
>
> 또한 SharePoint에서 체크 아웃된 문서에는 규정 레이블을 적용할 수 없습니다.
>
> 이러한 제한 사항 및 취소할 수 없는 작업으로 인해 보존 레이블에 대해 이 옵션을 선택하기 전에 반드시 규정 레코드를 사용해야 하는지 확인합니다. 실수로 인한 구성을 방지하기 위해 이 옵션은 기본적으로 사용할 수 없지만 먼저 PowerShell을 사용하여 사용하도록 설정해야 합니다. [보존 레이블을 사용하여 레코드를 선언](declare-records.md)에 지침이 포함되어 있습니다.

## <a name="configuration-guidance"></a>구성 지침

[레코드 관리 시작하기](get-started-with-records-management.md)를 참조하세요. 이 문서에는 레코드 관리 시나리오에 대한 구독, 사용 권한 및 종단 내 구성 지침에 대한 정보가 들어 있습니다.