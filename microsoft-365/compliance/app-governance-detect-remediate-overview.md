---
title: 앱 위협 감지 및 수정에 대해 알아보기
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 앱 위협 감지 및 수정에 대해 알아봅니다.
ms.openlocfilehash: 0812615a8a0ed78f0649a59a0f884f1c37a9e368
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59190062"
---
# <a name="learn-about-app-threat-detection-and-remediation"></a>앱 위협 감지 및 수정에 대해 알아보기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

Microsoft 앱 거버넌스를 사용하면 다음을 수행할 수 있습니다.

- 사용자가 만든 활성 앱 정책이 생성하는 악의적인 앱 활동 및 정책 기반 경고를 기반으로 기본 제공 앱 거버넌스 탐지 방법이 생성하는 위협 경고를 쉽게 모니터링합니다. 이러한 경고는 앱 작업이 비정상적이며 비준수, 악성 또는 위험한 앱을 사용하고 있음을 나타냅니다.  경고의 패턴을 사용하여 새 앱 정책을 만들거나 보다 제한적인 작업을 위해 기존 정책의 설정을 수정할 수 있습니다.
- 경고는 조사 후 수동으로 또는 활성 앱 정책의 작업 설정을 통해 자동으로 쉽게 수정할 수 있습니다.


>[!Note]
>Microsoft 365 리소스에 액세스할 수 있는 권한이 부여되지 않은 Azure 전용 앱의 비정상적인 활동은 앱 거버넌스 검색 및 경고에 포함되지 않습니다.
>

어떤 역할이 앱 거버넌스 페이지에 액세스할 수 있는지는 [관리자 역할](app-governance-get-started.md#administrator-roles)을 참조하세요.


## <a name="app-governance-integration-with-azure-active-directory-and-microsoft-cloud-app-security"></a>Azure Active Directory 및 Microsoft Cloud App Security를 사용하여 앱 거버넌스 통합

앱 거버넌스, Azure Active Directory(Azure AD) 및 Microsoft Cloud App Security는 다양한 데이터 집합을 수집하여 제공합니다.

- App Governance는 API 레벨에서 앱의 활동에 대한 자세한 정보를 제공합니다.
- Azure AD는 앱 로그인에 대한 기본 앱 메타데이터와 세부 정보를 제공합니다.
- Microsoft Cloud App Security는 앱 위험 정보를 제공합니다.

앱 거버넌스, Azure AD 및 Microsoft Cloud App Security 전반에서 정보를 공유하면 한 포털에 집계 정보를 표시하고 다른 포털에 연결하여 자세한 정보를 확인할 수 있습니다. 다음은 몇 가지 예입니다.

- 애플리케이션 거버넌스의 애플리케이션 로그인 정보:

  애플리케이션 거버넌스 포털에서 각 애플리케이션에 대해 집계된 로그인 작업을 확인하고 Azure Active Directory 관리 센터에 다시 연결하여 로그인 이벤트에 대한 세부 정보를 확인할 수 있습니다.

- Microsoft Cloud App Security 포털의 API 사용량 정보: 

  Microsoft Cloud App Security 포털에서 API 사용 수준 및 Aggregate 데이터 전송을 확인하고 애플리케이션 거버넌스 포털에 연결하여 자세한 내용을 확인할 수 있습니다.

다음은 통합에 대한 요약입니다.

![애플리케이션 거버넌스를 Azure AD 및 Microsoft Cloud App Security와 통합합니다.](..\media\manage-app-protection-governance\mapg-integration.png)

또한 앱 거버넌스는 앱 기반 보안 인시던트에 대한 자세한 분석을 위해 경고를 Microsoft Cloud App Security 및 Microsoft 365 Defender에 신호로 보냅니다.

<!--

CFA #3 Scenario 1:  As an admin, I can investigate alerts associated to my M365 apps through MAPG.
CFA #3 Scenario 2: As an admin, I can manually remediate 
CFA #3 Scenario 3: As an admin, I can configure policies to perform automatic 
--> 

## <a name="next-step"></a>다음 단계

[앱 위협 탐지 및 수정을 시작합니다.](app-governance-detect-remediate-get-started.md)
