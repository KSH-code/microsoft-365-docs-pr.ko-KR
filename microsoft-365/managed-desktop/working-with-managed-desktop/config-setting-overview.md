---
title: 사용자에 대한 구성 가능한 Microsoft Managed Desktop
description: 구성 가능한 설정에 대한 Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, 문서, 설정, 구성 가능한 설정
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a83181d6b0fa33b0eb432627530099b316ebb617
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150357"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>구성 가능한 설정-Microsoft 관리형 데스크톱

Microsoft Managed Desktop 관리되는 모든 장치에 적용되는 설정 및 정책을 Microsoft Managed Desktop. 자세한 내용은 장치 [구성을 참조하세요.](../service-description/device-policies.md)

조직의 구성 가능한 설정을 Microsoft Managed Desktop IT 관리자는 조직 및 비즈니스 요구에 맞는 설정을 사용자 지정하고 배포할 수 있습니다. 이러한 설정은 장치 구성 설정 및 장치 구성 설정에 의해 관리되는 정책 외에 Microsoft Managed Desktop.  

구성 가능한 설정 변경 사항은 클라우드에서 적용되고 정의된 배포 그룹의 Microsoft Managed Desktop 장치에 적용됩니다. 이 프로세스는 Microsoft Managed Desktop 정의 및 관리되는 장치 구성 설정 및 정책에 대한 변경 내용을 관리하는 방법과 비슷합니다. 변경 내용을 배포하는 Microsoft Managed Desktop 사용하는 프로세스와 동일한 프로세스를 사용하면 최신 IT 관리 방법을 사용하여 조직을 계속 진행할 수 있습니다.

## <a name="when-to-use-configurable-settings"></a>구성 가능한 설정을 사용하는 경우

구성 가능한 설정을 몇 번 사용할 수 있습니다. 

**온보더 Microsoft Managed Desktop** – Microsoft Managed Desktop 서비스를 온보드하거나 많은 수의 디바이스(20개 이상)를 온보더링할 때 구성 가능한 설정을 사용자 지정하는 것이 좋습니다. 범주 설정은 관리 포털에서 Microsoft Managed Desktop 구성됩니다. 온보드를 하고 관리 포털에 액세스한 후 조직에 맞게 사용자 지정할 범주를 결정하고, 변경을 진행하고, 배포를 준비한 다음 변경 내용을 배포할 수 있습니다.

**설정 유지** 관리 - 설정을 정기적으로 검토하고 필요한 업데이트를 적용합니다. 비즈니스 변경을 지원하기 위해 변경해야 할 수 있습니다.   

## <a name="setting-categories"></a>범주 설정

사용자 지정할 수 있는 구성 가능한 설정 범주는 다음과 같습니다.
- [바탕 화면 배경 그림](config-setting-ref.md#desktop-background-picture) - 사용자 지정 장치용 데스크톱 배경 Microsoft Managed Desktop. 
- [브라우저 시작 페이지](config-setting-ref.md#browser-start-pages) – 브라우저에 사용할 시작 페이지를 Microsoft Edge. 브라우저 시작 페이지 참조
- [Enterprise 모드 사이트 목록](config-setting-ref.md#enterprise-mode-site-list-location) - 사이트 및 해당 호환성 모드를 추가합니다. 목록의 사이트는 목록에서 Internet Explorer. 
- [신뢰할 수 있는 사이트](config-setting-ref.md#trusted-sites) – 신뢰할 수 있는 사이트를 추가하고 각 사이트에 대해 보안 영역 설정 
- [프록시 사이트 예외](config-setting-ref.md#proxy) – 프록시 서버 주소 번호 및 포트 번호를 설정하고 프록시 사이트 예외를 추가합니다.

각 설정 범주를 사용자 지정하고 자체적으로 배포할 수 있습니다. 여러 설정 범주에 변경 내용을 동시에 배포할 수 있습니다. 그러나 한 번의 변경 내용만 설정 범주에 배포할 수 있습니다.

예:
- 데스크톱 배경 그림 및 신뢰할 수 있는 사이트에 변경 내용을 각각 자체 배포로 동시에 배포할 수 있습니다. 
- 두 개의 배포를 브라우저 시작 페이지에 동시에 배포할 수 없습니다. 가장 최근 배포는 아직 진행 중인 이전 배포를 중지합니다.

## <a name="configurable-setting-process"></a>구성 가능한 설정 프로세스

Microsoft Managed Desktop 구성 가능한 설정을 사용할 때 다음과 비슷한 프로세스를 따라야 합니다.

**1단계 - 계획** - 구성 가능한 설정에 대해 알아보고 조직에 대해 구성할 범주를 결정할 수 있습니다. 각 그룹에 변경 내용을 배포할 것으로 예상되는 시간 표시 막대를 만드세요. 내부 변경 관리 프로세스를 충족하는 사용자와의 통신을 계획합니다. 예를 들어 브라우저 시작 페이지를 추가하는 경우 배포 후 브라우저에 새 시작 페이지 집합이 표시된다고 사용자에게 알립니다.  

**2단계 - 배포** 구성 및 단계 - 관리 포털에서 구성 가능한 Microsoft Managed Desktop 변경합니다. 변경 내용을 배포할 수 있도록 준비합니다. 사용자에게 변경 내용과 변경 내용이 장치 환경을 어떻게 변경하는지 알려야 합니다.   

관리 포털에서 변경 내용을 구성하고 Microsoft Managed Desktop 합니다. 자세한 내용은 구성 가능한 설정 [사용자 지정을 참조하세요.](config-setting-ref.md) 

**3단계 - 변경 내용 전달** 사용자에게 예정된 변경 내용에 대한 정보를 전달합니다. 각 배포에 대해 변경 관리 프로세스의 일부인 통신을 완료합니다. 사용자가 작업하는 방식이나 장치에 어떤 변화가 표시될지 명확히 전달해야 합니다.

**4단계 - 변경 내용 배포** - 테스트 그룹에서 시작하여 변경 내용을 배포합니다. 테스트 그룹을 사용하면 더 큰 장치 그룹에 변경 내용을 배포하기 전에 더 적은 수의 장치로 그룹의 문제를 확인하고 해결할 수 있습니다. 문제가 있는 경우 변경을 되버려 설정을 업데이트하고 새 배포를 단계화할 수 있습니다. Microsoft Managed Desktop 순서대로 구조화된 접근 방식을 따르고 테스트, 첫 번째, 빠른, 광범위 순서로 그룹에 배포하는 것이 좋습니다.   

구성 가능한 모든 설정은 Microsoft Managed Desktop 관리 포털을 사용하여 관리됩니다. 자세한 내용은 변경 내용 [배포를 참조하세요.](config-setting-deploy.md) 

**5단계 - 변경 내용 추적** - 배포 상태의 변경 내용 추적 각 설정에 대해 다음을 할 수 있습니다.
- **진행률 추적** - 변경을 배포한 후 상태를 추적합니다. 상태가 진행 중으로 변경된 다음 **완료** 또는 **실패로 변경됩니다.**  배포에 실패하면 문제 조사를 위해 Microsoft Managed Desktop 지원 요청이 자동으로 열립니다.  
- **배포된 버전 -** 배포된 각 변경에는 버전 번호가 있습니다.
- **변경 내용 되전** - 변경 내용을 되전하면 현재 배포가 중지하고 모든 그룹이 모든 그룹에 배포된 마지막 변경 내용으로 되전됩니다. 마지막으로 알려진 설정 값으로 롤백합니다.
- **변경 내용 유효성** 검사 - 배포가 완료된 후 변경 내용이 예상대로 적용된 유효성을 검사합니다.  

배포가 실패했거나 변경을 되전할 수 없는 [](admin-support.md) 경우 Microsoft Managed Desktop Operations를 사용하여 지원 요청을 열 수 있습니다. 

자세한 내용은 구성 가능한 설정 [배포 및 추적을 참조하세요.](config-setting-deploy.md)

## <a name="additional-resources"></a>추가 리소스
- [구성 가능한 설정 참조](config-setting-ref.md) 
- [구성 가능한 설정 배포](config-setting-deploy.md) 
