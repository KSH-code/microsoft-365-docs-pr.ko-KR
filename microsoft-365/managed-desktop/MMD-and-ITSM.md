---
title: Microsoft Managed Desktop 및 ITIL
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, ITISM
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 05bd5a2ee36633b7ccf9ae61e601988a7268bb2c
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289808"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft Managed Desktop 및 ITIL

대부분의 조직은 IT 서비스를 [ITIL](https://www.axelos.com/best-practice-solutions/itil)과 같은 공식화 된 It 서비스 모델 (itsm) 줄에 따라 구조화 하는 것이 귀중 하다 고 알게 되었습니다. 

Microsoft Managed Desktop을 사용 하면 조직에서 이러한 형식화 된 SM 모델의 여러 주요 측면을 준수할 수 있습니다. 이 항목에서는 ITIL을 사용 하 여 일반적인 ITIL 단계와 프로세스 및 동등한 Microsoft 관리 데스크톱 기능 간의 연결을 확인할 수 있습니다 (해당 되는 경우). 이는 조직의 Microsoft Managed Desktop 부분에만 적용 됩니다.

ITIL 및 해당 단계 및 프로세스에 대 한 자세한 내용은 해당 [설명서](https://www.axelos.com/best-practice-solutions/itil)를 참조 하세요.


## <a name="service-design"></a>서비스 디자인

이 표에서는 주요 ITIL 단계와 프로세스에 대해 설명 하 고 세부 정보를 제공 하는 문서에 대 한 링크를 제공 합니다.



|ITIL 프로세스 |설명  |설명서 |
|---------|---------|---------|
|서비스 수준 관리     | 응답 시간은 관리자 지원 요청 및 인시던트에 대해 정의 됩니다.  |  [Microsoft Managed Desktop의 관리자 지원](working-with-managed-desktop/admin-support.md)  |
|서비스 카탈로그 관리     | 서비스 설명 서비스의 구성 요소 세부 정보는 모든 현재 및 관심이 있는 고객에 게 제공 되는 서비스의 상태로 유지 됩니다.<br><br>서비스를 운영 하는 데 필요한 사항을 이해 하기 위한 필수 구성 요소입니다.  | - [Microsoft Managed Desktop 서비스 설명](service-description/index.md)<br><br>- [Microsoft Managed Desktop의 등록 준비](get-ready/index.md)  |
|정보 보안 관리     | 서비스에 대 한 정보 보안을 포함 한 보안 정보<br><br> 보안 관련 정책 및 장치를 구성 하는 방법에 대 한 기타 정보   | - [Microsoft Managed Desktop의 보안](service-description/security.md)<br><br>- [장치 구성](service-description/device-policies.md)  |
|가용성 관리     |  Microsoft Managed Desktop 잔액이 조직과의 가용성을 보장 하는 데 사용 됩니다.<br><br>관리자 및 사용자는 서비스 또는 가용성 문제가 발생 하는 경우 각 지원에 대 한 경로를 보유 합니다. | - [Microsoft Managed Desktop 작업 및 모니터링](service-description/operations-and-monitoring.md)<br><br>- [Microsoft Managed Desktop에 대 한 관리자 지원](working-with-managed-desktop/admin-support.md)<br>- [사용자를 위한 도움말 보기](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>서비스 전환


|ITIL 프로세스 |설명  |설명서 |
|---------|---------|---------|
|변경 관리     | 사용 가능한 변경 관리와 관련 된 책임, 프로세스 개요 및 유형의 균형을 정의 합니다.  | [Microsoft Managed Desktop 작업 및 모니터링](service-description/operations-and-monitoring.md#change-management) |
|릴리스 및 배포 관리     |  Microsoft Managed Desktop은 서비스에 등록 된 장치에 대 한 업데이트를 관리 합니다.  | [Microsoft Managed Desktop에서 업데이트를 처리 하는 방법](service-description/updates.md)        |
|서비스 자산 및 구성 관리     | 조직의 Microsoft Managed Desktop 배포에 대 한 정보는 IT 관리자 포털에서 확인할 수 있습니다.  | [Microsoft Managed Desktop의 관리자 지원](working-with-managed-desktop/admin-support.md) |
|지식 관리     | Microsoft Managed Desktop service의 정보는이 사이트에서 최신 상태로 유지 됩니다.   | [Microsoft Managed Desktop 문서 변경 기록](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>서비스 작업


|ITIL 프로세스 |설명  |설명서  |
|---------|---------|---------|
|이벤트 관리     |  장치 모니터링에 대 한 세부 정보가 제공 됩니다.<br><br>Microsoft Managed Desktop service의 표준 운영 절차에 대해 자세히 설명 합니다. |  - [Microsoft Managed Desktop의 보안](service-description/security.md)<br>- [Microsoft Managed Desktop 작업 및 모니터링](service-description/operations-and-monitoring.md)       |
|사건 관리  | Microsoft Managed Desktop은 정의 된 심각도 정의에 따라 인시던트를 조사 하 고 조치를 취할 수 있습니다.  |  [요청 심각도 정의 지원](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|요청 처리 관리     |  Microsoft Managed Desktop service와 관련 된 정보 및 변경 요청에 대 한 요청 프로세스를 정의 합니다.         |[Microsoft Managed Desktop의 관리자 지원](working-with-managed-desktop/admin-support.md)         |
|문제 관리     | 서비스 관련 문제는 지금 로컬 계정 팀으로 연결 해야 합니다. | 개발 설명서 |
|Access 관리     | 고객이 기능에 대해 자세히 확인할 수 있는 관리 구성 요소 및 책임에 액세스 합니다.  | [ID 및 액세스 관리](service-description/security.md#identity-and-access-management)        |
