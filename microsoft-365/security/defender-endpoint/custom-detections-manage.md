---
title: Microsoft Defender ATP에서 사용자 지정 검색 규칙 보기 및 관리
ms.reviewer: ''
description: 사용자 지정 검색 규칙을 보고 관리하는 방법 학습
keywords: 사용자 지정 검색, 보기, 관리, 경고, 편집, 요청 시 실행, 감지 규칙, 고급 헌팅, 헌트, 쿼리, 응답 작업, mdatp, Microsoft Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f6a7fc4d4141b19f9c5129eea9b89943d07695b2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165780"
---
# <a name="view-and-manage-custom-detection-rules"></a>사용자 지정 검색 규칙 보기 및 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

기존 사용자 지정 검색 [규칙을 관리하여](custom-detection-rules.md) 위협을 효과적으로 찾아 조치를 취하도록 합니다. 규칙 목록을 보고, 이전 실행을 확인하고, 트리거한 경고를 검토하는 방법을 탐색합니다. 필요한 경우 규칙을 실행하고 수정할 수도 있습니다.

## <a name="required-permissions"></a>필요한 사용 권한

사용자 지정 검색을 만들거나 관리하려면 역할에 보안 설정 관리 **권한이 필요합니다.** [](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)

## <a name="view-existing-rules"></a>기존 규칙 보기

모든 기존 사용자 지정 검색 규칙을 보기 위해 설정 **사용자** 지정  >  **검색으로 이동합니다.** 이 페이지에는 다음 실행 정보가 있는 모든 규칙이 나열됩니다.

- **마지막 실행**- 쿼리 일치를 확인하고 경고를 생성하기 위해 규칙을 마지막으로 실행한 경우
- **마지막 실행 상태**- 규칙이 성공적으로 실행된지 여부
- **다음 실행**-다음 예약된 실행
- **상태**- 규칙이 켜져 있는지 여부

## <a name="view-rule-details-modify-rule-and-run-rule"></a>규칙 세부 정보 보기, 규칙 수정 및 규칙 실행

사용자 지정 검색 규칙에 대한 포괄적인 정보를 표시하려면 설정 사용자 지정 검색의 규칙 목록에서 규칙  >  **이름을 선택합니다.** 선택한 규칙에 대한 페이지에는 다음 정보가 표시됩니다.

- 경고, 실행 상태 및 범위 세부 정보를 포함하여 규칙에 대한 일반 정보
- 트리거된 경고 목록
- 트리거된 작업 목록

![사용자 지정 검색 규칙 페이지](images/atp-custom-detection-rule-details.png)<br>
*사용자 지정 검색 규칙 페이지*

이 페이지에서 규칙에 대해 다음 작업을 수행할 수 있습니다.

- **를** 실행하여 규칙을 즉시 실행합니다. 이 작업을 수행하면 다음 실행 간격도 다시 설정됩니다.
- **편집**- 쿼리를 변경하지 않고 규칙 수정
- **쿼리 수정**-고급 헌팅에서 쿼리 편집
- **켜기**  /  **끄기**-규칙 사용 또는 실행 중지
- **삭제**- 규칙을 끄고 제거

>[!TIP]
>정보를 빠르게 보고 표의 항목에 대한 작업을 수행하기 위해 표 왼쪽에 있는 [&#10003;] 열을 사용하세요.

## <a name="related-topics"></a>관련 항목
- [사용자 지정 검색 개요](overview-custom-detections.md)
- [검색 규칙 만들기](custom-detection-rules.md)
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [경고 보기 및 구성](alerts-queue.md)
