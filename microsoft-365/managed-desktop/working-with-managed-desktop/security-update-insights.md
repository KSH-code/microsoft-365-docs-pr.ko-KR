---
title: Windows 보안 업데이트 정보 활용
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739837"
---
# <a name="windows-security-update-insights"></a>Windows 보안 업데이트 정보 활용
이 보기는 사용자 장치 보안 업데이트의 상태에 대한 개요를 Microsoft Managed Desktop 제공합니다. 

사용 현황 데이터를 확인하려면 보안 업데이트 Windows <strong>선택합니다.</strong>

![Windows 보안 업데이트 창: 왼쪽 열의 장치 상태 및 업데이트 버전 그래프, 가운데 열의 시간 경과에 따라 배포 진행률 업데이트, 배포 그룹당 활성 장치 백분율, 오른쪽 열의 95% 배포 목표에 도달하는 데 걸렸다는 일 수](../../media/update-insights.jpg)

## <a name="device-status"></a>장치 상태

Windows 업데이트하여 장치를 업데이트하려면 인터넷에 연결되어 있어야 합니다. 최소 6시간 동안 최대 2시간 동안 인터넷에 연결되어 있어야 합니다. 이 중 두 장치는 연속해야 합니다. 이러한 요구 사항을 충족하지 않는 장치가 업데이트될 수도 있습니다. 그러나 해당 장치를 충족하는 장치는 업데이트될 가능성이 가장 높습니다. 

다음 용어를 사용하여 Windows 업데이트의 컨텍스트에서 장치 활동을 분류합니다.

- <strong>활성:</strong> 최신 보안 업데이트 릴리스에 대한 최소 작업 기준(6시간, 연속 2개)을 충족하고 최소 5일마다 Microsoft Intune 체크 인한 장치
- <strong>동기화된:</strong> 지난 28일 이내에 Intune으로 체크 인한 장치
- <strong>동기화되지 않습니다.</strong> 지난 28일 동안 Intune으로 체크 인하지 않은 장치 <i></i>




## <a name="update-version-status"></a>버전 상태 업데이트

Microsoft는 매월 둘째 주 화요일에 보안 업데이트를 릴리스합니다. 각 릴리스에는 알려진 보안 취약성에 대한 중요한 업데이트가 추가되었습니다. Microsoft Managed Desktop 관리되는 장치의 95%가 매월 사용 가능한 최신 보안 업데이트로 업데이트되도록 보장합니다. 보안 업데이트는 때때로 새로운 위협을 긴급히 해결하기 위해 릴리스됩니다. Microsoft Managed Desktop 유사한 방법을 통해 이러한 업데이트를 배포할 수 있습니다.

다음 용어를 통해 보안 업데이트 버전의 상태를 분류합니다.

- <strong>현재:</strong> 현재 달에 릴리스된 업데이트를 실행하는 장치
- <strong>이전:</strong> 이전 달에 릴리스된 업데이트를 실행하는 장치
- <strong>이전:</strong> 이전 달 이전에 릴리스된 보안 업데이트를 실행하는 장치

이전 범주에 몇 <strong></strong> 가지 장치가 표시되어 있습니다. 대규모 또는 증가하는 인구는 조사할 수 있도록 Microsoft Managed Desktop 보고해야 하는 시스템적인 문제를 나타냅니다.


## <a name="deployment-progress"></a>배포 진행률

각 보안 업데이트 릴리스 주기가 시작될 때 Microsoft Managed Desktop 스냅숏을 만들어 배포 대상을 해당 인구의 95%로 설정합니다. 배포 <strong>진행률 영역에는</strong> 업데이트 배포가 각 릴리스의 이 목표를 얼마나 충족하는지 추적하는 기록 추세가 매일 업데이트됩니다. 이 그래프에는 활성 상태의 장치만 표시됩니다.

오른쪽 위에 있는 드롭다운 메뉴를 사용하여 이전 업데이트 주기에 대한 이 데이터를 볼 수 있습니다. 이 메뉴에서 선택한 기간은 전체 페이지의 모든 정보에 적용됩니다.

배포 <strong>그룹별로</strong> 업데이트된 활성 장치 영역은 각 배포 그룹에 대한 업데이트 설치 진행률을 표시하여 다른 Microsoft Managed Desktop 제공합니다.

대상 <strong>영역에 도달하는</strong> 데 걸려 오기 영역에는 현재 보안 업데이트로 업데이트되는 총 장치 수의 95%가 걸려 있는 기간이 표시됩니다. 배포가 진행되는 동안 이 <strong>영역에는</strong> 선택한 업데이트에 대한 95% 대상에 도달할 때까지 계속 업데이트가 표시됩니다.

## <a name="device-details-area"></a>장치 세부 정보 영역

대시보드의 맨 아래에는 장치 상태 및 업데이트 버전 [](#device-status) 상태를 포함하여 장치에 대한 자세한 정보가 [표시되어 있습니다.](#update-version-status) 이 목록을 검색하거나 나열된 값으로 필터링할 수 있습니다.


![장치 이름, 할당된 사용자, 장치 상태, 업데이트 버전, 운영 체제 버전 및 장치가 마지막으로 동기화된 날짜에 대한 열을 보여주는 장치 세부 정보 표입니다.](../../media/security-update-insights-device-table-sterile.png)
