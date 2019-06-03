---
title: Dynamics 365 및 GDPR의 위반 알림
description: Dynamics 365가 개인 데이터 위반으로부터 보호하는 방법 및 Microsoft가 위반 발생 시 대응하고 사용자에게 알리는 방법입니다.
keywords: Dynamics 365, Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: heicba
author: herviicban
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: c69bc0a0ac665fbcac68e3ba45abc7bf8f7e0ded
ms.sourcegitcommit: ea1d28fc3d0b93441aaca659c843f67495c1874f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34544945"
---
# <a name="dynamics-365-and-breach-notification-under-the-gdpr"></a>Dynamics 365 및 GDPR의 위반 알림

Dynamics 365는 GDPR(일반 데이터 보호 규정)에 따른 의무를 심각하게 준수하며 데이터 침해로부터 보호하기 위해 광범위한 보안 조치를 취합니다. Microsoft는 지속적으로 Dynamics 365 고객에게 안전한 엔터프라이즈 급 서비스를 제공하기 위해 노력하고 있습니다. 이 섹션의 정보에서는 Microsoft Dynamics 365가 보안 인시던트/데이터 침해에 대한 보호를 제공하는 방법 및 이러한 인시던트에 대응하고 고객에게 알리기 위해 따라야 하는 프로세스를 요약하여 알려드립니다.

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Microsoft Dynamics 365 기본 제공 보안 기능

Microsoft Dynamics 365는 클라우드 서비스 인프라 및 기본 제공 보안 기능을 통해 데이터를 보호하는 보안 조치 및 메커니즘을 사용하여 데이터를 안전하게 유지합니다. 또한 Dynamics 365는 [보안 ID, 데이터 보호, 역할 기반 보안 및 위협 관리](https://www.microsoft.com/trustcenter/security/dynamics365-security) 영역에서 데이터 무결성 및 개인 정보 보호를 보장하는 효율적인 데이터 액세스 및 공동 작업을 제공합니다.

## <a name="incident-response-training"></a>인시던트 대응 교육

Microsoft Dynamics 365에서 작업하는 모든 직원에게는 본인의 직책에 해당되는 보안 인시던트 및 대응 절차와 관련된 교육이 제공됩니다. 모든 Microsoft Dynamics 365 직원은 가입 시 교육을 받으며, 그 이후부터 매년 연간 재교육을 받습니다. 이 교육은 직원들이 Microsoft의 보안 접근 방식을 기본적으로 이해하도록 하므로 교육이 끝나면 모든 직원들은 다음 사항을 이해할 수 있게 됩니다.

- 보안 인시던트의 정의
- 보안 인시던트를 보고할 모든 직원의 책임
- 잠재적인 보안 인시던트를 Dynamics 365 보안 인시던트 대응 팀으로 에스컬레이션하는 방법
- Dynamics 365 보안 인시던트 대응 팀이 보안 인시던트에 대응하는 방법
- 개인 정보 보호, 특히 고객 개인 정보 보호와 관련된 문제 인식
- 보안 및 개인 정보, 에스컬레이션 담당자에 대한 추가 정보를 확인할 수 있는 위치

## <a name="how-does-microsoft-dynamics-365-define-security-incidentpotential-breaches"></a>Microsoft Dynamics 365가 보안 인시던트/잠재적인 침해를 정의하는 방식

보안 인시던트/데이터 침해는 Microsoft 장비 또는 Microsoft 시설에 저장된 고객 데이터에 대한 불법 액세스 또는 고객 데이터의 손실, 노출 또는 변경을 야기할 수 있는 이러한 장비나 시설에 대한 무단 액세스와 같은 이벤트를 나타냅니다. 보안 인시던트/데이터 침해에 대응할 때 Microsoft의 목표는 고객 데이터 및 Dynamics 365 서비스를 보호하는 것입니다. 보안 인시던트 관리를 위한 Microsoft의 접근 방법은 [NIST(National Institute of Standards and Technology)](https://www.nist.gov/) SP(특수 발행물) [800-61](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf)을 준수합니다.

Microsoft는 고객의 책임 영역 내에서 보안 문제를 모니터링하거나 대응하지 않습니다. 고객에 의한 보안 손상은 Dynamics 365 보안 인시던트로 처리되지 않으며 고객 테넌트에서 대응 노력을 관리해야 합니다. 적절한 서비스 계약이 있는 경우, 고객 인시던트 대응이 Microsoft Dynamics 365 고객 지원 서비스와 협력해서 진행될 수 있습니다.

## <a name="detection-of-potential-breaches"></a>잠재적인 침해 감지

Dynamics 365는 Microsoft Dynamics 365 인시던트 관리 플랜에 속하는 보안 인시던트 대응 프로세스에 따라 잠재적인 데이터 위반에 대응합니다. Dynamics 365의 보안 인시던트 대응은 감지, 평가, 진단, 안정화 및 종료의 5단계 프로세스로 구현됩니다. 보안 인시던트 대응 팀은 조사가 진행되면서 진단 및 안정화 단계 간을 전환할 수 있습니다. 보안 인시던트 대응 프로세스의 개요는 다음과 같습니다.

|**단계**|**설명**|
|:-----|:-----|
| ***1-감지*** | 잠재적인 인시던트의 최초 지표 |
| ***2-평가*** | 출장 인시던트 대응 팀 구성원이 이벤트의 영향 및 심각도를 평가합니다. 이러한 평가는 증거에 따라 보안 대응 팀을 향한 추가 에스컬레이션으로 이어질 수도 있고 그렇지 않을 수도 있습니다. |
| ***3-진단*** | 보안 응답 전문가가 해당 기술 또는 법정 조사를 수행하고, 방지, 완화 및 해결 전략을 파악합니다. 보안 팀에서 고객 데이터가 불법적이거나 허가되지 않은 개인에게 노출되었을 수 있다고 판단할 경우 고객 인시던트 알림 프로세스가 동시에 실행될 수 있습니다.|
| ***4 - 안정화 및 복구*** | 인시던트 대응 팀이 문제를 완화하기 위한 복구 계획을 세웁니다. 영향을 받은 시스템을 격리하는 것과 같은 위기 방지 단계가 즉시 진행되거나 진단과 동시에 수행될 수 있습니다. 즉각적인 위험이 지나간 후에 좀 더 장기적인 완화를 계획할 수 있습니다. |
| ***5 - 종료 및 사후 평가*** | 인시던트 대응 팀은 정책, 절차 및 프로세스를 수정하여 이벤트 재발을 방지하기 위해 인시던트의 세부 정보를 대략적으로 설명하는 사후 평가를 만듭니다. |

[Dynamics 보안 인시던트 관리](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=266d445f-ea95-42de-9124-4b2118a639ee&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) 백서에서는 Microsoft가 Dynamics 365 내의 보안 인시던트를 조사, 관리 및 대응하는 방법을 설명합니다.

Microsoft Dynamics 365에서 사용하는 감지 프로세스는 Dynamics 365 서비스의 기밀성, 무결성 및 가용성을 침해하는 이벤트를 검색하도록 고안되었습니다. 다음과 같은 일부 이벤트가 조사를 트리거할 수 있습니다.

- 내부 모니터링 및 경고 프레임워크를 통한 자동화된 시스템 경고. 이러한 경고는 맬웨어 방지, 침입 감지와 같은 서명 기반 경보나 비정상 상황 발생 시 예상되는 작업 및 경고를 프로파일링하도록 설계된 알고리즘을 통해 제공됩니다.
- 공용 클라우드에 배포된 Microsoft Dynamics 365 서비스 및 Sovereign 클라우드에 배포된 Microsoft Dynamics 365 서비스를 실행하는 자사 보고서
- 보안 취약성이 <secure@microsoft.com>을 통해 [MSRC(Microsoft Security Response Center)](https://technet.microsoft.com/security/dn440717)로 보고됩니다. MSRC는 전 세계의 파트너 및 보안 연구자들과 협력하여 보안 인시던트를 방지하고 Microsoft 제품 보안을 향상시키도록 지원합니다.
- Microsoft Dynamics 365 서비스에 영향을 미치는 의심스러운 활동(고객 책임 범위에서 발생하는 활동과 반대됨)을 설명하는 고객 보고서
- 보안 [Red 팀 및 Blue 팀](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) 활동. 이 전략은 불법 보안 전문가로 구성된 고도로 훈련된 Red 팀을 사용하여 Microsoft Dynamics 365 서비스에서 잠재적인 취약점을 밝히고 공격할 수 있습니다. 보안 응답 Blue 팀은 Red 팀의 활동을 감지하고 방어해야 합니다. Microsoft Dynamics 365 보안 대응 노력으로 보안 문제를 효과적으로 관리하는지 확인하는 데 Red 및 Blue 팀 작업이 모두 사용 됩니다. 보안 Red 팀 및 Blue 팀 활동은 고객 데이터 보호를 보장해야 하는 책임의 요구 사항으로 운영됩니다.
- Microsoft Dynamics 365 서비스 운영자에 의한 에스컬레이션. Microsoft 직원은 잠재적인 보안 문제를 식별하고 에스컬레이션하도록 교육을 받았습니다.

## <a name="microsoft-dynamics-365-data-breach-response"></a>Microsoft Dynamics 365 데이터 침해 대응

Microsoft는 업무에 미치는 영향, 복구 가능성 및 인시던트의 영향 정보를 확인하여 조사 작업에 적절한 우선 순위 및 심각도를 할당합니다. 우선 순위와 심각도는 조사를 진행하는 동안 새롭게 알아낸 사실과 결론에 따라 변경될 수 있습니다. 고객 데이터에 대해 임박한 위험 또는 확인된 위험을 수반하는 보안 이벤트는 높은 심각도로 취급되며, 해결 방안을 찾기 위해 24시간 내내 작업이 진행됩니다. Microsoft Dynamics 365는 개인 정보 침해를 “온라인 서비스 최종 사용자 또는 Microsoft 직원의 개인 데이터” 침해로 정의합니다.

보안 대응 팀은 Microsoft Dynamics 365 보안 엔지니어 및 SME(실무 전문가)와 공조하여 증거를 통한 실제 데이터를 기준으로 이벤트를 분류합니다. 보안 이벤트를 다음과 같이 분류할 수 있습니다.

- **가양성:** 검색 조건을 충족하지만 정상적인 비즈니스 방식의 일부로 확인되며 필터링할 필요가 있는 이벤트입니다. 서비스 팀은 가양성에 대한 근본 원인을 파악하고, 감지 원본을 활용하고 필요에 따라 미세 <span id="_Toc350859432" class="anchor"></span>조정하여 체계적인 방식으로 처리합니다.
- **보안 인시던트:** Microsoft 장비 또는 Microsoft 시설에 저장되어 있는 모든 고객 데이터 또는 지원 데이터에 대한 불법 액세스 또는 이러한 장비 또는 시설에 대한 무단 액세스로 인해 고객 데이터 또는 지원 데이터가 손실, 노출 또는 변경되는 인시던트입니다.
- **CRSI(고객 보고 가능 보안 인시던트):** Microsoft의 시스템, 장비 또는 시설을 불법적으로 또는 허가 없이 액세스하거나 사용하여 고객 데이터를 공개, 수정 또는 손실하는 경우입니다.
- **개인 정보 인시던트:** 개인 데이터와 관련된 보안 인시던트의 하위 형식입니다. 처리 절차는 보안 인시던트와 다르지 않습니다.

CRSI를 선언하려면 Microsoft에서 고객 데이터에 무단 액세스가 발생했거나 발생했을 가능성이 높은지 및/또는 알림이 있어야 한다는 법적 또는 계약상 약정이 있는지를 판단해야 합니다. 필수는 아니지만 특정 고객 영향, 리소스 액세스 및 복구 단계를 알고 있다고 기대합니다. 일반적으로 인시던트는 보안 인시던트의 진단 단계를 마친 후 CRSI로 선언됩니다. 그러나 모든 관련 정보를 사용할 수 있는 모든 위치에서 선언이 발생할 수 있습니다. 보안 인시던트 관리자는 보고 가능한 이벤트가 발생하여 고객 인시던트 알림 프로세스가 실행되기 시작했다는 것에 대해 합리적 의심을 넘어서 증명해야 합니다.

조사 과정 전반에서, 보안 대응 팀은 전역 법률 자문과 긴밀히 협의하면서 법률적 의무 및 고객과의 약정에 따라 법정 조치가 수행되도록 합니다. 또한 다양한 운영 환경에서 시스템 및 고객 데이터를 보고 처리하는 데 중요한 제한 사항이 적용됩니다. 고객 데이터뿐만 아니라 중요한 데이터 또는 기밀 데이터는 해당 인시던트 티켓에 기록된 인시던트 관리자의 명시적인 서면 동의 없이 프로덕션 환경 외부로 전송되지 않습니다.

Microsoft는 고객 및 비즈니스 위험이 성공적으로 방지되고, 수정 조치가 구현되는지 확인합니다. 필요한 경우 이벤트와 연결된 즉각적인 보안 위험을 해결하기 위한 긴급 완화 단계가 수행됩니다.

Microsoft는 또한 데이터 유출을 위한 내부 사후 평가을 완료합니다. 이 연습의 일환으로 응답 및 운영 절차의 충분성이 평가되고 Microsoft 내부 보안 정책 또는 관련 프로세스에 필요한 업데이트가 식별되고 구현됩니다. 데이터 유출에 대한 내부 사후 평가는 고객이 이용할 수 없는 극비 기록입니다. 그러나 사후 평가는 요약되어 다른 고객 이벤트 통지에 포함될 수 있습니다. 이 보고서는 Dynamics 365의 정기 감사 주기의 일부로 검토를 위해 외부 감사인에게 제공됩니다.

## <a name="customer-notification"></a>고객 알림

Microsoft Dynamics 365는 필요에 따라 데이터 침해 사실을 고객과 규제 기관에 알립니다. Microsoft은 Dynamics 365를 운영하면서 내부 구조를 과도하게 구획화하고 있습니다. 데이터 흐름 로그도 강력해졌습니다. 이러한 설계 방식은 대부분의 인시던트를 구체적인 고객의 범주에 포함할 수 있다는 장점이 있습니다. 이렇게 하는 목적은 데이터 침해 시, 영향을 받은 고객에게 정확하고 실행 가능한 방식으로 시기 적절하게 알리는 것입니다.

빠르게 변화하는 보안 위험이 고려되면서, 선언된 CRSI에 대해 가능한 한 신속하게 알림 프로세스가 진행됩니다. 일반적으로 인시던트 조사가 진행 중일 때는 알림 초안이 작성됩니다. 고객 알림은 다음 경우를 *제외하고* 침해 발생 후 즉시 전달됩니다.

- Microsoft가 알림을 진행할 때 다른 고객에 대한 위험이 증가할 수 있다고 판단한 경우, 예를 들어 알림이 진행될 경우 공격자가 알게 되어 수정 기회를 높일 수 있습니다.
- Microsoft의 법률 부서 및 인시던트 책임 관리자가 기타 비정상적이거나 극단적인 상황을 조사한 경우.

Microsoft Dynamics 365는 알림 프로세스를 과도하게 지연시키지 않으면서, 내부 조사를 수행할 수 있도록 하고, 최종 사용자 약정을 충족하도록 지원할 수 있는 자세한 정보를 고객에게 제공합니다.

개인 데이터 침해에 대한 알림은 전자 메일을 포함하여 Microsoft가 선택한 모든 방법을 통해 고객에게 전달됩니다. 데이터 침해 알림은 고객/테넌트 관리자가 구성할 수 있는 Office 보안 센터에 제공된 고객 연락처/관리자(영향 받은 테넌트만 해당) 목록으로 전달됩니다. 이러한 알림이 성공적으로 전달되도록 하기 위해 고객은 적용 가능한 각 구독 및 온라인 서비스 포털의 관리 연락처 정보가 올바른지 확인해야 합니다.

Microsoft Dynamics 365 팀은 CSS(고객 서비스) 및 고객 AM(계정 관리자) 또는 TAM(기술 계정 관리자)과 같은 추가 Microsoft 직원에게도 알리도록 선택할 수 있습니다. 이러한 개인은 고객과 밀접하게 관련되어 있는 경우가 많으며 보다 빠른 수정이 이루어지는 데 도움이 될 수 있습니다.<span id="_Appendix_A" class="anchor"></span>

## <a name="learn-more"></a>자세한 정보

- [Microsoft 보안 센터](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)