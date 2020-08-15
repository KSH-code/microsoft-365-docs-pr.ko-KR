---
title: 레코드에 대해 알아보기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 마이크로소프트 365에서 레코드 관리 솔루션을 구현하는 데 도움이 되는 레코드에 대해 알아봅니다.
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685444"
---
# <a name="learn-about-records"></a>레코드에 대해 알아보기

>*[보안 및 규정 준수에 대한 Microsoft 365 라이센스 지침](https://aka.ms/ComplianceSD).*

Microsoft 365의 레코드 관리를 통해 조직은 회사 정책 및 법적 고지 사항 또는 규제 의무를 준수하는 동시에 위험과 법적 책임을 줄일 수 있습니다.

콘텐츠가 레코드로 표시되는 경우:

- 항목에는 [허용 또는 차단되는 작업](#compare-restrictions-for-what-actions-are-allowed-or-blocked)에 대한 제한 사항이 적용됩니다.

- 항목에 대한 추가 활동이 기록됩니다.

- 보존 기간 종료 시에 항목이 삭제되는 경우 처리 증명을 가집니다.

[보존 레이블](retention.md#retention-labels)을 사용하여 콘텐츠를 레코드로 표시합니다. 사용자 및 관리자가 콘텐츠에 직접 적용할 수 있도록 해당 레이블을 게시하거나 레코드로 표시하기를 원하는 콘텐츠에 해당 레이블을 자동으로 적용할 수 있습니다.

보존 레이블을 사용하여 레코드를 콘텐츠로 표시하면 Microsoft 365 환경에서 일관된 단일 레코드 관리 전략을 구현할 수 있습니다.

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>허용 또는 차단되는 작업에 대한 제한 사항 비교

다음 표를 사용하여 표준 보존 레이블을 적용한 결과로 콘텐츠를 표시되는 제한 사항과 콘텐츠를 레코드로 표시하는 보존 레이블을 확인합니다. 

표준 보존 레이블에는 콘텐츠를 레코드로 표시하지 않고 데이터를 보존하는 구성이 있습니다.

>[!NOTE] 
> 자세한 내용을 제공하기 위해 표에는 SharePoint 및 OneDrive에는 적용되지만 Exchange에는 적용되지 않는 잠긴 레코드와 잠금이 해제된 레코드에 대한 열이 포함되어 있습니다. 레코드를 잠그거나 잠금 해제하는 기능은 Exchange 항목에서는 지원되지 않는 [레코드 버전 관리](record-versioning.md)를 사용합니다. 따라서 레코드로 표시되는 모든 Exchange 항목의 경우 해당 동작이 **레코드 - 잠금** 열에는 해당되지만 **레코드 - 잠금 해제됨** 열은 해당되지 않습니다.


|작업| 보존 레이블 |레코드 - 잠금| 레코드 - 잠금 해제됨|
|:-----|:-----|:-----|:-----|:-----|
|콘텐츠 편집|허용됨 | **차단됨** | 허용됨|
|속성 편집(이름 바꾸기 포함)|허용됨 |허용됨 | 허용됨|
|삭제|허용됨<sup>1</sup> |**차단됨** | **차단됨**|
|복사|허용됨 |허용됨 | 허용됨|
|컨테이너 내에서 이동<sup>2</sup>|허용됨 |허용됨 | 허용됨|
|컨테이너 간에 이동<sup>2</sup>|허용됨 |잠금이 해제되지 않은 경우 허용됨 | 허용됨|
|열기/읽기|허용됨 |허용됨 | 허용됨|
|레이블 변경|허용됨 |허용됨 - 컨테이너 관리자 전용 | 허용됨 - 컨테이너 관리자 전용|
|레이블 제거|허용됨 |허용됨 - 컨테이너 관리자 전용 | 허용됨 - 컨테이너 관리자 전용|

각주:

<sup>1</sup> 복사본이 안전한 위치에 유지되지만 SharePoint에 의해 차단되므로 OneDrive 및 Exchange에서 지원됩니다.

사용자가 SharePoint에서 레이블이 지정된 문서를 삭제하려고 할 때 표시되는 메시지:

![SharePoint에서 항목이 삭제되지 않았다는 메시지](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<sup>2</sup> 컨테이너에는 SharePoint 문서 라이브러리와 Exchange 사서함이 포함됩니다.

## <a name="next-steps"></a>다음 단계

아직 레코드 관리에 사용할 보존 레이블이 아직 없는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.

콘텐츠를 레코드로 표시하려면 [보존 레이블을 사용하여 레코드 삭제](declare-records.md)를 참조합니다.
