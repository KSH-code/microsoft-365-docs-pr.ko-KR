---
title: Windows 보안 업데이트 정보 활용
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 772d1d52e977a067ff9bc3517de9cb2ae6c8c9a3
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950370"
---
# <a name="windows-security-update-insights"></a>Windows 보안 업데이트 정보 활용
이 보기에서는 Microsoft Managed Desktop 장치에 대 한 보안 업데이트 상태에 대 한 개요를 제공 합니다. 

사용 현황 데이터를 보려면 <strong>Windows 보안 업데이트</strong> 탭을 선택 합니다.

![Windows 보안 업데이트 창: 왼쪽 열에 있는 장치 상태 및 업데이트 버전의 막대 그래프, center 열에서 시간이 지남에 따라 배포 진행률을 업데이트 하 고, 배포 그룹별 활성 장치 비율 및 오른쪽 열에 95% 배포 대상에 도달 하기 위해 소요 된 일 수를 표시 합니다.](../../media/update-insights.jpg)

## <a name="device-status"></a>장치 상태

Windows 업데이트를 통해 장치를 업데이트 하려면 해당 장치가 인터넷에 연결 되어 있어야 하 고, 최소 6 시간 동안 최대 절전 상태가 아니어야 하며,이 중 두 가지는 연속적 이어야 합니다. 장치가 최대 절전 모드와 연결 되어 있지 않으면 "사용 중인 것으로 간주 됩니다." 이러한 요구 사항을 충족 하지 않는 장치가 업데이트 될 수 있지만, 이러한 장치를 충족 하는 장치를 업데이트 하는 것이 가장 높습니다. 

다음 용어로 Windows Update 컨텍스트에서 장치 활동을 분류 합니다.

- <strong>활성 상태:</strong> 최신 보안 업데이트 릴리스에 대 한 최소 사용 조건 (6 시간, 두 개 연속)을 충족 하 고 최소 5 일 마다 Microsoft Intune을 체크 인 한 장치
- <strong>동기화 됨:</strong> 지난 28 일 이내에 Intune을 사용 하 여 체크 인 한 장치
- <strong>비동기화 됨:</strong> 지난 28 일 동안 Intune을 사용 하 <i>여 체크 인하지 않은 장치</i>




## <a name="update-version-status"></a>업데이트 버전 상태

Microsoft는 해당 월의 두 번째 화요일 마다 보안 업데이트를 릴리스 합니다. 각 릴리스는 알려진 보안 취약성에 대 한 중요 업데이트를 추가 합니다. Microsoft Managed Desktop은 해당 관리 장치의 95%가 매달 사용 가능한 최신 보안 업데이트로 업데이트 되도록 합니다. 새 위협 요소를 urgently 위해 보안 업데이트가 다른 시간에 출시 되는 경우가 있습니다. Microsoft Managed Desktop은 이러한 업데이트를 비슷한 방식으로 배포 합니다.

보안 업데이트 버전의 상태는 다음과 같은 용어로 분류 됩니다.

- <strong>현재:</strong> 이번 달에 출시 된 업데이트를 실행 하는 장치
- <strong>이전 작업:</strong> 이전 달에 출시 된 업데이트를 실행 하는 장치
- <strong>이전 버전:</strong> 이전 달 이전에 릴리스된 보안 업데이트를 실행 하는 장치

<strong>오래</strong> 된 범주에서 일부 장치를 확인 해야 하는 경우--크거나 커지는 모집단은 Microsoft Managed Desktop에 보고 해야 하는 문제를 파악 하 여 조사를 수행할 수 있다는 것을 나타냅니다.


## <a name="deployment-progress"></a>배포 진행률

각 보안 업데이트 릴리스 주기가 시작 될 때 Microsoft Managed Desktop은 장치 채우기에 대 한 스냅숏을 만들고 해당 모집단의 95%로 해당 배포 대상을 설정 합니다. <strong>배포 진행률</strong> 영역에는 업데이트 배포가 각 릴리스에 대해이 목표를 충족 하는 정도를 추적 하 여 매일 업데이트 되는 역사적 추세를 보여 줍니다. 이 그래프에는 활성 상태인 장치만 표시 됩니다.

오른쪽 상단의 드롭다운 메뉴를 사용 하 여 이전 업데이트 주기에 대해이 데이터를 볼 수 있습니다. 이 메뉴에서 선택한 기간은 전체 페이지에 있는 모든 정보에 적용 됩니다.

<strong>배포 그룹별 업데이트 된 활성 장치</strong> 영역은 각 Microsoft 관리 되는 데스크톱 배포 그룹에 대 한 업데이트 설치의 진행률을 표시 하는 다양 한 보기를 제공 합니다.

<strong>대상에 도달 하</strong> 는 데 소요 되는 날짜 영역에는 현재 보안 업데이트를 사용 하 여 업데이트 되는 총 장치 수의 95%가 발생 한 시간이 표시 됩니다. 배포를 진행 하는 동안이 영역에는 선택한 업데이트에 대 한 95% 대상이 도달할 때까지 <strong>업데이트를 계속</strong> 표시 합니다.

## <a name="device-details-area"></a>장치 세부 정보 영역

대시보드의 아래쪽에는 [장치 상태](#device-status) 및 [업데이트 버전 상태](#update-version-status)를 포함 하 여 장치에 대 한 자세한 정보가 표시 되는 표가 있습니다. 이 목록을 검색 하거나 나열 된 값으로 필터링 할 수 있습니다.


![장치 이름, 할당 된 사용자, 장치 상태, 업데이트 버전, 운영 체제 버전 및 장치를 마지막으로 동기화 한 날짜에 대 한 열이 표시 되는 디바이스 정보 테이블](../../media/security-update-insights-device-table-sterile.png)
