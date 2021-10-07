---
title: 정기적인 빠른 검사 및 전체 검사 Microsoft Defender 바이러스 백신
description: 실행해야 하는 시간 및 전체 검사 또는 빠른 검사로 실행 여부를 포함하여 재발(예약된) 검사 설정
keywords: 빠른 검사, 전체 검사, 빠른 대 전체, 검사 예약, 매일, 매주, 시간, 예약, 정기적인
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: f5347bb3b671473f6d16d9f50578a9a7a2c5ebe1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60162497"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>예약된 빠른 또는 전체 Microsoft Defender 바이러스 백신 검사 구성

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

실시간 실시간 보호 및 필요한 바이러스 [](run-scan-microsoft-defender-antivirus.md) 백신 검사 외에도 정기적인 예약된 바이러스 백신 검사도 설정할 수 있습니다. 검사 유형, 검사가 실행되는 경우 및 보호 업데이트 후 또는 [](manage-protection-updates-microsoft-defender-antivirus.md) 끝점이 사용되지 않을 때 검사가 실행될지 구성할 수 있습니다. 필요한 경우 재구성 작업을 완료하기 위해 특수 검색을 설정할 수도 있습니다.

## <a name="what-do-you-want-to-do"></a>무슨 작업을 하고 싶으십니까?

- [빠른 검사, 전체 검사 및 사용자 지정 검사에 대해 자세히 알아보기](#quick-scan-full-scan-and-custom-scan)
- [그룹 정책을 사용하여 바이러스 백신 검사 예약](schedule-antivirus-scans-group-policy.md)
- [이 Windows PowerShell 사용하여 바이러스 백신 검사 예약](schedule-antivirus-scans-powershell.md)
- [관리 Windows 사용하여 바이러스 백신 검사 예약](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>다음에 유의해야 합니다.

- 기본적으로 Microsoft Defender 바이러스 백신 검사 시간이 15분 전에 업데이트를 검사합니다. 이 [기본값을](manage-protection-update-schedule-microsoft-defender-antivirus.md) 다시 설정하기 위해 보호 업데이트를 다운로드하고 적용해야 하는 일정을 관리할 수 있습니다.

- 예약된 전체 검사 중에 디바이스의 연결이 풀리며 배터리에서 실행되는 경우 예약된 검사는 완료 전에 스캔이 중지된 이벤트 1002와 함께 중지됩니다. Microsoft Defender 바이러스 백신 예약된 다음에 전체 검사가 실행됩니다.

## <a name="quick-scan-full-scan-and-custom-scan"></a>빠른 검사, 전체 검사 및 사용자 지정 검사

예약된 검색을 설정할 때 검사가 전체 검사인지 아니면 빠른 검사인지를 지정할 수 있습니다. 대부분의 경우 빠른 검사가 권장됩니다.

<br>

****

|빠른 검사|전체 검사|사용자 지정 검사|
|---|---|---|
|(권장) 빠른 검사는 레지스트리 키 및 알려진 시작 폴더와 같이 시스템으로 시작하기 위해 등록된 맬웨어가 있을 수 있는 모든 Windows 검색합니다. <p> 파일을 열고 닫을 때 그리고 사용자가 폴더를 탐색할 때마다 파일을 검토하는 실시간 보호와 함께 빠른 검사가 시스템 및 커널 수준 맬웨어로 시작되는 맬웨어를 강력한 보호하는 데 도움이 됩니다. <p> 대부분의 경우 빠른 검사만으로 충분하며 예약된 검사에 권장되는 옵션입니다.|전체 검사는 빠른 검색을 실행하여 시작한 다음 탑재된 모든 고정 디스크 및 이동식/네트워크 드라이브(전체 검사가 구성된 경우)에 대한 파일 검색을 계속합니다. <p> 전체 검사는 검사해야 하는 데이터의 양과 유형에 따라 완료하는 데 몇 시간 또는 며칠이 걸릴 수 있습니다. <p> 전체 검사가 완료되면 새로운 보안 인텔리전스를 사용할 수 있으며 새 보안 인텔리전스를 통해 다른 위협이 검색되지는 않습니다. <p> 전체 검사와 관련된 시간 및 리소스 때문에 일반적으로 Microsoft는 전체 검사의 시간을 정하지 않는 것이 좋습니다.|사용자 지정 검사는 지정한 파일 및 폴더에서 실행되는 빠른 검사입니다. 예를 들어 USB 드라이브 또는 장치의 로컬 드라이브에 있는 특정 폴더를 검색하도록 선택할 수 있습니다.|
|

> [!NOTE]
> 기본적으로 빠른 검사는 USB 드라이브와 같은 탑재된 이동식 장치에서 실행됩니다.

## <a name="how-do-i-know-which-scan-type-to-choose"></a>선택할 검사 유형을 어떻게 알 수 있나요?

다음 표를 사용하여 검사 유형을 선택하십시오.

<br>

****

|시나리오|권장 검사 유형|
|---|---|
|정기적인 예약된 검색을 설정하려는 경우|빠른 검사 <p> 빠른 검사는 디바이스의 프로세스, 메모리, 프로필 및 특정 위치를 확인합니다. 빠른 [검사는 항상 실시간](configure-real-time-protection-microsoft-defender-antivirus.md)보호와 결합되어 시스템으로 시작되는 맬웨어와 커널 수준 맬웨어에 대해 강력한 범위를 제공합니다. 실시간 보호는 파일을 열고 닫을 때와 사용자가 폴더로 이동할 때마다 검토합니다.|
|개별 장치에서 맬웨어와 같은 위협이 감지됩니다.|빠른 검사 <p> 대부분의 경우 빠른 검사는 검색된 맬웨어를 catch하고 정리합니다.|
|필요한 경우 검색을 [실행하려는 경우](run-scan-microsoft-defender-antivirus.md)|빠른 검사|
|USB 드라이브와 같은 휴대용 장치에 맬웨어가 포함되어 있지 않은지 확인하려는 경우|사용자 지정 검사 <p> 사용자 지정 검색을 사용하면 특정 위치, 폴더 또는 파일을 선택하고 빠른 검색을 실행합니다.|
|

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>빠른 검사 및 전체 검사에 대해 알아야 할 다른 것은 무엇입니까?

- 악성 파일은 빠른 검사에 포함되지 않은 위치에 저장할 수 있습니다. 그러나 항상 실시간 보호는 열고 닫힌 모든 파일과 사용자가 액세스한 폴더에 있는 모든 파일을 검토합니다. 실시간 보호와 빠른 검사의 조합은 맬웨어에 대한 강력한 보호를 제공하는 데 도움이 됩니다.

- 클라우드 제공 보호를 통해 액세스 보호 기능을 사용하면 시스템에서 액세스하는 모든 파일이 최신 보안 인텔리전스 및 클라우드 기계 학습 모델을 통해 스캔되도록 할 수 있습니다. [](cloud-protection-microsoft-defender-antivirus.md)

- 실시간 보호가 맬웨어를 감지하고 영향을 받는 파일의 범위가 처음에 결정되지 않은 경우 Microsoft Defender 바이러스 백신 프로세스의 일부로 전체 검사가 시작됩니다.

- 전체 검사는 빠른 검사와 같은 다른 검사에서 검색되지 않은 악성 파일을 검색할 수 있습니다. 그러나 전체 검사는 시간이 걸릴 수 있으며 중요한 시스템 리소스를 사용하여 완료할 수 있습니다.

- 장치가 오랜 시간 동안 오프라인 상태인 경우 전체 검사가 완료되는 데 더 오래 걸릴 수 있습니다.
