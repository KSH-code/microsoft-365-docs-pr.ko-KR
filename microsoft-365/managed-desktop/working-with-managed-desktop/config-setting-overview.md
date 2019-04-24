---
title: Microsoft Managed Desktop에 대 한 구성 가능 설정
description: Microsoft Managed Desktop을 사용한 구성 가능한 설정에 대 한 정보
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서, 설정, 구성 가능한 설정
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0d30e92eb9747079a7edc5a8fd198298508f342e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278216"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>구성 가능 설정-Microsoft Managed Desktop

microsoft managed desktop은 microsoft managed desktop이 관리 하는 모든 장치에 적용 되는 설정 및 정책을 배포 합니다. 자세한 내용은 [장치 구성을](../service-description/device-policies.md)참조 하세요.

Microsoft Managed Desktop의 구성 가능한 설정은 IT 관리자에 게 조직 및 비즈니스 요구에 고유한 설정을 사용자 지정 하 고 배포 하는 방법을 제공 합니다. 이러한 설정은 Microsoft managed Desktop에서 관리 하는 장치 구성 설정 및 정책에 추가 됩니다.  

구성 가능한 설정 변경 내용은 클라우드에서 작성 되며 정의 된 배포 그룹의 Microsoft Managed Desktop 장치에 적용 됩니다. 이 프로세스는 Microsoft Managed Desktop이 서비스에 의해 정의 되 고 관리 되는 장치 configuruation 설정 및 정책에 대 한 변경 내용을 관리 하는 방법과 비슷합니다. Microsoft Managed Desktop이 변경 내용을 배포 하는 데 사용 하는 것과 동일한 프로세스를 사용 하 여 최신 IT 관리 방법을 사용 하 여 조직을 앞으로 계속 이동할 수 있습니다.

## <a name="when-to-use-configurable-settings"></a>구성 가능한 설정을 사용 하는 경우

구성 가능한 설정을 사용 하는 몇 가지 시간이 있습니다. 

**온 보 딩 프로세스** -microsoft managed desktop은 microsoft managed desktop service에 내장 되어 있거나 많은 수의 장치 (20 개 이상)를 온보드 했을 때 구성 가능한 설정을 사용자 지정 하는 것이 좋습니다. 설정 범주는 Microsoft Managed 데스크톱 관리 포털에서 구성 됩니다. 관리자 포털에 대 한 액세스 권한을 가진 후에는 조직에 맞게 사용자 지정할 범주 설정을 결정 하 고, 변경 작업을 수행 하 고, 배포를 준비 하 고, 변경 내용을 배포할 수 있습니다.

**설정 유지** -정기적으로 설정을 검토 하 고 필요한 사항을 업데이트 합니다. 비즈니스 변경 사항을 지원 하기 위해 변경 작업을 수행 해야 할 수 있습니다.   

## <a name="setting-categories"></a>범주 설정

사용자 지정할 수 있는 구성 가능한 설정 범주는 다음과 같습니다.
- [바탕 화면 배경 그림](config-setting-ref.md#desktop-background-picture) -Microsoft Managed desktop 장치에 대 한 바탕 화면 배경 그림을 사용자 지정 합니다. 
- [브라우저 시작 페이지](config-setting-ref.md#browser-start-pages) -Microsoft Edge에서 사용할 시작 페이지를 추가 합니다. 브라우저 시작 페이지 참조
- [엔터프라이즈 모드 사이트 목록](config-setting-ref.md#enterprise-mode-site-list-location) -사이트 및 호환 모드를 추가 합니다. 목록의 사이트가 Internet Explorer에서 시작 됩니다. 
- [신뢰할 수 있는 사이트](config-setting-ref.md#trusted-sites) -신뢰할 수 있는 사이트를 추가 하 고 각 사이트에 대해 보안 영역을 설정 합니다. 
- [프록시 사이트 예외](config-setting-ref.md#proxy) -프록시 서버 주소 번호 및 포트 번호를 설정 하 고 프록시 사이트 예외를 추가 합니다.

각 설정 범주를 사용자 지정 하 고 직접 배포할 수 있습니다. 동시에 여러 설정 범주에 대 한 변경 내용을 배포할 수 있지만 한 번에 하나의 변경만 설정 범주에 배포할 수 있습니다.

예를 들면 다음과 같습니다.
- 데스크톱 배경 그림 및 신뢰할 수 있는 사이트에 대 한 변경 내용을 각 사용자에 게 동시에 배포할 수 있습니다. 
- 두 개의 배포를 브라우저 시작 페이지에 동시에 배포할 수는 없습니다. 가장 최근 배포에서는 아직 진행 중인 이전 배포를 중지 합니다.

## <a name="configurable-setting-process"></a>구성 가능한 설정 프로세스

Microsoft Managed Desktop은 조직에 대해 구성 가능한 설정을 활용할 때 다음과 유사한 프로세스를 수행 하는 것이 좋습니다.

**1 단계-계획** -구성 가능한 설정에 대해 설명 하 고 조직에 대해 구성할 설정 범주를 결정 합니다. 각 그룹에 대 한 변경 내용을 배포할 것으로 예상 되는 시간에 대 한 일정을 만듭니다. 내부 변경 관리 프로세스를 충족 하는 사용자에 대 한 통신을 계획 합니다. 예를 들어 브라우저 시작 페이지를 추가 하는 경우에는 배포 후 브라우저에 새 시작 페이지 집합을 사용할 수 있음을 사용자에 게 알려 줍니다.  

**2 단계-배포 구성 및 단계** -Microsoft Managed Desktop administration portal에서 구성 가능한 설정을 변경 합니다. 배포 준비가 완료 되도록 변경 단계를 진행 합니다. 사용자에 게 변경 내용에 대 한 정보와 변경 내용이 장치 환경을 어떻게 변경 하는지 알려 줄 것을 고려해 야 합니다.   

Microsoft Managed Desktop admin 포털에서 변경 사항을 구성 하 고 준비 합니다. 자세한 내용은 [구성 가능한 설정 사용자 지정](config-setting-ref.md)을 참조 하십시오. 

**3 단계-변경 내용 전달** 사용자에 게 예정 된 변경 내용에 대 한 정보를 전달 합니다. 각 배포에 대해 변경 관리 프로세스의 일부인 통신을 완료 합니다. 사용자가 작업 하는 방식 또는 장치에 표시 되는 내용에 영향을 주는 변경 사항을 명확 하 게 전달 해야 합니다.

**4 단계-배포 변경** -테스트 그룹부터 시작 하 여 변경 내용을 배포 합니다. 테스트 그룹을 사용 하면 대규모 장치 그룹에 대 한 변경 내용을 배포 하기 전에 장치 수가 적을수록 그룹의 모든 문제를 확인 하 고 문제를 해결할 수 있습니다. 문제가 발생할 경우 변경 내용을 되돌리고 설정을 업데이트 하 고 새 배포를 준비할 수 있습니다. Microsoft Managed Desktop은 Test, First, Fast, 폭넓은 순서로 구조화 된 방식을 따르고 그룹에 배포 하는 것이 좋습니다.   

모든 구성 가능한 설정은 Microsoft managed Desktop admin 포털을 사용 하 여 관리 됩니다. 자세한 내용은 [배포 변경](config-setting-deploy.md)항목을 참조 하십시오. 

**5 단계-변경 내용 추적** -배포 상태에 대 한 변경 진행률을 추적 합니다. 각 설정에 대해 다음 작업을 수행할 수 있습니다.
- **진행 상황 관리** -변경 내용을 배포한 후 상태를 추적 합니다. 상태가 **진행**중으로 변경 되 고 **완료**되거나 **실패**합니다. 배포에 실패 하면 문제를 조사 하기 위해 Microsoft Managed Desktop 작업에 대 한 지원 요청이 자동으로 열립니다.  
- **배포 된 버전 확인** -각 배포 되는 변경 내용에 버전 번호가 있습니다.
- **변경 내용 되돌리기** -변경 내용을 되돌리면 현재 배포가 중지 되 고 모든 그룹이 모든 그룹에 배포 된 마지막 변경 내용으로 되돌아갑니다. 마지막으로 성공한 설정 값으로 롤백하는 중입니다.
- **변경 내용 유효성 검사** -배포가 완료 된 후 변경 내용이 예상 대로 적용 되었는지 확인 합니다.  

배포에 실패 했거나 변경 내용을 되돌릴 수 없는 경우 Microsoft Managed Desktop 작업을 사용 하 여 [지원 요청을 엽니다](admin-support.md) . 

자세한 내용은 [배포 및 추적 구성 가능 설정](config-setting-deploy.md)를 참조 하세요.

## <a name="additional-resources"></a>추가 리소스
- [구성 가능한 설정 참조](config-setting-ref.md) 
- [구성 가능한 설정 배포](config-setting-deploy.md) 
