---
title: Microsoft 365 정보 네트워크 라우팅
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 정보 네트워크 라우팅
ms.openlocfilehash: 367f83684a4a200e3ddd630e1412c756d7093da1
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749554"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 정보 네트워크 라우팅(미리 보기)

정보 네트워크 라우팅은 Microsoft 서비스 끝점에 대한 네트워크 연결을 최적화하고 개선하기 위해 다양한 Microsoft 365 응용 프로그램을 타사 SD-WAN(소프트웨어 정의 네트워크) 솔루션과 통합하는 기능입니다. SD-WAN 연결이 최적화되어 사용자 환경 및 성능이 향상될 수 있습니다.

>[!IMPORTANT]
>Microsoft 365 정보 네트워크 라우팅은 현재 미리 보기 상태입니다. 지원을 받는 지침을 포함하여 이 미리 보기에 대한 자세한 내용은 [Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2151565)정보 네트워크 라우팅 공개 미리 보기를 참조하세요.

## <a name="overview"></a>개요

정보를 제공하는 네트워크 라우팅은 Microsoft와 SD-WAN 솔루션 간의 양방향 데이터 공유 채널을 제공합니다. 구성하는 모든 사무실 위치 및 인터넷 회로에 대해 Microsoft는 각 특정 인터넷 회로와 연결된 네트워크 트래픽에 대해 선택한 Microsoft 365 응용 프로그램 환경의 품질에 대한 피드백을 SD-WAN 솔루션과 주기적으로 공유합니다. 이 피드백을 사용하여 SD-WAN 솔루션은 사용 가능한 대체 링크를 통해 Microsoft 365 응용 프로그램 트래픽을 라우팅하여 스마트 복구 작업을 수행할 수 있습니다. 

대기 시간 증가 또는 높은 패킷 손실과 같은 특정 인터넷 회로 경로의 서비스 품질 저하는 지속적으로 감지하기 어렵습니다. 이러한 성능 저하는 Exchange Online, SharePoint, OneDrive 및 Microsoft Teams와 같은 응용 프로그램의 사용자 경험에 해를 입을 수 있습니다. 일반적인 증상으로는 Exchange 콘텐츠 검색 속도가 느려지거나, SharePoint 또는 OneDrive 문서 라이브러리와 상호 작용할 때 전송 속도가 높거나, Microsoft Teams에서 통화 또는 모임 품질이 저하됩니다.

네트워크 정보 라우팅 내의 피드백 및 복구 메커니즘은 거의 실시간으로 이러한 문제를 동적으로 감지하고 배포된 SD-WAN 솔루션에 자동 복구 작업을 수행하게 합니다.

또한 데이터 공유 채널은 장치 및 연결된 회로와 관련된 구성 정보 및 사용 통계를 포함하여 SD-WAN 솔루션에서 네트워크 수준 광학 데이터를 주기적으로 수신하는 데도 사용됩니다. 개인 정보는 수집되거나 저장되지 않습니다. 수집된 모든 정보는 사무실 위치 및 연결된 인터넷 회로로 집계됩니다. 이 정보는 Microsoft에서 Microsoft 365 서비스 및 응용 프로그램을 사용할 때 보고된 문제를 보다 효율적이고 효과적으로 해결하는 데 도움이 될 수 있습니다.

>[!NOTE]
>Microsoft 365의 정보 제공 네트워크 라우팅은 WW 상용 클라우드의 테넌트는 지원하지만 GCC 보통, GCC High, DoD, Germany 또는 중국 클라우드는 지원하지 않습니다.

## <a name="requirements"></a>요구 사항

### <a name="integrated-sd-wan-solutions"></a>통합 SD-WAN 솔루션

Microsoft는 다양한 파트너와 협력하여 Microsoft 365 정보 네트워크 라우팅과의 통합을 지원하고 있습니다. 현재 사용하도록 설정된 솔루션은 다음과 같습니다.

| 디바이스 제작자 | 솔루션 이름 | 최소 버전 |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>네트워크 토폴로지

정보 네트워크 라우팅은 현재 Microsoft로 네트워크 트래픽을 보내는 데 사용되는 공용 IP 주소를 기반으로 특정 사무실 위치 및 인터넷 회로와 관련된 트래픽을 식별합니다. 

분기 위치에서 직접 인터넷 액세스를 제공하는 네트워크 회로가 하나 이상 없는 경우 네트워크 정보 라우팅에서 중요한 가치를 제공하지 않을 수 있습니다.

### <a name="application-usage"></a>응용 프로그램 사용 현황

응용 프로그램 환경 데이터(네트워크 품질 메트릭을 통해 반영)는 Windows, Teams, SharePoint 및 OneDrive를 실행하는 디바이스에서 Microsoft Outlook 사용을 통해 수집됩니다. 다른 응용 프로그램 트래픽은 네트워크 회로의 상태 평가 시 고려되지 않습니다.

## <a name="enabling-informed-network-routing"></a>정보 제공 네트워크 라우팅 사용

정보를 제공된 네트워크 라우팅을 사용하려면 여러 단계가 필요하고, 그 중 일부는 SD-WAN 솔루션의 구성 인터페이스 내에서 수행해야 합니다. Microsoft 365 관리 센터에서 구성을 진행하기 전에 SD-WAN 솔루션 내에서 네트워크 정보 라우팅을 사용하도록 설정하는 프로세스를 시작하는 방법에 대한 지침은 SD-WAN 솔루션 공급업체에 문의하십시오.

Microsoft 365 관리 센터에서 정보 네트워크 라우팅을 사용하도록 설정할 준비가 된 경우 필요한 전역 관리자 권한이 있는지 확인합니다.

>[!IMPORTANT]
>선택한 SD-WAN 솔루션에서 정보 제공된 네트워크 라우팅 데이터 공유 채널에 액세스하기 위해 필요한 테넌트 수준 응용 프로그램에 동의하려면 전역 관리자로 다음 단계를 수행해야 합니다.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>1단계: SD-WAN 솔루션 구성 옵션 열기

Microsoft [365](https://admin.microsoft.com/)관리 센터의 왼쪽 **탐색 >** 상태 및 네트워크 연결을 선택합니다.

관리 센터의 이 섹션에서는 조직에 대한 집계된 네트워크 연결 메트릭과 연결을 개선하는 방법에 대한 지침을 제공합니다. 관리 센터에서 사용할 수 있는 이러한 기능에 대한 자세한 내용은 [Microsoft 365](office-365-network-mac-perf-overview.md) 관리 센터의 네트워크 연결(미리 보기)을 참조하세요.

**SD-WAN** > 설정을 선택하여 정보 제공된 네트워크 라우팅 구성 창을 열 수 있습니다. 설정 아래에 나타나는  다른 옵션은 관리 센터의 일반 네트워크 연결 지침에 적용될 수 있으며, 정보를 제공한 네트워크 라우팅을 사용하도록 설정할 필요는 없습니다.

구성 창에서 SD-WAN 솔루션 추가(미리 **보기)를 선택합니다.**

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>2단계: SD-WAN 솔루션 및 데이터 저장소 위치 선택

드롭다운 상자에서 배포한 SD-WAN 솔루션과 네트워크 정보 라우팅과 연결된 데이터를 저장할 위치를 선택합니다. 자세한 내용은 [데이터 저장소](#data-storage) 섹션을 참조하세요.

**다음** 을 선택합니다.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>3단계: 데이터 공유 조건 수락

Microsoft와 선택한 SD-WAN 솔루션 간의 데이터 공유와 관련된 제공된 용어를 신중하게 읽고 확인한 다음 표시된 확인란을 선택합니다.

**다음** 을 선택합니다.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>4단계: SD-WAN 솔루션에 대한 사용 권한 부여

이 단계에서는 Azure AD(Azure Active Directory)를 사용하여 사용 권한 부여 요청을 시작됩니다. 선택한 SD-WAN 솔루션이 정보를 제공하는 네트워크 라우팅 데이터 저장소 및 테넌트와 연결된 서비스 상태 정보에 액세스할 수 있도록 허용하는 테넌트 수준 권한을 부여하도록 요청됩니다. 이 작업을 수행하려면 전역 관리자 역할 권한이 필요합니다.

이 응용 **프로그램 링크에 대한** 사용 권한 부여를 선택하고 Azure AD 요청을 따르게 됩니다.

사용 권한 부여를 완료한 후 다음을 **선택합니다.**

### <a name="step-5-confirm-your-configuration-settings"></a>5단계: 구성 설정 확인

테넌트에 대한 네트워크 정보 라우팅을 사용하도록 설정하는 마지막 단계는 제공한 설정을 표시하는 확인 페이지입니다. 

이제 테넌트에 대해 정보 네트워크 라우팅이 사용하도록 설정됩니다.

**완료를** 선택한 다음 SD-WAN 솔루션 구성 창을 닫습니다.

## <a name="configuring-network-informed-routing"></a>네트워크 정보 라우팅 구성

SD-WAN 솔루션 내에서 정보를 제공된 네트워크 라우팅에 대한 구성의 상당수(예: 정상적인 상황에서 트래픽 라우팅 방법 및 문제가 감지된 경우 사용할 대체 경로 구성)를 수행할 수 있습니다. 이러한 구성 단계에 대한 자세한 내용은 SD-WAN 솔루션 공급자에게 문의하십시오.

정보를 제공하는 네트워크 라우팅이 이러한 위치에 대한 연결을 제공하는 네트워크 회로와 연결된 트래픽을 올바르게 식별할 수 있도록 Microsoft 365 관리 센터에서 각 사무실 위치를 구성해야 합니다.

Office 위치는 Microsoft의 지속적인 네트워크 원격 분석 모음의 일부로 자동 검색될 수 있습니다. 따라서 일부 위치는 테넌트의 관리 센터에 미리 채워지는 경우도 있습니다. 

이러한 위치가 정확하면 원하는 각 위치에 대해 정보 제공된 네트워크 라우팅 기능을 사용하도록 설정하고 인터넷 회로와 공용 IP 주소를 구성하기만 하면 됩니다. 

자동 검색 위치가 정확하지 않은 경우 또는 테넌트에 미리 채워진 위치가 없는 경우 조직의 정확한 토폴로지가 반영될 수 있도록 위치를 수동으로 추가하거나 편집해야 합니다.

### <a name="updating-locations"></a>위치 업데이트

테넌트의 위치는 위치 **탭에서** 찾을 수 있습니다. 위치는 목록에서 직접 편집하거나 CSV 파일을 사용하여 업데이트할 수 있습니다.

정보 네트워크 라우팅을 사용하도록 설정할 각 사무실 위치가 이 목록에 표시되어 있습니다.

>[!NOTE]
>수집된 샘플  및 기타 평가 관련 정보에 대한 위치 목록의 열은 정보 제공된 네트워크 라우팅 기능과 관련이 없습니다.

### <a name="enabling-a-location-for-informed-network-routing"></a>정보를 제공된 네트워크 라우팅에 대한 위치 사용

1. 위치 **목록에서** **빠른** 작업 메뉴에서 편집을 선택하여 위치 구성 창을 니다.

2. 이 **위치에서 Microsoft 365** 정보 네트워크 라우팅 사용 선택.

3. 이 사무실 위치 섹션의 **Egress IP 주소** 범위에 이 사무실 위치에 대한 인터넷 연결을 제공하는 모든 네트워크 회로를 추가합니다. 각 회로가 네트워크 트래픽을 나타내는 고유한 공용 IP 주소 서브넷과 연결되어야 합니다.

4. 변경 내용을 저장하려면 **저장** 을 선택합니다.

## <a name="disabling-network-informed-routing"></a>네트워크 정보 라우팅을 사용할 수 없습니다.

SD-WAN 솔루션 설정을 다시 설정하여 전체 테넌트에 대해 정보를 제공한 네트워크 라우팅 기능을 사용하지 않도록 설정할 수 있습니다. 이렇게 하면 Microsoft 365 내의 모든 데이터 처리가 중지되는 반면 관리 센터 내에서 네트워크 정보 라우팅을 사용하지 않도록 설정해야 합니다.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>1단계: SD-WAN 솔루션 구성 옵션 열기

Microsoft [365](https://admin.microsoft.com/) 관리 센터의 왼쪽 **탐색 >** 상태 및 네트워크 연결을 선택합니다.

**SD-WAN** > 설정을 선택하여 정보 제공된 네트워크 라우팅 구성 창을 열 수 있습니다.

구성 창에는 현재 구성된 SD-WAN 솔루션의 요약이 표시되어 있습니다.

### <a name="step-2-reset-your-configuration"></a>2단계: 구성 다시 설정

구성 창에서 **SD-WAN** 솔루션 설정 다시 설정을 선택합니다.

이제 설정이 다시 설정되고 네트워크 라우팅에 대한 정보를 알릴 수 없습니다. 정보 네트워크 라우팅을 사용하도록 설정하는 단계에 따라 원하는 경우 다시 사용하도록 설정할 [수 있습니다.](#enabling-informed-network-routing)

## <a name="data-storage"></a>데이터 저장소

Microsoft와 SD-WAN 솔루션 공급자 간에 교환되는 데이터는 네트워크 정보 라우팅을 처음 사용하도록 설정하는 동안 선택한 데이터 저장소 위치에 저장됩니다. 데이터 저장소 위치 옵션은 데이터가 저장되는 Microsoft Azure 지역이 포함된 지리적 영역을 나타내며,

>[!NOTE]
>미리 보기 단계 중 사용 가능한 유일한 데이터 저장소 위치는 **북미입니다.** 정보 네트워크 라우팅이 일반적이기 전에 추가 데이터 저장소 위치를 사용할 수 있습니다.

데이터는 최대 30일 동안 이 위치에 보존됩니다. 사용하지 않도록 설정하면 이 30일 보존 기간 내에 남은 모든 데이터가 제거됩니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365 관리 센터의 네트워크 연결(미리 보기)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Connectivity Location Services(미리 보기)](office-365-network-mac-location-services.md)
