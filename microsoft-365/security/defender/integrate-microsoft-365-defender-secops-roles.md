---
title: 4단계. Microsoft 365 Defender 역할, 책임 및 감독 정의
description: 보안 작업에 역할을 통합할 때 역할, 책임 및 감독을 Microsoft 365 Defender 기본입니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, microsoft, Microsoft 365, 인시던트 대응, 사이버 공격, 보안 운영, soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 597550afd40f61ad40b52ed8c9651109a523bb1d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197992"
---
# <a name="step-4-define-microsoft-365-defender-roles-responsibilities-and-oversight"></a>4단계. Microsoft 365 Defender 역할, 책임 및 감독 정의

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

조직은 운영 역할을 정의하기 전에 Microsoft 365 Defender, 구성 및 관리에 대한 소유권과 책임이 초기 작업으로 설정되어야 합니다. 일반적으로 라이선스, 구독 비용 및 Microsoft 365 및 Enterprise EMS(Security + Mobility) 서비스(Microsoft 365 Defender 포함)의 소유권은 SOC(보안 운영 센터) 팀 외부에 있습니다. SOC 팀은 해당 개인과 함께 작업하여 해당 개인의 적절한 감독을 Microsoft 365 Defender. 

대부분의 최신 SOC는 팀 구성원이 자신의 기술et 및 기능에 따라 범주에 할당합니다. 예제:

- 위협 및 분석 기능의 수명 주기 관리와 관련된 작업에 할당된 위협 인텔리전스 팀.
- 로그, 경고, 이벤트 및 모니터링 기능을 유지 관리하는 SOC 분석가로 구성된 모니터링 팀입니다.
- 보안 & 최적화하는 데 배정된 엔지니어링 운영 팀

사용자에 대한 SOC 팀 역할 및 Microsoft 365 Defender 자연스럽게 이러한 팀에 통합됩니다.

다음 표에서는 각 SOC 팀의 역할 및 책임과 각 역할이 각 역할과 통합되는 방법을 Microsoft 365 Defender.

| SOC 팀 | 역할 및 책임 | Microsoft 365 Defender 작업  |
|:-------|:-----|:-------|
| SOC 감독 | <ul><li>SOC 거버넌스 수행</li><li>일별, 주별, 월별 프로세스 설정</li><li>교육 및 인식 제공</li><li>직원 고용, 피어 그룹 및 모임에 참여</li><li>파랑, 빨간색, 자주색 팀 연습 수행</ul>  | <ul><li>Microsoft 365 Defender 포털 액세스 제어</li><li>기능/URL 및 라이선스 업데이트 레지스터 유지 관리</li><li>IT, 법률, 규정 준수 및 개인 정보 관련자와의 통신 유지 관리</li><li>새로운 Microsoft 365 또는 Microsoft Azure 변경 제어 모임에 참가합니다.</ul> |
| 위협 인텔리전스 & 분석  | <ul><li>위협 인텔리전스 피드 관리</li><li>바이러스 및 맬웨어 기여</li><li>위협 & 분류</li><li>Insider 위협 특성 개발 </li><li>위협 인텔과 위험 관리 프로그램 통합</li><li>HR, 법률, IT 및 보안 팀에 데이터 과학, BI 및 분석과 데이터 인사이트를 통합합니다.<ul> | <ul><li>Id 위협 모델링을 위한 Microsoft Defender 유지 관리</li><li>위협 모델링을 위한 Microsoft Defender Office 365 유지 관리</li><li>Endpoint 위협 모델링을 위한 Microsoft Defender 유지 관리</ul> |
| 모니터링 | <ul><li>계층 1, 2, 3 분석가</li><li>로그 원본 유지 관리 및 엔지니어링</li><li>데이터 원본 수집 </li><li>SIEM 구문 분석, 경고, 상관 관계, 최적화</li><li>이벤트 및 경고 생성</li><li>이벤트 및 경고 분석</li><li>이벤트 및 경고 보고</li><li>티켓 시스템 유지 관리</ul> | 용도: <ul><li>보안 및 준수 센터</li><li>Microsoft 365 Defender 포털</ul> |
| SecOps & 엔지니어링 | <ul><li>앱, 시스템 및 끝점에 대한 취약성 관리</li><li>XDR/SOAR 자동화</li><li>준수 테스트</li><li>피싱 및 DLP 엔지니어링</li><li>엔지니어링</li><li>좌표 변경 컨트롤</li><li>좌표 런북 업데이트</li><li>침투 테스트<ul> | <ul><li>Microsoft Cloud App Security</li><li>엔드포인트용 Defender</li><li>ID용 Defender</ul> |
| CSIRT(컴퓨터 보안 인시던트 대응 팀) | <ul><li>사이버 인시던트 조사 및 대응</li><li>포렌식 수행</li><li>**SOC에서 격리되는 경우가 자주 있습니다.**</ul> | 인시던트 대응 Microsoft 365 Defender 공동 작업 및 유지 관리 |
||||


## <a name="next-step"></a>다음 단계

[5단계. 사용 사례 개발 및 테스트](integrate-microsoft-365-defender-secops-use-cases.md)
