---
title: Microsoft Managed Desktop 및 ITIL
description: ITIL 단계와 Microsoft Managed Desktop 정보 및 문서의 상관 관계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: e545b64670bb92c40465f1c50b2cb46b9fd7a8d8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841438"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft Managed Desktop 및 ITIL

많은 조직에서는 [ITIL과](https://www.axelos.com/best-practice-solutions/itil)같은 공식화된 ITSM(IT 서비스 모델) 줄에 따라 IT 서비스를 구성하는 것이 매우 소중합니다. 

Microsoft Managed Desktop을 사용하면 조직이 공식화된 ITSM 모델의 여러 주요 측면을 준수할 수 있습니다. 이 문서에서는 ITIL을 예로 들어 일반적인 ITIL 단계와 프로세스, 해당하는 경우 동등한 Microsoft Managed Desktop 기능 간의 연결을 볼 수 있습니다. 이 정보는 조직의 Microsoft Managed Desktop 부분에만 적용됩니다.

ITIL 및 해당 단계 및 프로세스에 대한 자세한 내용은 해당 설명서를 [참조하세요.](https://www.axelos.com/best-practice-solutions/itil)


## <a name="service-design"></a>서비스 디자인

이 표에서는 주요 ITIL 단계 및 프로세스와 Microsoft Managed Desktop 기능과 관련이 있으며 자세한 내용은 설명서에 대한 링크를 제공합니다.



|ITIL 프로세스 |설명  |설명서 |
|---------|---------|---------|
|서비스 수준 관리     | 응답 시간은 관리자 지원 요청 및 인시던트에 대해 정의됩니다.  |  [Microsoft Managed Desktop의 관리자 지원](working-with-managed-desktop/admin-support.md)  |
|서비스 카탈로그 관리     | 서비스의 구성 요소를 자세히 설명하는 서비스 설명은 현재 및 관심 있는 모든 고객이 사용할 수 있는 서비스의 상태를 계속합니다.<br><br>서비스를 운영하는 데 필요한 사항을 이해하기 위해 자세히 설명된 선행 사항  | - [Microsoft Managed Desktop 서비스 설명](service-description/index.md)<br><br>- [Microsoft Managed Desktop에 등록 준비](get-ready/index.md)  |
|정보 보안 관리     | 서비스에 대한 정보 보안을 비롯한 보안 정보입니다.<br><br> 디바이스 구성 방법에 대한 보안 관련 정책 및 기타 정보   | - [Microsoft Managed Desktop의 보안](service-description/security.md)<br><br>- [장치 구성](service-description/device-policies.md)  |
|가용성 관리     |  Microsoft Managed Desktop은 서비스의 가용성을 보장하기 위해 조직과 책임의 균형을 조정합니다.<br><br>관리자와 사용자는 서비스 또는 가용성 문제가 있는 경우 각 지원에 대한 경로를 사용할 수 있습니다. | - [Microsoft Managed Desktop 작업 및 모니터링](service-description/operations-and-monitoring.md)<br><br>- [Microsoft Managed Desktop에 대한 관리자 지원](working-with-managed-desktop/admin-support.md)<br>- [사용자에 대한 도움말](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>서비스 전환


|ITIL 프로세스 |설명  |설명서 |
|---------|---------|---------|
|변경 관리     | 책임의 정의 균형, 프로세스 개요 및 사용 가능한 변경 관리와 관련된 유형.  | [Microsoft Managed Desktop 작업 및 모니터링](service-description/operations-and-monitoring.md#change-management) |
|릴리스 및 배포 관리     |  Microsoft Managed Desktop은 서비스에 등록된 장치에 대한 업데이트를 관리합니다.  | [Microsoft Managed Desktop에서 업데이트 처리 방법](service-description/updates.md)        |
|서비스 자산 및 구성 관리     | 조직의 Microsoft Managed Desktop 배포에 대한 정보는 IT 관리 포털에서 사용할 수 있습니다.  | [Microsoft Managed Desktop의 관리자 지원](working-with-managed-desktop/admin-support.md) |
|지식 관리     | Microsoft Managed Desktop 서비스에 대한 정보는 이 사이트에서 최신으로 유지됩니다.   | [Microsoft Managed Desktop 문서 변경 기록](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>서비스 작업


|ITIL 프로세스 |설명  |설명서  |
|---------|---------|---------|
|이벤트 관리     |  장치 모니터링에 대한 세부 정보가 제공됩니다.<br><br>Microsoft Managed Desktop 서비스에 대한 표준 운영 절차가 자세히 설명됩니다. |  - [Microsoft Managed Desktop의 보안](service-description/security.md)<br>- [Microsoft Managed Desktop 작업 및 모니터링](service-description/operations-and-monitoring.md)       |
|인시던트 관리  | Microsoft Managed Desktop은 정의된 심각도 정의에 따라 인시던트에 대해 조사하고 대응합니다.  |  [요청 심각도 정의 지원](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|요청 이행 관리     |  Microsoft Managed Desktop 서비스와 관련된 정보 요청 및 변경 요청에 대한 프로세스가 정의됩니다.         |[Microsoft Managed Desktop의 관리자 지원](working-with-managed-desktop/admin-support.md)         |
|문제 관리     | 서비스 관련 문제는 현재 로컬 계정 팀으로 연결해야 합니다. | 개발 설명서 |
|액세스 관리     | 기능에 대해 자세히 설명하기 위한 고객의 액세스 관리 구성 요소 및 책임  | [ID 및 액세스 관리](service-description/security.md#identity-and-access-management)        |
