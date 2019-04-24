---
title: Azure 및 GDPR의 위반 알림
description: Azure가 개인 데이터 위반으로부터 보호하는 방법 및 Microsoft가 위반 발생 시 대응하고 사용자에게 알리는 방법입니다.
keywords: Azure, Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR
author: herviicban
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: heicba
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 287175d6f78efa1052e446b230f39c33fc4d5fc6
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286433"
---
# <a name="azure-and-breach-notification-under-the-gdpr"></a>Azure 및 GDPR의 위반 알림

Microsoft Azure는 GDPR(일반 데이터 보호 규정)에 따라 의무를 다합니다. Microsoft Azure는 데이터 침해로부터 보호하기 위해 광범위한 보안 조치를 취합니다. 여기에는 물리적 및 논리적 보안 제어 뿐만 아니라 자동화된 보안 프로세스, 포괄적인 정보 보안 및 개인 정보 보호 정책, 모든 직원에 대한 개인 정보 보호 교육이 포함됩니다.

설계 단계부터 개인 정보 보호(Privacy-by-Design) 및 기본적으로 개인 정보 보호(Privacy-by-Default) 방법을 통합하는 필수 개발 프로세스인 [보안 개발 수명 주기](https://www.microsoft.com/sdl/)를 통해 처음부터 Microsoft Azure에 보안이 기본적으로 제공됩니다. Microsoft 보안 전략의 주요 원칙은 심층 방어 전략이 확장된 "위반 예측"입니다. Microsoft는 Azure의 보안 기능을 지속적으로 개선함으로써 새로운 위협에 앞서나갈 수 있습니다. Azure 보안에 대한 자세한 내용은 다음 [리소스](https://www.microsoft.com/trustcenter/security/azure-security)를 참조하세요.

Microsoft에는 Microsoft Azure에 대한 공격 영향력을 완화하기 위해 작동하는 글로벌 연중무휴 인시던트 응답 서비스가 제공됩니다. 여러 보안 및 준수 감사(예: [ISO/IEC 27018](https://www.microsoft.com/trustcenter/compliance/iso-iec-27018))를 통해 입증된 결과에 따라, Microsoft는 데이터 센터에서 연중무휴 CCTV 모니터링, 훈련된 보안 직원, 스마트 카드 및 생체 인식 제어를 비롯한 엄격한 운영 및 프로세스를 사용하여 무단 액세스를 방지합니다.

#### <a name="detection-of-potential-breaches"></a>잠재적인 침해 감지
-------------------------------

최신 클라우드 컴퓨팅의 특성으로 인해, 고객 클라우드 환경에서 발생하는 모든 데이터 침해가 Microsoft Azure 서비스와 관련된 것은 아닙니다. Microsoft는 Azure 서비스에 대해 공유 책임 모델을 사용하여 보안 및 운영 책임을 정의합니다. 클라우드 서비스 공급자와 고객 모두 클라우드 보안 부분 책임이 있으므로, 공유 책임이 클라우드 서비스의 보안을 논의할 때 특히 중요합니다.

Microsoft는 고객의 책임 영역 내에서 보안 문제를 모니터링하거나 대응하지 않습니다. 고객에 의한 보안 손상은 Azure 보안 인시던트로 처리되지 않으며 고객 테넌트에서 대응 노력을 관리해야 합니다. 적절한 서비스 계약이 있는 경우, 고객 인시던트 대응이 Microsoft Azure [고객 지원 서비스](https://azure.microsoft.com/support/options/)와 협력해서 진행될 수 있습니다.또한 Microsoft Azure는 고객이 보안 인시던트 대응을 개발 및 관리하기 위해 활용할 수 있는 다양한 서비스(예: [Azure Security Center](https://azure.microsoft.com/services/security-center/))도 제공합니다.

Azure는 Microsoft Azure 인시던트 관리 플랜에 속하는 보안 인시던트 대응 프로세스에 따라 잠재적인 데이터 위반에 대응합니다. Azure의 보안 인시던트 대응은 감지, 평가, 진단, 안정화 및 닫기의 5단계 프로세스로 구현됩니다. 보안 인시던트 대응 팀은 조사가 진행되면서 진단 및 안정화 단계 간을 전환할 수 있습니다. 보안 인시던트 대응 프로세스의 개요는 다음과 같습니다.

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">단계</th>
<th align="left">설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">감지</td>
<td align="left">잠재적인 인시던트의 최초 지표</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">평가</td>
<td align="left">출장 인시던트 대응 팀 구성원이 이벤트의 영향 및 심각도를 평가합니다. 이러한 평가는 증거에 따라 보안 대응 팀을 향한 추가 에스컬레이션으로 이어질 수도 있고 그렇지 않을 수도 있습니다.</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">진단</td>
<td align="left"><p>보안 응답 전문가가 해당 기술 또는 법정 조사를 수행하고, 방지, 완화 및 해결 전략을 파악합니다.</p>
<p>보안 팀에서 고객 데이터가 불법적이거나 허가되지 않은 개인에게 노출되었을 수 있다고 판단할 경우 고객 인시던트 알림 프로세스가 동시에 실행될 수 있습니다.</p></td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left">안정화 및 복구</td>
<td align="left">인시던트 대응 팀이 문제를 완화하기 위한 복구 계획을 세웁니다. 영향을 받은 시스템을 격리하는 것과 같은 위기 방지 단계가 즉시 진행되거나 진단과 동시에 수행될 수 있습니다. 즉각적인 위험이 지나간 후에 좀 더 장기적인 완화를 계획할 수 있습니다.</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left">종료 및 사후 평가</td>
<td align="left">인시던트 대응 팀은 정책, 절차 및 프로세스를 수정하여 이벤트 재발을 방지하기 위해 인시던트의 세부 정보를 대략적으로 설명하는 사후 평가를 만듭니다.</td>
</tr>
</tbody>
</table>

[클라우드의 Microsoft Azure 보안 응답](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) 백서에서는 Microsoft가 Azure 내의 보안 인시던트를 조사, 관리 및 대응하는 방법을 설명합니다.

Microsoft Azure에서 사용하는 감지 프로세스는 Azure 서비스의 기밀성, 무결성 및 가용성을 침해하는 이벤트를 검색하도록 고안되었습니다. 다음과 같은 일부 이벤트가 조사를 트리거할 수 있습니다.

-   내부 모니터링 및 경고 프레임워크를 통한 자동화된 시스템 경고. 이러한 경고는 맬웨어 방지, 침입 감지와 같은 서명 기반 경보나 비정상 상황 발생 시 예상되는 작업 및 경고를 프로파일링하도록 설계된 알고리즘을 통해 제공됩니다.

-   첫 번째 파티는 Microsoft Azure 및 Azure Government에서 실행되는 Microsoft 서비스에서 보고합니다.

-   보안 취약성이 <secure@microsoft.com>을 통해 [MSRC(Microsoft Security Response Center)](https://technet.microsoft.com/security/dn440717)로 보고됩니다. MSRC는 전 세계의 파트너 및 보안 연구자들과 협력하여 보안 인시던트를 방지하고 Microsoft 제품 보안을 향상시키도록 지원합니다.

-   고객은 [고객 지원 포털](http://www.windowsazure.com/support/contact/) 또는 Microsoft Azure 및 Azure Government 관리 포털을 통해 보고하며 Azure 인프라에 영향을 주는 의심스러운 작업(고객의 책임 범위 내에서 발생하는 작업과는 반대됨)을 설명합니다.

-   보안 [레드팀 및 블루팀](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) 활동. 이 전략에서는 공격적인 Microsoft 보안 전문가로 이루어진 고도로 숙련된 레드팀을 활용하여 Azure의 잠재적인 약점을 알아내고 공격합니다. 보안 대응 블루팀은 레드팀의 활동을 감지하고 견제합니다.레드팀 및 블루팀 작업은 둘 다 Azure의 보안 대응 노력이 보안 인시던트를 효과적으로 관리하고 있는지를 확인하는 데 사용됩니다. 보안 레드팀 및 블루팀 활동은 고객 데이터 보호를 지원하기 위한 협약의 규칙에 따라 운영됩니다.

-   Azure 서비스 운영자에 의한 에스컬레이션. Microsoft 직원들은 잠재적인 보안 문제를 식별하고 에스컬레이션하도록 교육을 받습니다.

#### <a name="azures-data-breach-response"></a>Azure의 데이터 위반 대응
----------------------------

Microsoft는 업무에 미치는 영향, 복구 가능성 및 인시던트의 영향 정보를 확인하여 조사 작업에 적절한 우선 순위 및 심각도를 할당합니다. 우선 순위와 심각도는 조사를 진행하는 동안 새롭게 알아낸 사실과 결론에 따라 변경될 수 있습니다. 고객 데이터에 대한 임박하거나 확인된 위험을 수반하는 보안 이벤트는 높은 심각도로 취급되며, 해결 방안을 찾기 위해 24시간 내내 작업이 진행됩니다. Microsoft Azure는 인시던트의 영향 정보를 다음 위반 범주로 분류합니다.

<table>
<thead>
<tr class="header">
<th align="left">범주</th>
<th align="left">정의</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">없음</td>
<td align="left">정보가 노출, 변경, 삭제 또는 다른 방식으로 손상되지 않았습니다.</td>
</tr>
<tr class="even">
<td align="left">개인 정보 보호 위반</td>
<td align="left">납세자, 직원, 수익자 등의 중요한 개인 데이터가 액세스되었거나 노출되었습니다.</td>
</tr>
<tr class="odd">
<td align="left">독점 위반</td>
<td align="left">PCII(보호되는 중요한 인프라 정보)와 같은 분류되지 않은 소유 정보가 액세스되었거나 노출되었습니다.</td>
</tr>
<tr class="even">
<td align="left">무결성 손실</td>
<td align="left">중요한 정보 또는 소유 정보가 변경되었거나 삭제되었습니다.</td>
</tr>
</tbody>
</table>

보안 대응 팀은 Microsoft Azure 보안 엔지니어 및 SME와 공조하여 증거를 통한 실제 데이터를 기준으로 이벤트를 분류합니다. 보안 이벤트를 다음과 같이 분류할 수 있습니다.

-   **가양성:** 검색 조건을 충족하지만 정상적인 비즈니스 방식의 일부로 확인되며 필터링할 필요가 있는 이벤트입니다. 서비스 팀은 가양성에 대한 근본 원인을 파악하고, 감지 원본을 활용하고 필요에 따라 미세 <span id="_Toc350859432" class="anchor"></span>조정하여 체계적인 방식으로 처리합니다.

-   **보안 인시던트:** Microsoft 장비 또는 Microsoft 시설에 저장되어 있는 모든 고객 데이터 또는 지원 데이터에 대한 불법 액세스 또는 이러한 장비 또는 시설에 대한 무단 액세스로 인해 고객 데이터 또는 지원 데이터가 손실, 노출 또는 변경되는 인시던트입니다.

-   **CRSI(고객 보고 가능 보안 인시던트):** Microsoft의 시스템, 장비 또는 시설을 불법적으로 또는 허가 없이 액세스하거나 사용하여 고객 데이터를 공개, 수정 또는 손실하는 경우입니다.

-   **개인 정보 위반:** 개인 데이터와 관련된 보안 인시던트의 하위 형식입니다. 처리 절차는 보안 인시던트와 다르지 않습니다.

CRSI가 선언되려면, Microsoft가 고객 데이터에 대한 무단 액세스가 발생했거나 발생했을 가능성이 높고, 알림이 진행되어야 하는 법적 또는 계약 조항이 있음을 확인해야 합니다. 구체적인 고객 영향, 리소스 액세스 및 복구 단계가 공개되면 좋지만 반드시 그럴 필요는 없습니다.인시던트는 일반적으로 보안 인시던트의 진단 단계가 끝난 후에 CRSI로 선언됩니다. 그렇지만 모든 관려 정보를 사용할 수 있게 되는 언제든지 이러한 선언이 진해욀 수 있습니다. 보안 인시던트 관리자는 고객 인시던트 알림 프로세스를 실행하기 전에, 보고 가능한 이벤트가 발생했을 것이라는 합리적인 추측을 넘어서는 명확한 증거를 확보해야 합니다.

조사 과정 전반에서, 보안 대응 팀은 전역 법률 자문과 긴밀히 협의하면서 법률적 의무 및 고객과의 약정에 따라 법정 조치가 수행되도록 합니다. 또한 다양한 운영 환경에서 시스템 및 고객 데이터를 보고 처리하는 데 중요한 제한 사항이 적용됩니다. 고객 데이터뿐만 아니라 중요한 데이터 또는 기밀 데이터는 해당 인시던트 티켓에 기록된 인시던트 관리자의 명시적인 서면 동의 없이 프로덕션 환경 외부로 전송되지 않습니다.

Microsoft는 고객 및 비즈니스 위험이 성공적으로 방지되고, 수정 조치가 구현되는지 확인합니다. 필요한 경우 이벤트와 연결된 즉각적인 보안 위험을 해결하기 위한 긴급 완화 단계가 수행됩니다.

또한 Microsoft는 데이터 침해에 대한 내부 사후 평가도 완료합니다. 이 과정의 일부로, 대응 및 운영 절차가 충분한지 평가되고, 보안 인시던트 대응 SOP 또는 관련 프로세스에 필요할 수 있는 모든 업데이트가 파악되고 구현됩니다. 데이터 침해에 대한 내부 사후 평가는 고객이 사용할 수 없는 중대한 기밀 기록입니다. 그렇지만 사후 평가를 요약하여 다른 고객 이벤트 알림에 포함할 수 있습니다. 이러한 보고서는 Azure의 정기 감사 주기의 일부로 검토될 수 있게 외부 감사자에게 제공됩니다.

#### <a name="customer-notification"></a>고객 알림
---------------------

Microsoft Azure는 필요에 따라 데이터 침해 사실을 고객과 규제 기관에 알립니다. Microsoft은 Azure를 운영하면서 내부 구조를 과도하게 구획화하고 있습니다. 데이터 흐름 로그도 강력해졌습니다. 이러한 설계 방식은 대부분의 인시던트를 구체적인 고객의 범주에 포함할 수 있다는 장점이 있습니다. 이렇게 하는 목적은 데이터 침해 시, 영향을 받은 고객에게 정확하고 실행 가능한 방식으로 시기 적절하게 알리는 것입니다.

CRSI가 선언된 후에, 빠르게 변화하는 보안 위험이 고려되면서 가능한 한 신속하게 알림 프로세스가 진행됩니다. 일반적으로 인시던트 조사가 진행 중일 때는 알림 초안이 작성됩니다. 고객 알림은 다음 경우를 *제외하고* 침해를 선언하고 72시간 이내에 전달됩니다.

-   Microsoft가 알림을 진행할 때 다른 고객에 대한 위험이 증가할 수 있다고 판단한 경우, 예를 들어 알림이 진행될 경우 공격자가 알게 되어 수정 기회를 높일 수 있습니다.

-   Microsoft의 법률 부서 CELA(회사 외부 업무 및 법률 담당) 및 인시던트 책임 관리자가 기타 비정상적이거나 극단적인 상황을 조사한 경우.

Microsoft Azure는 알림 프로세스를 과도하게 지연시키지 않으면서, 내부 조사를 수행할 수 있도록 하고, 최종 사용자 약정을 충족하도록 지원할 수 있는 자세한 정보를 고객에게 제공합니다.

개인 데이터 침해에 대한 알림은 전자 메일을 포함하여 Microsoft가 선택한 모든 방법을 통해 고객에게 전달됩니다. 데이터 침해 알림은 [구현 지침](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)에 따라 구성될 수 있는 Azure Security Center 제공 보안 연락처 목록으로 전달됩니다. Azure Security Center에 연락처 목록이 제공되지 않으면 알림은 Azure 구독의 한 명 이상의 관리자에게 전송됩니다. 이러한 알림이 성공적으로 전달되도록 하기 위해 고객은 적용 가능한 각 구독 및 온라인 서비스 포털의 관리 연락처 정보가 올바른지 확인해야 합니다.

Microsoft Azure 또는 Azure Government 팀은 CSS(고객 서비스) 및 고객 AM(계정 관리자) 또는 TAM(기술 계정 관리자)과 같은 추가 Microsoft 직원에게도 알리도록 선택할 수 있습니다. 이러한 개인은 고객과 밀접하게 관련되어 있는 경우가 많으며 보다 빠른 수정이 이루어지는 데 도움이 될 수 있습니다.<span id="_Appendix_A" class="anchor"></span>

#### <a name="microsoft-intune-data-breach"></a>Microsoft InTune 데이터 침해
----------------------------

Microsoft Intune은 Microsoft Enterprise Mobility + Security Suite 클라우드 서비스 제품의 핵심 구성 요소입니다. 데이터 거버넌스 전략을 지원하기 위해 모든 Microsoft 클라우드 서비스는 Microsoft의 설계 단계부터 개인 정보 및 보안 유지(Privacy and Security by Design) 및 기본적으로 개인 정보 및 보안 유지(Privacy and Security by Default) 방법을 사용하여 개발됩니다.

이와 같이 Microsoft Intune 클라우드 서비스 제품은 Microsoft Azure 서비스 팀이 데이터 침해 프로세스에서 보호하기 위해 수행하는 것과 동일한 기술 및 조직적 방침을 따릅니다. 따라서 여기에 나오는 "Microsoft Azure 데이터 침해" 알림 문서에 설명된 모든 정보는 Microsoft Intune 서비스에서도 비슷합니다. 예를 들어, Microsoft Intune은 동일한 보안 인시던트 대응 프로세스 및 수명 주기(1단계: 감지부터 5단계<strong>:</strong> 닫기 및 사후 평가까지)를 유지하며, 고객 보안 인시던트 알림 프로세스도 동일합니다. 또한 Microsoft Intune은 Microsoft O365 팀과 직접 공조하여 Intune에서 모든 Microsoft O365 고객에 대한 침해 알림 의무를 이행합니다.

Microsoft에서 개인 데이터 위반을 감지하고 대처하는 방법에 대한 자세한 내용은 Service Trust Portal의 [GDPR에서 데이터 위반 알림](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)을 참조하세요.


#### <a name="learn-more"></a>자세한 정보
[Microsoft 보안 센터](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
