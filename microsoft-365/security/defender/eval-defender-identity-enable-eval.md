---
title: Id에 대한 Microsoft Defender의 평가 환경 사용
description: 센서를 구성하고 Microsoft 365 Defender 로컬 관리자를 검색하여 Microsoft 365 Defender & 테스트 랩 또는 파일럿 환경에서 ID에 대한 Microsoft Defender를 설치합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6a89c0e9d9b8b66048ddd50ab967520987a152a9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192539"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a>Id에 대한 Microsoft Defender의 평가 환경 사용

**적용 대상:**
- Microsoft 365 Defender

이 문서는 Id에 대한 Microsoft Defender의 평가 환경을 설정하는 프로세스의 [2단계](eval-defender-identity-overview.md) 중 2단계입니다. 이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-identity-overview.md)

다음 단계에 따라 ID용 Microsoft Defender 환경을 설정할 수 있습니다. 

![Microsoft Defender 평가 환경에서 Id에 대해 Microsoft Defender를 사용하도록 설정하는 단계입니다.](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [1단계. ID 인스턴스에 대한 Defender 설정](#step-1-set-up-the-defender-for-identity-instance)
- [2단계. 센서 설치 및 구성](#step-2-install-and-configure-the-sensor)
- [3단계. 센서가 있는 컴퓨터의 이벤트 로그 및 프록시 설정 구성](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [4단계. Id에 Defender를 허용하여 다른 컴퓨터에서 로컬 관리자 식별](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a>1단계. ID 인스턴스에 대한 Defender 설정

ID용 Defender 포털에 로그인하여 인스턴스를 만든 다음 이 인스턴스를 Active Directory 환경에 연결합니다. 

|  |단계     |추가 정보  |
|---------|---------|---------|
|1     | ID용 Defender 인스턴스 만들기        | [빠른 시작: Microsoft Defender for Identity 인스턴스 만들기](/defender-for-identity/install-step1)        |
|2     | 커넥트 대한 Defender 인스턴스를 Active Directory 포리스트에 추가   | [빠른 시작: 커넥트 포리스트로 설정](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a>2단계. 센서 설치 및 구성

다음으로, 도메인 컨트롤러 및 AD FS 서버의 ID에 대한 Defender 센서를 다운로드, 설치 및 구성합니다.

|  |단계     |추가 정보  |
|---------|---------|---------|
|1     | 필요한 ID 센서에 대한 Microsoft Defender 수를 결정 합니다.        | [Microsoft Defender for Identity 용량 계획](/defender-for-identity/capacity-planning)   |
|2     | 센서 설치 패키지 다운로드  |  [빠른 시작: Id용 Microsoft Defender 센서 설정 패키지 다운로드](/defender-for-identity/install-step3)   |
|3      | Id용 Defender 센서 설치    |  [빠른 시작: Id용 Microsoft Defender 센서 설치](/defender-for-identity/install-step4)       |
|4      | 센서 구성       |  [Id에 대한 Microsoft Defender 센서 설정 구성 ](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a>3단계. 센서가 있는 컴퓨터의 이벤트 로그 및 프록시 설정 구성

센서를 설치한 컴퓨터의 경우 Windows 로그 수집 및 인터넷 프록시 설정을 구성하여 검색 기능을 사용하도록 설정하고 향상합니다.

|  |단계     |추가 정보  |
|---------|---------|---------|
|1     | 이벤트 Windows 컬렉션 구성         | [이벤트 Windows 구성](/defender-for-identity/configure-windows-event-collection)        |
|2     | 인터넷 프록시 설정 구성        | [Id 센서에 대한 Microsoft Defender에 대한 끝점 프록시 및 인터넷 연결 설정 구성](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a>4단계. Id에 Defender를 허용하여 다른 컴퓨터에서 로컬 관리자 식별

Id 측면 이동 경로 검색을 위한 Microsoft Defender는 특정 컴퓨터의 로컬 관리자를 식별하는 쿼리를 사용 합니다. 이러한 쿼리는 ID 서비스용 Defender 계정을 사용하여 SAM-R 프로토콜을 사용하여 수행됩니다. 

Windows 클라이언트 및 서버에서 ID용 Defender 계정이 SAM-R을 수행할 수 있도록 허용하려면 네트워크 액세스 정책에 나열된 구성된 계정 외에도 ID용 Defender 서비스 계정을 추가하도록 그룹 정책을 수정해야 합니다. 도메인 컨트롤러를 제외한 모든 컴퓨터에 그룹 **정책을 적용해야 합니다.**

이 작업을 하는 방법에 대한 지침은 SAM에 대한 원격 호출을 하도록 [Id에 대한 Microsoft Defender 구성을 참조하세요.](/defender-for-identity/install-step8-samr) 

## <a name="next-steps"></a>다음 단계

3단계 중 3단계: [Id에 대한 Microsoft Defender 파일럿](eval-defender-identity-pilot.md)

ID에 대한 [Microsoft Defender 평가 개요로 돌아가기](eval-defender-identity-overview.md)

평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)