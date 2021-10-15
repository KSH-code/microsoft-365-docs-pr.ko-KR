---
title: 새 장치 유효성 검사
description: 디바이스를 주문하기 전에 각 모델 중 하나를 얻은 후 테스트합니다.
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 2b3ba016e5a205ddb6eaccc4df71bdc4ad612085
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364618"
---
# <a name="validate-new-devices"></a>새 장치 유효성 검사

처음 Microsoft Managed Desktop 구독자이든, 장기 구독자이든, 처음으로 서비스에 등록하는 장치 모델의 예를 테스트하는 것이 가장 좋은 예입니다. 새 디바이스를 주문하거나 기존 디바이스를 다시 사용(Shop Microsoft Managed Desktop 비즈니스 장치 사이트)에서 권장되는 장치를 Windows Pro [마찬가지입니다.](https://www.microsoft.com/en-us/windowsforbusiness/view-all-devices) 해당 사이트에서 필터로 필터링 영역의 기능을 확장한  다음  을 선택하여 서비스에 권장되는 장치를 **Microsoft Managed Desktop.** 디바이스의 유효성을 검사하면 예상한 사용자 환경을 제공할 수 있습니다.

## <a name="validate-devices"></a>디바이스 유효성 검사

1. 다음 문서의 단계를 통해 새 모델의 예를 하나 이상 수행합니다.
    - [Microsoft Managed Desktop 장치 설정](set-up-devices.md)
    - [사용자 환경 현지화](localization.md)
    - [Autopilot 및 등록 상태 페이지의 첫 실행 환경](esp-first-run.md)
    - [Windows 10 위치 서비스](device-location.md)
    - [앱 컨트롤 시작](get-started-app-control.md)
    - [장치에 앱 배포](deploy-apps.md)
2. 오류, 오류 또는 프롬프트 없이 다음 환경이 작동 하는지 확인 합니다.
    - 네트워크에 가입하고 사용자가 로그인한 후 Autopilot 환경
    - 등록 상태 페이지를 사용하도록 설정한 경우 [작동합니다.](esp-first-run.md)
    - 사용자가 응용 프로그램에 로그인할 Office 수 있습니다.
    - OneDrive, 문서 및 그림을 Windows 폴더 동기화
    - 장치에서 업데이트, 정책 및 업무(LINE-OF-BUSINESS) 응용 프로그램을 수신합니다.
3. 장치 인벤토리 보고서에서 [](../working-with-managed-desktop/device-inventory-report.md) 보고된 장치 및 하드웨어 요구 사항을 검토하여 예상과 일치하는지 확인합니다.

문제가 발생하는 경우 관리 [포털에서](../working-with-managed-desktop/admin-support.md) 지원을 요청할 수 있습니다.

모든 것이 잘 진행되면 배포에 필요한 유효성이 검사된 나머지 장치를 주문할 준비가 된 것입니다.
