---
title: 배터리 정보
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 81b7a7c3db69d1c20f9a9cd8c6ea4a37b481ce59
ms.sourcegitcommit: 9b390881fe661deb0568b4b86a5a9094f3c795f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269389"
---
# <a name="battery-insights"></a>배터리 정보
이 보기는 Microsoft 관리 데스크톱 장치에 대 한 전원, 배터리 및 앱 사용 메트릭을 제공 합니다. 이러한 용도의 앱은 실행 중이 고 포커스가 있는 경우 "사용 중"으로 간주 됩니다.

사용 현황 데이터를 보려면 **배터리** 탭을 선택 합니다.

![배터리 창: 왼쪽 위에 있는 각 장치에 대해 예상 되는 배터리 수명 모델입니다. 오른쪽 위에 있는 설명서 링크입니다.](images/insights_battery.png)

## <a name="predicted-battery-life"></a>예측 한 배터리 수명

예상 되는 **배터리 수명** 영역에서 장치 모델에 따라 구성 된 장치에 대 한 예상 배터리 수명 예측을 제공 합니다.

> [!NOTE]
> 이 데이터는 Microsoft Managed Desktop deployment에서 데이터를 보고 하는 장치를 임의로 <em>선택</em> 했을 때 에너지 사용량, 사용 시간 및 배터리 용량 샘플링에서 파생 됩니다.

이 표에서는 다른 Microsoft Managed Desktop 배포의 동일한 모델에 대 한 예상 배터리 수명, 평균 배터리 수명 및 해당 환경에서이 데이터를 보고 하는 장치 수를 제공 합니다. 열 머리글을 선택 하 여 데이터를 정렬 합니다.



## <a name="top-energy-consumers"></a>주요 에너지 소비자

**상위 에너지 소비자** 분야에서는 MilliWatt (mWh)에서 가장 많은 에너지를 사용 하는 환경에서 앱을 찾을 수 있습니다. 표시 되는 앱은 왼쪽에 있는 **예측 된 배터리 수명** 섹션에서 선택한 특정 장치에 따라 결정 됩니다. 예를 들어 마이크로 Sft Surface Book 2 장치의 앱 단위 소비량을 보려면 배터리 수명 영역에서 해당 행을 선택 합니다. 모델을 선택 하지 않으면 기본적으로 데이터를 포함 하는 모든 앱에 대 한 앱 소비 데이터가 표시 됩니다.

 각 앱에 대해 색 세그먼트는 다음 범주 중에서 앱의 에너지 사용 분포를 보여 줍니다.

- CPU
- 디스플레이
- 네트워크
- 기타

"Other"는 디스크 활동, 모바일 광대역 사용량, 내부 저항에 대 한 에너지 손실 등 다양 한 원본의 에너지 소비량을 포함할 수 있습니다. 

오른쪽 위에 있는 메뉴를 사용 하 여 포그라운드 앱, 백그라운드 앱 또는 둘 다를 표시 하도록이 보기를 필터링 할 수 있습니다. 포그라운드 앱은 마우스를 사용 하 여 항목을 선택 하는 것과 같이 지난 28 일 이내에 사용자 상호 작용이 발생 한 응용 프로그램입니다.

## <a name="insights"></a>인사이트

이 **Insights** 영역에는 CPU 및 네트워크 범주에 있는 세 가지 에너지 소비자가 표시 됩니다. 이러한 항목은 모든 Microsoft Managed Desktop 배포에 비해 평균 에너지 보다 높은 수준으로 소비 됩니다. 표시 리소스는 장치 사용 시간 및 화면 밝기 설정에 크게 좌우 되므로 표시 하지 않습니다. 

자세한 내용을 보려면 **세부 정보** 열에서 목록을 선택 합니다.

## <a name="battery-optimization"></a>배터리 최적화

Windows 10에서는 전원 사용을 개선 하 고 Microsoft 관리 되는 데스크톱 장치의 배터리 수명 증가를 위해 다양 한 [장치 설정을](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) 제공 합니다. 이러한 설정 중 일부는 다른 Windows 기능을 줄일 수 있으므로 조직의 장치 역할과 같은 다른 요소도 고려해 야 합니다. Windows 지원에서는 이러한 [배터리 저장 팁](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)의 목록을 유지 관리 합니다.

사용자는 관리자 권한 상승이 나 지원을 필요로 하지 않고 자체 설정을 직접 조정할 수 있습니다. 다른 설정을 위해서는 조직의 IT 관리자가 지원 해야 합니다.
