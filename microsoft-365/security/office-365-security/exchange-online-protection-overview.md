---
title: Exchange Online Protection(EOP) 개요
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: EOP(Exchange Online Protection)가 독립 실행형 및 하이브리드 환경에서 어떻게 프레미스 전자 메일 조직을 보호할 수 있도록 하는지 알아보십시오.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce90f1429e2c54f413ae54172a6d2f663ef6a358
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624731"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection(EOP)는 스팸, 맬웨어 및 기타 전자 메일 위협으로부터 조직을 보호하는 데 도움이 되는 클라우드 기반 필터링 서비스입니다. EOP는 사서함이 있는 모든 Microsoft 365 조직에 Exchange Online 포함됩니다.

이 문서의 나머지부분에서는 EOP의 작동 방식에 대해 설명합니다.

> [!NOTE]
> EOP는 자체적으로만 사용할 수 있으며, 하이브리드 환경에서는 사서함을 보호할 수 있으며, 하이브리드 환경에서도 EOP를 통해 사서함을 보호할 Exchange 있습니다. 자세한 내용은 독립 실행형 을 [Exchange Online Protection.](/exchange/standalone-eop/standaonline-eop)

## <a name="how-eop-works"></a>EOP의 작동 방식

EOP가 받는 전자 메일을 처리하는 방법을 확인하면 EOP의 작동 방식을 이해하는 데 도움이 됩니다.

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="정크 메일 또는 정크 메일 또는 최종 사용자 메일 배달에 대한 판결이 나기 전에 EOP, 연결, 맬웨어 방지, 메일 흐름 규칙 슬래시 정책 필터링 및 콘텐츠 필터링을 통해 전달되는 인터넷 또는 고객 피드백의 그래픽입니다.":::

- 들어오는 메시지가 EOP에 들어오면 처음에는 연결 필터링을 통과하여 보낸 사람 신뢰도를 확인합니다. 대부분의 스팸은 이 시점에서 중지된 후 EOP에서 거부됩니다. 자세한 내용은 [연결 필터링 구성](configure-the-connection-filter-policy.md)을 참조하십시오.

- 그런 다음 메시지에서 맬웨어를 검사합니다. 메시지 또는 첨부 파일에서 맬웨어가 발견된 경우 메시지는 관리자만 검사 저장소로 라우팅됩니다. 맬웨어 보호에 대한 자세한 내용은 [EOP의 맬웨어 방지 보호를 참조합니다.](anti-malware-protection.md)

- 메시지는 정책 필터링을 통해 계속 진행됩니다. 여기서 템플릿에서 만들거나 적용하는 사용자 지정 메일 흐름 규칙(전송 규칙)에 대해 메시지가 평가됩니다. 예를 들어 특정 보낸 사람으로부터 메일이 도착하면 관리자에게 알림을 보내는 규칙을 사용할 수 있습니다. DLP(데이터 손실 방지) 검사도 이 시점(EXCHANGE ENTERPRISE CAL with Services)에도 있습니다.

- 다음으로, 메시지가 스팸, 피싱 또는 대량 전자 메일을 검사하는 스팸 방지 필터링을 통과합니다. 검색된 메시지는 다른 옵션 중에서 검지 또는 사용자의 정크 메일 폴더로 보낼 수 있습니다. 자세한 내용은 [Configure anti-spam policies](configure-your-spam-filter-policies.md) 및 [Configure anti-phishing policies을 참조하십시오.](configure-anti-phishing-policies-eop.md)

이러한 모든 보호 계층을 성공적으로 전달하는 메시지는 받는 사람에게 배달됩니다.

자세한 내용은 전자 메일 보호의 순서 및 [우선 순위를 참조하세요.](how-policies-and-protections-are-combined.md)

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>EOP 계획 및 사내 전자 메일 조직용 기능

사용 가능한 EOP 구독 계획은 다음을 제공합니다.

- **EOP 독립 실행형: EOP에** 등록하여온-프레미스 전자 메일 조직을 보호합니다.

- **Exchange Online EOP 기능:** Exchange Online(독립 실행형 또는 Microsoft 365의 일부분)를 포함하는 모든 구독은 EOP를 사용하여 Exchange Online 사서함을 보호합니다.

- **Exchange Enterprise CAL with Services:** Exchange CAL with Services 라이선스를 추가로 구입한 Exchange Enterprise 조직이 있는 경우 EOP는 포함된 서비스의 일부입니다.

모든 EOP 구독 계획의 요구 사항, 중요한 제한 및 기능 가용성에 대한 자세한 내용은 Exchange Online Protection [서비스 설명을 참조하세요.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

> [!NOTE]
> 사서함이 포함된 Microsoft 365 Office 365 구독이 있는 Exchange Online EOP가 있는 것입니다. 구독에서 EOP 보안 기능을 설정하는 단계 및 추가된 보안에 대한 정보는 Office 365 Microsoft Defender를 통해 위협으로부터 보호를 [참조하세요.](protect-against-threats.md) 설치에 대한 EOP 기능에 대한 권장 설정은 EOP 및 보안용 [Microsoft Defender에](recommended-settings-for-eop-and-office365.md)대한 권장 Office 365 있습니다.

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>전자 메일 조직에 대해 EOP 설정

EOP는 간단하게 설정할 수 있으며, 특히 준수 규칙이 많지 않은 소규모 조직의 경우에는 더욱 그렇습니다. 그러나 도메인이 여러 개이거나 사용자 지정 준수 규칙 또는 하이브리드 메일 흐름을 사용하는 대규모 조직의 경우에는 EOP 설정에 더 많은 시간과 계획이 필요할 수 있습니다.

EOP를 이미 구입한 경우 [EOP 서비스 설정](/exchange/standalone-eop/set-up-your-eop-service)을 참조하여 메시징 환경을 보호하도록 EOP를 구성하는 데 필요한 모든 단계를 완료하십시오.

### <a name="eop-datacenters"></a>EOP 데이터 센터

EOP는 최고 수준의 사용 가능성을 제공하도록 설계된 전 세계 데이터 센터 네트워크에서 실행됩니다. 예를 들어 데이터 센터를 사용할 수 없더라도 서비스 중단 없이 전자 메일 메시지가 다른 데이터 센터에 자동으로 라우팅됩니다. 각 데이터 센터의 서버는 사용자 대신 메시지를 수락하여 조직과 인터넷을 분리하는 계층을 제공함으로써 서버에 대한 부하를 줄입니다. 이처럼 가용성이 뛰어난 네트워크를 통해 Microsoft는 전자 메일이 제때에 조직으로 배달되도록 할 수 있습니다.

EOP는 특정 지역 내에서만 데이터 센터 간 부하 분산을 수행합니다. 단일 지역에서 프로비전되는 경우에는 해당 영역에 대한 메일 라우팅을 사용하여 모든 메시지가 처리됩니다. 다음 목록에는 EOP 데이터 센터에 대한 영역 메일 라우팅의 작동 방식이 나와 있습니다.

- EMEA(유럽, 중동 및 아프리카)에서는 모든 Exchange Online 사서함이 EMEA 데이터 센터에 있으며 모든 메시지가 EOP 필터링용으로 EMEA 데이터 센터를 통해 라우팅됩니다.
- APAC(Asia-Pacific)에서 모든 Exchange Online 사서함은 APAC 데이터 센터에 있으며 메시지는 현재 EOP 필터링을 위해 APAC 데이터 센터를 통해 라우팅됩니다.
- 미국에서는 서비스가 다음 위치에 배포됩니다.
  - 남미: Exchange Online 사서함은 브라질과 칠레의 데이터 센터에 있습니다. 모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다. Quarantined messages are stored in the datacenter where the tenant is located.
  - 캐나다: Exchange Online 사서함은 캐나다의 데이터 센터에 있습니다. 모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다. Quarantined messages are stored in the datacenter where the tenant is located.
  - 미국: Exchange Online 사서함은 미국 데이터 센터에 있습니다. 모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다. Quarantined messages are stored in the datacenter where the tenant is located.
- GCC(정부 커뮤니티 클라우드)의 경우에는 모든 Exchange Online 사서함이 미국 데이터 센터에 있으며 모든 메시지는 EOP 필터링용으로 미국 데이터 센터를 통해 라우팅됩니다.

## <a name="eop-help-for-admins"></a>관리자를 위한 EOP 도움말

EOP 관리자의 도움말 내용은 다음과 같은 최상위 범주로 구성되어 있습니다.

- [Office 365 관리자용 Microsoft Defender에 대해 EOP, 1일차](protect-against-threats.md)구성: Microsoft Defender의 핵심에서 EOP 보호 및 검색 Office 365.

- [EOP 기능: EOP에서](eop-features.md)사용할 수 있는 기능 목록을 제공합니다.

- [EOP 서비스](/exchange/standalone-eop/set-up-your-eop-service)설정: EOP 서비스를 설정하는 단계와 추가 정보에 대한 링크를 제공합니다.

- [Google Postini, Barracuda Spam and Virus Firewall 또는 Cisco IronPort에서 EOP로](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)전환: 다른 전자 메일 보호 제품에서 EOP로 전환하는 프로세스에 대해 설명

- [독립 실행형 EOP에서](/exchange/standalone-eop/manage-recipients-in-eop)받는 사람 관리: 독립 실행형 EOP에서 메일 사용자 및 그룹을 관리하는 방법을 설명 합니다.

- [EOP의](mail-flow-in-eop.md)메일 흐름: 커넥터를 사용하여 사용자 지정 메일 흐름 시나리오를 구성하는 방법, 서비스에 연결된 도메인을 관리하는 방법 및 DBEB(디렉터리 기반 Edge 차단) 기능을 사용하도록 설정하는 방법에 대해 설명합니다.

- [EOP 및 Office 365 보안용 Microsoft Defender에](recommended-settings-for-eop-and-office365.md)대한 권장 설정: 서비스를 설정하고 프로비전한 후의 권장 구성 설정 및 고려 사항을 설명

- [Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)감사 보고서: 감사 보고서를 사용하여 서비스의 구성 변경 내용을 추적하는 방법에 대해 설명

- [EOP의](anti-spam-and-anti-malware-protection.md)스팸 방지 및 맬웨어 방지 보호: 스팸 필터링 및 맬웨어 필터링에 대해 설명하고 조직의 요구 사항을 가장 잘 충족할 수 있도록 사용자 지정하는 방법을 보여줍니다. 또한 관리자 및 최종 사용자가 격리된 메시지에 대해 수행할 수 있는 작업도 설명합니다.

- [Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)보고 및 메시지 추적 : 사용 가능한 보고서 및 문제 해결 도구에 대해 설명

- [Exchange](/exchange/exchange-admin-center) [EOP의](/exchange/standalone-eop/exchange-admin-center-eop)Exchange Online 또는 Exchange 관리 센터: 관련 EOP 기능을 관리하기 위해 EAC(Exchange 관리 센터) 관리 인터페이스를 액세스하고 탐색하는 방법에 대해 설명

- [Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): 명령줄에서 EOP 서비스를 관리할 수 있는 원격 PowerShell에 대한 정보를 제공합니다.

- [EOP에 대한 도움말 및 지원](help-and-support-for-eop.md) 도움말 및 기술 지원 서비스를 구하는 내용에 대해 설명합니다.