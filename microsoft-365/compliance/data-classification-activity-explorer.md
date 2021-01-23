---
title: 활동 탐색기 시작하기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 활동 탐색기는 사용자가 레이블이 지정된 콘텐츠에 대해 수행하는 작업을 확인하고 필터링하여 데이터 분류 기능을 자세히 설명합니다.
ms.openlocfilehash: 6825c00373617011db28fa484f272086f887ea40
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921636"
---
# <a name="get-started-with-activity-explorer"></a>활동 탐색기 시작하기

데이터 분류 개요 및 콘텐츠 탐색기 탭을 통해 검색된 후 레이블이 지정된 콘텐츠와 해당 콘텐츠의 위치를 확인할 수 있습니다. 활동 탐색기는 사용자가 레이블이 지정된 콘텐츠로 수행한 작업을 모니터링할 수 있도록 하여 이 기능 제품군을 자세히 설명합니다. 활동 탐색기는 기록 보기를 제공합니다.

![자리 표시자 스크린샷 개요 활동 탐색기](../media/data-classification-activity-explorer-1.png)

사용할 수 있는 30개가 넘는 여러 가지 필터가 있습니다. 예를 들면:

- 날짜 범위
- 활동 유형
- 위치
- 사용자
- 민감도 레이블
- 보존 레이블
- 파일 경로
- DLP 정책


## <a name="prerequisites"></a>필수 구성 요소

테이터 분류에 액세스하고 이를 사용하는 모든 계정에는 다음 구독 중 하나에서 할당된 라이선스가 있어야 합니다.

- Microsoft 365 (E5)
- Office 365 (E5)
- 고급 규정 준수 (E5) 추가 기능
- 고급 위협 인텔리전스 (E5) 추가 기능
- Microsoft 365 E5/A5 정보 보호 및 거버넌스
- Microsoft 365 E5/A5 규정 준수

### <a name="permissions"></a>권한

 활동 탐색기 탭에 액세스하려면 계정에 다음 역할이나 역할 그룹 중 하나의 구성원 자격이 할당되어야 합니다.

**Microsoft 365 역할 그룹**

- 전역 관리자
- 준수 관리자
- 보안 관리자
- 규정 준수 데이터 관리자

## <a name="activity-type"></a>활동 유형

Microsoft 365는 SharePoint Online, OneDrive에서 다음과 같은 유형의 활동을 모니터링하고 보고합니다.

- 레이블을 적용함
- 레이블을 변경함(업그레이드, 다운그레이드 또는 제거함)
- 자동 레이블 지정 시뮬레이션

중요 레이블이 지정된 콘텐츠에 어떤 작업이 수행되고 있는지 파악하면 사용자가 이미 적용한 제어(예: [데이터 손실 방지 정책](data-loss-prevention-policies.md))이 유효한지를 파악할 수 있다는 이점이 있습니다. 그렇지 않고, 많은 수의 항목이 `highly confidential` 레이블이 지정되었다가 `general`로 다운그레이드되는 것과 같은 예기치 않은 상황이 발생하는 경우, 다양한 정책을 관리하고 새로운 작업을 수행하여 원치 않은 동작을 제한할 수 있습니다.

> [!NOTE]
> 현재 활동 탐색기에서는 Exchange Online의 보존 활동을 모니터링하고 있지 않습니다.

## <a name="see-also"></a>참고 항목
- [민감도 레이블에 대해 알아보기](sensitivity-labels.md)
- [보존 정책 및 보존 레이블에 대해 알아보기](retention.md)
- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)

