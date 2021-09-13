---
title: 사용자에 대해 평가 환경을 Microsoft Cloud App Security
description: Microsoft Defender에서 MICROSOFT Defender의 아키텍처를 Office 365 제품 간의 상호 작용을 Microsoft 365 Defender 이해합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1b5e664e6675b477ecb2507fd52588aa159bcc9b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189292"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a>사용자에 대해 평가 환경을 Microsoft Cloud App Security


**적용 대상:**

- Microsoft 365 Defender

이 문서는 사용자 환경의 평가 환경을 설정하는 프로세스의 [2단계](eval-defender-mcas-overview.md) 중 Microsoft Cloud App Security. 이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-mcas-overview.md)

이 문서에서는 Cloud App Security 포털에 액세스하고 클라우드 앱 트래픽 데이터를 수집하는 데 필요한 통합을 구성하는 프로세스를 진행하는 과정을 진행합니다.

환경에서 사용되는 클라우드 앱을 검색하기 위해 다음 중 하나 또는 둘 다를 할 수 있습니다.

- 끝점용 Microsoft Defender와 통합하여 클라우드 검색을 빠르게 시작하고 실행합니다. 이 네이티브 통합을 통해 네트워크의 모든 디바이스에서 클라우드 트래픽에 Windows 10 즉시 데이터를 수집할 수 있습니다.
- 네트워크에 연결된 모든 장치에서 액세스하는 모든 클라우드 앱을 검색하려면 방화벽 및 기타 Cloud App Security 로그 수집기 배포합니다. 그러면 끝점에서 데이터를 수집하여 분석하기 위해 Cloud App Security 전송합니다. Cloud App Security 기능을 위해 기본적으로 일부 타사 Proxies와 통합됩니다.

이 문서에는 두 방법 모두에 대한 지침이 포함되어 있습니다.

다음 단계에 따라 설치 Microsoft Cloud App Security.

![Microsoft Defender 평가 환경에서 Microsoft Microsoft Cloud App Security 사용하도록 설정하는 단계입니다.](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [1단계. 커넥트 포털에 Cloud App Security 수 있습니다.](#step-1-connect-to-the-cloud-app-security-portal)
- [2단계. 끝점용 Microsoft Defender와 통합](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [3단계. 방화벽 및 Cloud App Security 로그 수집기 배포](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [4단계. 클라우드 검색 대시보드를 확인하여 조직에서 사용되는 앱 확인](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a>1단계. 커넥트 포털에 Cloud App Security 수 있습니다.

라이선스를 확인하고 Cloud App Security 연결하기 위해 빠른 [시작:](/cloud-app-security/getting-started-with-cloud-app-security)시작을 Microsoft Cloud App Security. 

포털에 즉시 연결할 수 없는 경우 방화벽의 허용 목록에 IP 주소를 추가해야 할 수 있습니다. 에 [대한 기본 설정을 Cloud App Security.](/cloud-app-security/general-setup)

그래도 문제가 있는 경우 네트워크 요구 [사항을 검토하세요.](/cloud-app-security/network-requirements)

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>2단계. 끝점용 Microsoft Defender와 통합

Microsoft Cloud App Security Microsoft Defender for Endpoint와 기본적으로 통합됩니다. 이러한 통합은 클라우드 검색의 롤아웃을 간소화하고, 회사 네트워크를 넘어 클라우드 검색 기능을 확장하며, 장치 기반 조사를 가능하게 합니다. 이러한 통합은 IT 관리 디바이스에서 클라우드 앱 및 서비스에 액세스하는 Windows 10 있습니다. 

끝점에 대해 Microsoft Defender를 이미 설정한 경우 Cloud App Security 통합을 구성하는 것이 Microsoft 365 Defender. 통합이 켜진 후 클라우드 검색 대시보드에서 Cloud App Security 포털로 돌아가서 다양한 데이터를 볼 수 있습니다.

이러한 작업을 수행하기 위해 [Microsoft Defender for Endpoint와](/cloud-app-security/mde-integration)Microsoft Cloud App Security. 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a>3단계. 방화벽 및 Cloud App Security 로그 수집기 배포

네트워크에 연결된 모든 디바이스에서 적용 범위를 확인하려면 방화벽 및 기타 Cloud App Security 로그 수집기 를 배포하여 끝점에서 데이터를 수집하고 분석을 위해 Cloud App Security 전송합니다. 

다음 SWG(Secure Web Gateways) 중 하나를 사용하는 경우 Cloud App Security 통합을 제공합니다.
- Zscaler
- iboss
- 코라타
- Menlo Security

이러한 네트워크 장치와의 통합에 대한 자세한 내용은 클라우드 검색 설정 [을 참조하세요.](/cloud-app-security/set-up-cloud-discovery) 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>4단계. 클라우드 검색 대시보드를 확인하여 조직에서 사용되는 앱 확인

클라우드 검색 대시보드는 조직에서 클라우드 앱이 사용되는 방식에 대한 더 많은 정보를 제공하도록 디자인됩니다. 사용되는 앱 종류, 열린 경고 및 조직의 앱 위험 수준에 대한 간략한 개요를 제공합니다. 

클라우드 검색 대시보드 사용을 시작하고 검색된 앱 작업을 [참조하세요.](/cloud-app-security/discovered-apps)

## <a name="next-steps"></a>다음 단계

3단계 중 3단계: [파일럿 Microsoft Cloud App Security](eval-defender-mcas-pilot.md)

평가용 [개요로 Microsoft Cloud App Security](eval-defender-mcas-overview.md)

평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)