---
title: Microsoft Managed Desktop 및 Windows 11
description: 서비스에서 Windows 11을 사용할 수 있는 방법 및 경우
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7a99ca8d5f56fd5614dc27e3a28efe905ba30e46
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215402"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Microsoft Managed Desktop 및 Windows 11

Windows 11이 발표된 후 Windows 장치를 최신으로 유지하기 위한 노력의 일환으로 Windows 10 11 마이그레이션 계획을 세우기 시작한 것일 수 있습니다. 이 문서에서는 중요한 고려 사항과 환경의 원활한 Microsoft Managed Desktop 지원할 방법에 대해 간략하게 설명하고 있습니다. 11 자체에 Windows 대한 자세한 내용은 Windows [11 개요를 참조하세요.](/windows/whats-new/windows-11)

Microsoft Managed Desktop 디바이스에 Windows 11을 설치하기 위해 따라야 하는 특정 단계는 Windows [11에서](../working-with-managed-desktop/test-win11-mmd.md)미리 보기 및 Microsoft Managed Desktop.

## <a name="timeline-for-windows-11"></a>Windows 시간 표시 막대 11

Windows 11 preview 빌드는 2021년 6월 28일부터 Windows [프로그램 을 통해](/windows-insider/)사용할 수 있습니다. 2021년 말에 릴리스 빌드를 일반적으로 사용할 수 있을 것으로 예상됩니다.

디바이스에서 미리 보기 빌드를 관리하는지 여부에 Microsoft Managed Desktop 있습니다. 엔터프라이즈 지원이 종료될 때까지 Windows 10 계속 지원할 계획입니다. 수명 [주기 Windows 10 릴리스](/windows/release-health/release-information) 정보를 참조하세요.

일반적으로 Windows 11을 사용할 수 있는 경우 더 많은 유효성 검사 테스트를 수행하게 됩니다. 표준 배포 그룹을 통해 Windows 11이 Microsoft Managed Desktop 2022년 1월에 제공될 것으로 예상됩니다.

기술 준비 상태 및 비즈니스 고려 사항을 기반으로 각 테넌트에 대한 마이그레이션 계획을 개발하고 구현하기 위해 관리자에게 문의하고 권고합니다.

## <a name="assessing-pre-release-versions-of-windows-11"></a>11 버전의 Windows 평가

Microsoft Managed Desktop 장치의 95% 이상이 Windows 11을 사용할 수 있으므로 프로덕션 배포 전에 테스트 장치에서 업그레이드를 미리 볼 수 있습니다. 11개 Windows 요구 사항에 대한 자세한 내용은 Windows [11 요구 사항 을 참조하세요.](/windows/whats-new/windows-11-requirements) 디바이스의 자격 상태에 대한 세부 정보를 요청할 수 Microsoft Managed Desktop.

Microsoft Managed Desktop 디바이스의 경우 최신 작업 공간 - **11** 시험판 테스트 장치 Windows 추가를 요청할 수 있습니다. 이 그룹은 Windows 구성과 함께 11개 미리 보기 Microsoft Managed Desktop 수 있습니다. Microsoft Managed Desktop 11 preview 빌드의 릴리스 Windows 관리하지 않는 경우 이 장치 그룹의 구성원이 장치 그룹보다 더 Windows 10 수 있습니다.

Microsoft Managed Desktop 관리되지 않는 장치의 경우 Windows 프로그램 참여를 통해 [](/windows-insider/) 미리 보기 빌드를 다운로드하고 Windows 11 배포에 대한 지침을 얻을 수 있습니다. 11 pre-release Windows 실행 중이고 나중에 Microsoft Managed Desktop 디바이스를 등록하는 경우 장치로 되돌아가지 Windows 10.

## <a name="support-for-pre-release-windows-11-devices"></a>11개 디바이스의 Windows 지원

모든 플랫폼의 사전 릴리스 빌드에는 일반 공급 전에 식별 및 해결될 수 있는 결함 및 응용 프로그램 호환성 문제가 포함되어야 합니다. 따라서 Windows 11의 시험판 빌드를 실행하는 장치는 테스트 장치로 고려하지만 나머지 환경과 함께 보안 위협을 모니터링하며 다른 Microsoft Managed Desktop 장치와 동일한 보안 경고 응답을 적용합니다.

생산성을 유지하면서 Windows 11로 마이그레이션할 수 있도록 지원하기 위해 최선을 다하고 있기 때문에, 사전 릴리스 빌드에서 발생하는 결함을 보고하는 것이 권장됩니다. 당사는 Windows 11을 광범위하게 배포할 때 사용자 생산성을 차단하는 결함과 Windows 10 장치의 사용자 생산성을 차단하는 결함의 우선 순위를 지정합니다.

## <a name="testing-application-compatibility"></a>응용 프로그램 호환성 테스트

응용 프로그램 호환성은 생산성 중단으로 인한 플랫폼 마이그레이션에서 가장 일반적인 문제 중 하나입니다. 당사는 앱의 원활한 전환이 11일 때의 원활한 전환에 대해 확신할 수 있도록 몇 가지 사전 및 사후 Windows 있습니다.

### <a name="proactive-measures"></a>사전 조치

**일반적인 앱:** Microsoft는 11의 빌드에 배포된 가장 일반적인 엔터프라이즈 응용 프로그램 및 제품군을 Windows 있습니다. 테스트 중에 발견된 문제를 해결하기 위해 외부 소프트웨어 게시자 및 내부 제품 팀과 함께 작업합니다. 사전 호환성 테스트 노력에 대한 자세한 내용은 응용 프로그램 호환성 블로그 [를 참조하세요.](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/)

업무용 **앱:** [](https://www.microsoft.com/en-us/testbase) 테스트 기준은 앱 게시자 및 IT 관리자가 보안 Azure 환경에서 Windows 11 빌드를 실행하는 가상 머신에서 Microsoft가 실행되는 앱 및 테스트 사례를 제출하는 데 사용할 수 있는 리소스입니다. 개인 Azure Portal에서 각 테스트 실행에 대한 결과, 테스트 인사이트 및 회귀 분석을 사용할 수 있습니다. Microsoft Managed Desktop 앱 사용 및 안정성 데이터를 기반으로 유효성 검사를 위해 업무용 앱의 우선 순위를 지정하는 데 도움이 됩니다. 테스트 기준에 대한 자세한 내용은 Test [Base for Microsoft 365.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566)

### <a name="reactive-measures"></a>사후 조치
테스트 또는 프로덕션 환경에서 앱 호환성 문제가 발생하는 경우 App [Assure](/fasttrack/products-and-capabilities#app-assure) 또는 앱 설치를 적절하게 FastTrack 지원을 받을 수 있습니다. Windows 11의 경우 여기에는 최신 운영 체제 빌드에서 실행되는 Office, Microsoft Edge, Teams 및 업무(LINE-OF-BUSINESS) 응용 프로그램의 모든 기능이 포함됩니다. App Assure는 앱 게시자를 직접 참여하여 앱 호환성 문제의 우선 순위를 지정하고 해결합니다.

