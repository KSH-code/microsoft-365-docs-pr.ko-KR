---
title: 프로덕션 Microsoft 365 Defender 환경으로 승격
description: 이 문서를 사용하여 MDI, MDO, MDE 및 MCAS를 MDI 또는 M365D의 라이브 환경으로 Microsoft 365 Defender 홍보할 수 있습니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: eb59cc540d2c77f2d4715aa1c6c12f4e36aec8b0
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753050"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a>프로덕션 Microsoft 365 Defender 환경으로 승격

**적용 대상:**
- Microsoft 365 Defender

평가 환경을 Microsoft 365 Defender 환경을 프로덕션 환경으로 승격하기 위해 먼저 필요한 라이선스를 구입합니다. eval 환경 [](eval-create-eval-environment.md) 만들기의 단계를 수행하고 평가판 시작을 Office 365 E5 라이선스를 구입합니다.

그런 다음 추가 구성을 완료하고 파일럿 그룹이 전체 프로덕션에 도달할 때까지 파일럿 그룹을 확장합니다.

## <a name="microsoft-defender-for-identity"></a>ID용 Microsoft Defender

Id에 대한 Defender에는 추가 구성이 필요하지 않습니다. 필요한 라이선스를 구입하고 모든 Active Directory 도메인 컨트롤러 및 AD FS(Active Directory Federation Services) 서버에 센서를 설치해야 합니다.

## <a name="microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender

MDO를 평가하거나 파일럿한 후 전체 프로덕션 환경으로 승격할 수 있습니다.

1. 필요한 라이선스를 구매하여 프로비전하고 프로덕션 사용자에게 할당합니다.
2. 프로덕션 전자 메일 도메인 또는 특정 사용자 그룹에 대해 권장 기준 정책 구성(Standard 또는 Strict)을 다시 실행합니다.
3. 원하는 경우 프로덕션 전자 메일 도메인 또는 사용자 그룹에 대해 사용자 지정 MDO 정책을 만들고 구성합니다.  그러나 할당된 모든 기준 정책은 항상 사용자 지정 정책보다 우선합니다.
4. EOP로 직접 확인하려면 프로덕션 전자 메일 도메인의 공용 MX 레코드를 업데이트합니다.
5. 타사 SMTP 게이트웨이를 해제하고 이 릴레이와 연결된 모든 EXO 커넥터를 사용하지 않도록 설정하거나 삭제합니다.

## <a name="microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender

파일럿에서 프로덕션 환경으로의 Microsoft Defender 평가 환경을 승격하기 위해 지원되는 도구 및 방법을 사용하여 서비스에 더 많은 끝점을 [온보딩하기만 합니다.](../defender-endpoint/onboard-configure.md)

다음 일반 지침을 사용하여 끝점용 Microsoft Defender에 더 많은 장치를 온보딩합니다.

1. 장치가 최소 요구 사항을 [충족하는지 확인합니다.](../defender-endpoint/minimum-requirements.md)
2. 장치에 따라 끝점 포털용 Defender의 온보딩 섹션에 제공된 구성 단계를 따릅니다.
3. 장치에 적합한 관리 도구 및 배포 방법을 사용합니다.
4. 검색 테스트를 실행하여 장치가 제대로 온보드 및 서비스에 보고되었는지 확인합니다.

## <a name="microsoft-cloud-app-security"></a>Microsoft 클라우드 앱 보안

Microsoft Cloud App Security 구성이 필요하지 않습니다. 필요한 라이선스를 구입해야 합니다. 특정 사용자 그룹에 대한 배포 범위를 지정한 경우 프로덕션 규모에 도달할 때까지 이러한 그룹의 범위를 늘리면 됩니다.
