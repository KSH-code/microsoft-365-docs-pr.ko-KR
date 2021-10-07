---
title: Office 365의 네트워크 및 마이그레이션 계획
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: 이 문서에는 네트워크 계획, 테스트 및 마이그레이션에 대한 정보로 연결되는 링크가 포함되어 Office 365.
ms.openlocfilehash: 21bd36395f6ceb6a13b3180a26f8dbf7f197f134
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177090"
---
# <a name="network-and-migration-planning-for-office-365"></a>Office 365의 네트워크 및 마이그레이션 계획

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

이 문서에는 네트워크 계획 및 테스트 및 마이그레이션에 대한 정보로 연결되는 링크가 포함되어 Office 365.
  
처음 배포하거나 Office 365 마이그레이션하기 전에 이러한 항목의 정보를 사용하여 필요한 대역폭을 예측한 다음, 배포 또는 마이그레이션할 수 있는 충분한 대역폭이 있는지 테스트하고 확인할 수 Office 365.

이 문서는 에 대한 네트워크 계획 및 성능 [조정의 Office 365.](./network-planning-and-performance.md)

네트워크 및 기타 Microsoft 클라우드 플랫폼 및 Microsoft 365 최적화하는 단계는 Microsoft [Cloud Networking for Enterprise Architects](../solutions/cloud-architecture-models.md) 포스터를 참조하세요.
   
## <a name="estimate-network-bandwidth-requirements"></a>네트워크 대역폭 요구 사항 예측
<a name="EstimateBandwidthRequirements"> </a>

이 Office 365 사용하는 경우 조직의 인터넷 회로 사용률이 증가할 수 있습니다. 현재 사용 가능한 대역폭의 양이 사용량이 가장 많은 일 수를 처리할 수 있는 용량을 20% Office 365 완전히 배포된 후 예상 증가를 처리할 수 있는지 확인하는 것이 중요합니다.
  
대역폭을 예측하기 위해 다음 단계를 사용합니다.
  
1. 각 인터넷 연결을 사용할 클라이언트 수를 평가합니다. 다중 테라비트 네트워크에서 가능한 한 많은 연결을 처리합니다. 
    
2. 클라이언트가 Office 365 사용할 수 있는 서비스 및 기능을 결정하십시오. 서비스 또는 사용 프로필이 다른 사용자 그룹이 있을 수 있습니다.
    
3. 파일럿 클라이언트 그룹에 대한 네트워크 사용을 측정합니다. 파일럿 클라이언트가 조직의 여러 사용자 프로필과 다양한 지리적 위치를 대표하는지 확인 이전 계산기에서 자체 네트워크에서 수행한 Exchange Microsoft Teams [](/microsoftteams/prepare-network) 사례 연구에 대해 [](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) 결과를 교차 검사할 수 있습니다. [](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) 
    
4. 파일럿 그룹의 측정값을 사용하여 전체 조직의 요구 사항을 추정하고 다시 테스트하여 네트워크를 변경하기 전에 예측의 유효성을 검사합니다.
    
## <a name="test-your-existing-network"></a>기존 네트워크 테스트
<a name="calculators"> </a>

 **네트워크 도구.** 인터넷 대역폭을 테스트하고 유효성을 검사하여 다운로드, 업로드 및 대기 시간 제약 조건을 확인합니다. 이러한 도구는 완전히 배포된 후뿐만 아니라 마이그레이션을 위한 네트워크의 기능을 결정하는 데 도움이 됩니다. 
    
- [Microsoft 원격 연결 분석기:](https://go.microsoft.com/fwlink/p/?LinkId=517243)사용자 환경의 Exchange Online 테스트합니다.
    
- Microsoft 지원 및 복구 도우미 [사용하여](https://diagnostics.office.com/#/Download?env=SOC) Office 365 문제를 Outlook Office 365 해결합니다. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>네트워크 계획 및 마이그레이션 성능 향상을 위한 모범 사례 Office 365
<a name="BestPractices"> </a>

사용자 환경 개선에 대한 자세한 내용은 이러한 모범 사례를 좀 더 Office 365 하세요.
  
1. 사용자를 바로 지원하기 시작하고 싶나요? [네트워크가](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) 협조하지 않는 경우 Office 365 Office 365 온라인, SharePoint, Exchange Online 및 Lync Online을 비롯한 느린 네트워크에서 SharePoint 사용에 대한 팁을 참조하세요. 이 문서는 TechNet 및 Support.office.com 콘텐츠 로드에 연결하여 Office 365 Internet Explorer 환경을 최적화하는 방법에 대해 안내하며, 웹 페이지를 사용자 지정하는 쉬운 방법과 최상의 Office 365 환경을 설정하는 방법에 대한 정보를 제공합니다. 
    
2. 네트워크 [Office 365](./microsoft-365-network-connectivity-principles.md) 원칙을 읽고 트래픽을 안전하게 관리하고 최상의 성능을 Office 365 연결 원칙을 이해합니다. 이 문서는 Office 365 네트워크 연결을 안전하게 최적화하기 위한 최신 가이드를 이해하는 데 도움이 됩니다. 
    
3. 업데이트에 대한 일정을 신중하게 관리하여 메일 마이그레이션 Windows 향상합니다. 클라이언트 컴퓨터를 일괄적으로 업데이트하고 네트워크 대역폭 사용을 규제하기 위해 클라이언트 컴퓨터로 마이그레이션하기 전에 Office 365 업데이트할 수 있습니다. 자세한 내용은 최신 업데이트에 대한 데스크톱 수동 업데이트 [Office 365 구성을 참조하세요.](https://support.microsoft.com/gp/office-2013-365-update)
    
4. Office 365 네트워크 트래픽은 신뢰할 수 있는 인터넷 서비스로 취급되어 일부 조직에서 신뢰할 수 없는 인터넷 서비스에 대한 네트워크 트래픽에 적용하는 기존의 필터링 및 검색을 무시할 수 있는 경우 가장 잘 수행됩니다. 여기에는 일반적으로 프록시 사용자 인증 및 패킷 검사와 같은 아웃바운드 처리가 제거될 뿐만 아니라, 적절한 NAT(Network Address Translation) 및 증가하는 네트워크 요청을 처리할 수 있는 충분한 대역폭 용량을 사용하여 인터넷으로 로컬로 전송하도록 보장하는 작업도 포함됩니다. 네트워크에서 [](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)Office 365 인터넷 서비스로 사용할 수 있도록 네트워크를 구성하는 방법에 대한 추가 지침은 Office 365 끝점 관리를 참조하세요.
    
1. 끝점 [Office 365 관리합니다.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a) 이로 Office 365 트래픽이 늘어나면 아웃바운드 프록시 연결이 증가하고 TLS/SSL을 통해 보안 트래픽이 증가합니다.
    
2. 아웃바운드 Proxy에 사용자 인증이 필요한 경우 연결 속도가 느려지거나 기능이 손실될 수 있습니다. Office 365 도메인에 대한 인증 요구 사항을 무시하면 이 오버헤드를 줄일 수 있습니다.
    
3. 공유 일정 및 사서함 수가 많은 경우 공유 일정과 사서함 수가 증가할 Outlook 수 Exchange. 예를 들어 Outlook 클라이언트는 사용 중인 각 공유 일정에 대해 최대 두 개의 추가 연결을 열 수 있습니다. 이 경우, egress 프록시가 연결을 처리하거나 해당 연결을 위해 프록시를 Office 365 Outlook.
    
4. 공용 IP 주소에 대해 지원되는 최대 장치 수와 여러 IP 주소에서 부하를 분산하는 방법을 결정하십시오. 자세한 내용은 에서 NAT 지원을 [Office 365.](nat-support-with-microsoft-365.md)
    
5. 네트워크의 컴퓨터에서 아웃바운드 연결을 검사하는 경우 이 필터링을 Office 365 도메인으로 무시하면 연결 및 성능이 향상됩니다. 또한 아웃바운드 검사를 무시하면 단일 인터넷으로의 인터넷을 유출할 필요가 제거되는 경우가 자주 있으며, 이 경우 해당 네트워크 요청에 대해 로컬 Office 365 수 있습니다.
    
6. 일부 고객은 내부 네트워크 설정이 성능에 영향을 줄 수 있습니다. 설정 MTU(최대 전송 단위) 크기, 네트워크 자동 협상 또는 자동 검색, 인터넷에 대한 최적 경로 등의 설정은 일반적으로 볼 수 있는 위치입니다.
    
## <a name="network-planning-reference-for-office-365"></a>네트워크 계획 참조를 Office 365
<a name="NetReference"> </a>

이러한 항목에는 네트워크 Office 365 자세한 정보가 포함되어 있습니다.
  
- [Office 365 끝점 관리](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [콘텐츠 배달 네트워크](content-delivery-networks.md)
    
- [Office 365에 대한 외부 Domain Name System 레코드](external-domain-name-system-records.md)
    
- [Office 365 서비스의 IPv6 지원](ipv6-support.md)
    
- [Office 365 네트워크 연결 원칙](./microsoft-365-network-connectivity-principles.md)
    
- [Office 365 서비스에 연결되는 네트워크 장치 계획](plan-for-network-devices.md)
    
- [Office 365 설치 가이드](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 개요](microsoft-365-overview.md)