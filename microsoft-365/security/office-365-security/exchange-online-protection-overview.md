---
title: EOP (Exchange Online Protection) 개요
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: EOP (Exchange Online Protection)를 사용 하 여 독립 실행형 및 하이브리드 환경에서 온-프레미스 전자 메일 조직을 보호 하는 방법을 알아봅니다.
ms.openlocfilehash: b546b60e242d7f4f7fd4c4550bb61b94052ff4d1
ms.sourcegitcommit: eb905c5b4d7e71fc930a207357295b0160c4f065
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2020
ms.locfileid: "48137022"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 개요

EOP (Exchange Online Protection)는 스팸 및 맬웨어로부터 조직을 보호 하는 클라우드 기반 필터링 서비스입니다. EOP는 Exchange Online 사서함이 있는 모든 Microsoft 365 조직에 포함 되어 있습니다. 그러나 EOP는 다음과 같은 온-프레미스 시나리오 에서도 사용할 수 있습니다.

- **독립 실행형 시나리오에서**EOP는 온-프레미스 Exchange 조직 또는 기타 모든 온-프레미스 SMTP 전자 메일 솔루션에 대해 클라우드 기반 전자 메일 보호 기능을 제공 합니다.

- **하이브리드 배포에서**: 온-프레미스 및 클라우드 사서함을 함께 사용 하는 경우 전자 메일 환경을 보호 하 고 메일 라우팅을 제어 하도록 EOP를 구성할 수 있습니다.

이러한 시나리오에서 EOP는 전자 메일 환경 관리를 단순화 하 고 온-프레미스 하드웨어 및 소프트웨어 유지 관리와 함께 제공 되는 많은 부담을 완화할 수 있습니다.

이 항목의 나머지 부분에서는 독립 실행형 및 하이브리드 환경에서 EOP가 작동 하는 방식에 대해 설명 합니다.

## <a name="how-eop-works"></a>EOP의 작동 방식

EOP가 받는 전자 메일을 처리하는 방법을 확인하면 EOP의 작동 방식을 이해하는 데 도움이 됩니다.

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="정크 메일 또는 격리 또는 최종 사용자 메일 배달이 결과 되기 전, EOP에 전달 되는 인터넷 또는 고객 의견이 나 연결, 맬웨어 방지, 메일 흐름 규칙-슬래시 정책 필터링, 콘텐츠 필터링 등을 통해 전자 메일을 그래픽으로 표시 합니다.":::

- 들어오는 메시지가 EOP 입력 되 면 처음에는 보낸 사람의 신뢰도를 확인 하는 연결 필터링을 통과 합니다. 대부분의 스팸은이 시점에서 중지 되며 EOP에 의해 거부 됩니다. 자세한 내용은 [연결 필터링 구성](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-connection-filter-policy?view=o365-worldwide)을 참조하십시오.

- 그런 다음 메시지에 맬웨어 징후가 검사 됩니다. 메시지 또는 첨부 파일에서 맬웨어가 발견 되 면 메시지가 관리자 전용 격리 저장소로 라우팅됩니다. 맬웨어를 구성 하는 방법에 대 한 자세한 내용은 [여기](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide)에서 확인할 수 있습니다.

- 메시지는 서식 파일에서 만들거나 적용 하는 사용자 지정 메일 흐름 규칙 (전송 규칙이 라고도 함)에 대해 평가 되는 정책 필터링을 계속 합니다. 예를 들어 메일이 특정 보낸 사람에 게 서 도착 하면 관리자에 게 알림을 보내는 규칙을 만들 수 있습니다. DLP (데이터 손실 방지) 확인은이 지점에서 수행 됩니다 (Exchange Enterprise CAL with Services).

- 다음으로, 메시지는 콘텐츠 필터링 (스팸 방지 라고도 함)을 통해 전달 됩니다. 다른 옵션 중 하나를 사용 하 여이 필터로 스팸을 확인 *하거나 피싱* 를 차단 또는 사용자의 정크 메일 폴더로 보낼 수 있다는 메시지가 표시 됩니다. 자세한 내용은 [스팸 방지 정책 구성](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide) 및 [피싱 방지 정책 구성을](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-phishing-policies-eop?view=o365-worldwide)참조 하세요.

이러한 모든 보호 계층을 통과 하는 모든 메시지는 받는 사람에 게 배달 됩니다.

자세한 내용은 [전자 메일 보호의 주문 및 우선 순위](how-policies-and-protections-are-combined.md)를 참조 하세요.

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>온-프레미스 전자 메일 조직에 대 한 EOP 요금제 및 기능

사용 가능한 EOP 구독 계획은 다음과 같습니다.

- **EOP 독립 실행형**: EOP에 등록 하 여 온-프레미스 전자 메일 조직을 보호 합니다.

- **Exchange online의 EOP 기능**: exchange online (독립 실행형 또는 Microsoft 365의 일부로)이 포함 된 모든 구독은 EOP을 사용 하 여 exchange online 사서함을 보호 합니다.

- **Exchange ENTERPRISE cal With services**: 서비스 라이선스로 추가 EXCHANGE Enterprise cal을 구매한 온-프레미스 Exchange 조직이 있는 경우 EOP는 포함 된 서비스의 일부입니다.

모든 EOP 구독 계획에서 요구 사항, 중요 제한 및 기능 가용성에 대 한 자세한 내용은 [Exchange Online Protection 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)참조 하세요.

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>온-프레미스 전자 메일 조직에 대해 EOP 설정

EOP는 간단하게 설정할 수 있으며, 특히 준수 규칙이 많지 않은 소규모 조직의 경우에는 더욱 그렇습니다. 그러나 도메인이 여러 개이거나 사용자 지정 준수 규칙 또는 하이브리드 메일 흐름을 사용하는 대규모 조직의 경우에는 EOP 설정에 더 많은 시간과 계획이 필요할 수 있습니다.

EOP를 이미 구입한 경우 [EOP 서비스 설정](set-up-your-eop-service.md)을 참조하여 메시징 환경을 보호하도록 EOP를 구성하는 데 필요한 모든 단계를 완료하십시오.

### <a name="eop-datacenters"></a>EOP 데이터 센터

EOP는 최고 수준의 사용 가능성을 제공하도록 설계된 전 세계 데이터 센터 네트워크에서 실행됩니다. 예를 들어 데이터 센터를 사용할 수 없더라도 서비스 중단 없이 전자 메일 메시지가 다른 데이터 센터에 자동으로 라우팅됩니다. 각 데이터 센터의 서버는 사용자 대신 메시지를 수락 하 여 조직과 인터넷을 분리 하는 계층을 제공 함으로써 서버의 부하를 줄여 줍니다. 이처럼 가용성이 뛰어난 네트워크를 통해 Microsoft는 전자 메일이 제때에 조직으로 배달되도록 할 수 있습니다.

EOP는 특정 지역 내에서만 데이터 센터 간 부하 분산을 수행합니다. 단일 지역에서 프로비전되는 경우에는 해당 영역에 대한 메일 라우팅을 사용하여 모든 메시지가 처리됩니다. 다음 목록에는 EOP 데이터 센터에 대한 영역 메일 라우팅의 작동 방식이 나와 있습니다.

- EMEA(유럽, 중동 및 아프리카)에서는 모든 Exchange Online 사서함이 EMEA 데이터 센터에 있으며 모든 메시지가 EOP 필터링용으로 EMEA 데이터 센터를 통해 라우팅됩니다.

- APAC (아시아 태평양)에서는 모든 Exchange Online 사서함이 APAC 데이터 센터에 있고 메시지는 현재 EOP 필터링을 위해 APAC 데이터 센터를 통해 라우팅됩니다.

- 미주에서 서비스는 다음 위치에 배포 됩니다.

  - 남미: Exchange Online 사서함은 브라질 및 칠레 데이터 센터에 있습니다. 모든 메시지는 EOP 필터링의 로컬 데이터 센터를 통해 라우팅됩니다. 격리 된 메시지는 테 넌 트가 있는 데이터 센터에 저장 됩니다.

  - 캐나다: Exchange Online 사서함은 캐나다 데이터 센터에 있습니다. 모든 메시지는 EOP 필터링의 로컬 데이터 센터를 통해 라우팅됩니다. 격리 된 메시지는 테 넌 트가 있는 데이터 센터에 저장 됩니다.

  - 미국: Exchange Online 사서함은 미국 데이터 센터에 있습니다. 모든 메시지는 EOP 필터링의 로컬 데이터 센터를 통해 라우팅됩니다. 격리 된 메시지는 테 넌 트가 있는 데이터 센터에 저장 됩니다.

- GCC(정부 커뮤니티 클라우드)의 경우에는 모든 Exchange Online 사서함이 미국 데이터 센터에 있으며 모든 메시지는 EOP 필터링용으로 미국 데이터 센터를 통해 라우팅됩니다.

## <a name="eop-help-for-admins"></a>관리자를 위한 EOP 도움말

EOP 관리자의 도움말 내용은 다음과 같은 최상위 범주로 구성되어 있습니다.

- Office 365 Advanced Threat Protection의 핵심에 EOP 보호 및 검색 도구를 구성 하려면 [EOP, 1 일 365,](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide)#을 구성 합니다.

- [EOP 기능](eop-features.md): EOP에서 사용할 수 있는 기능 목록을 제공 합니다.

- [EOP Service 설정](set-up-your-eop-service.md): EOP 서비스를 설정 하는 단계와 추가 정보에 대 한 링크를 제공 합니다.

- [Google Postini, Barracuda 스팸 및 바이러스 방화벽 또는 Cisco ironpor에서 EOP로 전환](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)다른 전자 메일 보호 제품에서 EOP로 전환 하는 프로세스에 대해 설명 합니다.

- [독립 실행형 EOP에서 받는 사람 관리](manage-recipients-in-eop.md): EOP에서 메일 사용자 및 그룹을 관리 하는 방법에 대해 설명 합니다.

- [EOP의 메일 흐름](mail-flow-in-eop.md): 커넥터를 사용 하 여 사용자 지정 메일 흐름 시나리오를 구성 하는 방법, 서비스와 연결 된 도메인을 관리 하는 방법 및 DBEB (디렉터리 기반 Edge 차단) 기능을 사용 하도록 설정 하는 방법에 대해 설명 합니다.

- [EOP 구성을 위한 모범 사례](best-practices-for-configuring-eop.md): 서비스를 설정 및 프로 비전 한 후 권장 되는 구성 설정 및 고려 사항에 대해 설명 합니다.

- [독립 실행형 EOP의 감사 보고서](auditing-reports-in-eop.md): 감사 보고서를 사용 하 여 서비스에 대 한 구성 변경 내용을 추적 하는 방법에 대해 설명 합니다.

- [EOP의 스팸 방지 및 맬웨어 방지 보호](anti-spam-and-anti-malware-protection.md): 스팸 필터링 및 맬웨어 필터링에 대해 설명 하 고 조직의 요구에 가장 잘 맞게 사용자 지정 하는 방법을 보여 줍니다. 또한 관리자 및 최종 사용자가 격리된 메시지에 대해 수행할 수 있는 작업도 설명합니다.

- [Reporting and message trace In Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): 사용할 수 있는 보고서 및 문제 해결 도구에 대해 설명 합니다.

- [독립 실행형 EOP의 Exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md): EOP 서비스를 관리 하기 위해 EAC (exchange 관리 센터) 관리 인터페이스를 액세스 하 고 탐색 하는 방법에 대해 설명 합니다.

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): 명령줄에서 EOP 서비스를 관리 하는 데 사용할 수 있는 원격 PowerShell에 대 한 정보를 제공 합니다.

- [EOP에 대한 도움말 및 지원](help-and-support-for-eop.md) 도움말 및 기술 지원 서비스를 구하는 내용에 대해 설명합니다.
