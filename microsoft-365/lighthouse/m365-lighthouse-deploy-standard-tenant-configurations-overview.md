---
title: 기준을 사용하여 표준 테넌트 구성 배포 개요
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 서비스 공급자를 사용하는 MSP(관리 Microsoft 365 Lighthouse)의 경우 기준을 사용하여 표준 테넌트 구성을 배포하는 방법을 배워야 합니다.
ms.openlocfilehash: 793a8f61634660487dc9256d23f0f7d83ff68983
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177042"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>기준을 사용하여 표준 테넌트 구성 배포 개요 

> [!NOTE]
> 이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md) 조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse 기준은 여러 고객 테넌트에서 보안 설정을 평가하고 Microsoft 365 수 있는 반복 가능하고 확장 가능한 방법을 제공합니다. 또한 기준은 사용자, 장치 및 데이터를 보호하는 구성을 사용하여 핵심 보안 정책 및 테넌트 준수 표준을 모니터링하는 데 도움이 됩니다.

파트너가 자신의 속도에 따라 보안을 채택할 수 있도록 설계된 Lighthouse는 표준 기준 매개 변수 집합 및 Microsoft 365 서비스를 위한 구성을 제공합니다. 이러한 보안 구성은 테넌트의 보안 및 준수 Microsoft 365 측정하는 데 도움이 됩니다.

Lighthouse 내에서 기본 기준 및 해당 배포 단계를 볼 수 있습니다. 테넌트에 기준을 적용하려면  왼쪽 탐색 창에서 테넌트를 선택한 다음 테넌트를 선택합니다. 그런 다음 배포 계획 **탭으로 이동하여** 원하는 기준을 구현합니다.

## <a name="standard-baseline-security-templates"></a>표준 기준 보안 템플릿

보안 워크로드에 대한 Lighthouse 표준 기준 구성은 모든 관리되는 테넌트가 허용되는 보안 범위 및 규정 준수 상태를 달성할 수 있도록 고안되었습니다.

다음 표의 기준 구성은 Lighthouse 기본 기준을 표준으로 제공합니다.<br><br>

| 기준 구성 | 설명 |
|--|--|
| 관리자에게 MFA 필요 | 관리자에 대해 다단계 인증을 요구하는 보고서 전용 조건부 액세스 정책입니다. 모든 클라우드 응용 프로그램에 필요합니다. |
| 최종 사용자에 대해 MFA 필요 | 사용자에 대해 다단계 인증이 필요한 보고서 전용 조건부 액세스 정책입니다. 모든 클라우드 응용 프로그램에 필요합니다. |
| 레거시 인증 차단 | 레거시 클라이언트 인증을 차단하는 보고서 전용 조건부 액세스 정책입니다. |
| 디바이스를 Microsoft Endpoint Manager – Azure AD 가입 | 테넌트 장치가 테넌트에 등록할 수 있도록 장치 등록을 Microsoft Endpoint Manager. 이 수행은 사용자와 사용자 간에 자동 등록을 설정하여 Azure Active Directory Microsoft Endpoint Manager. |
| AV(바이러스 백신) 정책 구성 | 미리 구성된 Windows 장치용 장치 구성 Microsoft Defender 바이러스 백신. |
| 창 10 준수 정책 설정 | 기본 Windows 충족하기 위해 미리 구성된 설정이 있는 장치 정책입니다. |

## <a name="related-content"></a>관련 콘텐츠

[기본 Microsoft 365 Lighthouse](m365-lighthouse-deploy-baselines.md) 배포(문서)\
[Microsoft 365 Lighthouse FAQ(문서)](m365-lighthouse-faq.yml)
