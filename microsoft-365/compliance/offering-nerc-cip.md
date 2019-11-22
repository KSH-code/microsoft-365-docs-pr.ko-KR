---
title: North American Electric Reliability Corporation(북미전력안정성회사:NERC)
description: Azure 및 Azure Government는 NERC CIP 표준에 준하여 클라우드에 특정 작업을 배포하는 등록된 개체에 적합합니다.
keywords: Microsoft 365, 규정 준수, 제안
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: e2a5ece0c6604ff6e2e9073557ee0f6c59f3694f
ms.sourcegitcommit: b2197dbf723d11992bbad568a84df3ef3cff421d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2019
ms.locfileid: "39195409"
---
# <a name="compliance-offering-north-american-electric-reliability-corporation-nerc"></a>규정 준수 제안: North American Electric Reliability Corporation(북미전력안정성회사:NERC)

## <a name="about-the-nerc"></a>NERC에 대한 정보

[North American Electric Reliability Corporation](https://www.nerc.com/)(북미전력안정성회사:NERC)는 북아메리카의 대량의 전력 시스템의 안정성을 보장 하는 비영리 규제 기관입니다. NERC는 캐나다의 US Federal Energy Regulatory Commission(미국 연방 에너지 규제 위원회:FERC)와및 정부 기관의 감독을 받습니다. 2006년 FERC는 2005년의 에너지 정책 법률(Energy Policy Act)(미국 공공 법규 109-58)에 따라 NERC를 Electric Reliability Organization(전력 안정성 조직:ERO)으로 지정하였습니다. NERC는 NERC [Critical Infrastructure Protection(중요 인프라 보호:CIP) 표준](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx)으로 알려진 안정성 표준을 개발하고 적용합니다.

## <a name="microsoft-and-the-nerc-cip-standard"></a>Microsoft와 NERC CIP 표준

North American Electric Reliability Corporation(북미전력안정성회사:NERC)는 북아메리카의 대량의 전력 시스템의 안정성을 보장 하는 비영리 규제 기관입니다. NERC는 캐나다의 US Federal Energy Regulatory Commission(미국 연방 에너지 규제 위원회:FERC)와및 정부 기관의 감독을 받습니다. 2006년 FERC는 2005년의 에너지 정책 법률(Energy Policy Act)(미국 공공 법규 109-58)에 따라 NERC를 Electric Reliability Organization(전력 안정성 조직:ERO)으로 지정하였습니다. NERC는 NERC [Critical Infrastructure Protection(중요 인프라 보호:CIP) 표준](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx)으로 알려진 안정성 표준을 개발하고 적용합니다.

모든 대량의 전력 시스템 소유자, 운영자 및 사용자는 [NERC CIP 표준을 준수](https://www.nerc.com/pa/comp/Pages/default.aspx)해야 합니다. 이들은 NERC에 등록을 해야 합니다. 클라우드 서비스 공급업체와 제3자 공급업체는 NERC CIP 표준의 적용 대상이 아닙니다. 그러나 CIP 표준에는 [등록된 개체](https://www.nerc.com/pa/comp/Pages/Registration.aspx)가 대량 전력 시스템(BES)을 사용하는 경우 고려할 목표가 포함 되어 있습니다. 대량 전기 시스템을 운영하는 Microsoft 고객은 자체 NERC CIP 표준의 준수를 보장할 전체적 책임이 있습니다. Microsoft Azure나 Microsoft Azure Government 모두 BES 또는 BES 사이버 자산을 구성하지는 않습니다.

현재 [CIP 표준](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf) 및 NERC [용어 사전](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf)의 집합에서 NERC가 설명하듯이 BES 사이버 자산은 BES의 실시간 모니터링 또는 컨트롤 기능을 수행하 고 장애가 발생하는 경우 15분 내에 BES의 안정적 운영에 영향을 줄 수 있습니다. 클라우드 컴퓨팅에서 BES 사이버 자산과 보호 되는 사이버 자산을 제대로 활용하려면 NERC CIP 표준에 있는 기존의 정의를 [수정할 필요가 있습니다](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx). 그러나 CIP의 중요한 데이터를 처리하는 작업 부하가 많고 이들은 BES 사이버 시스템 정보(BCSI)의 광범위한 범주를 포함하여 15분 규칙의 적용을 받지 않습니다.

Azure 및 Azure Government는 NERC CIP 표준에 준하여 BCSI 작업을 포함하여 특정 작업을 배포하는 등록된 개체에 적합합니다. Microsoft에서는 Azure 또는 Azure Government에서의 NERC CIP 준수의 의무에 따라 데이터와 작업을 배포하는 데 관심이 있는 등록된 개체가 다음의 문서를 사용할 수 있도록 합니다.

- [NERC CIP 표준과 클라우드 컴퓨팅](https://aka.ms/AzureNERC)은 FedRAMP와 같은 클라우드 서비스 공급자에게 적용되는 제3자의 감사를 기반으로 하는 NERC CIP의 요구 사항에 대한 규정 준수를 위해 고려할 사항을 설명하는 백서입니다. 이는 클라우드 운영 담당자를 위한 백그라운드 심사를 다루고 등록된 개체의 관심사인 논리적 격리 및 멀티테넌시에 대한 일반적인 질문에 답변을 해줍니다. 또한 온-프레미스 및 클라우드 배포 시 보안과 관련하여 고려할 사항도 다룹니다.
- [NERC 감사를 위한 클라우드 구현 가이드](https://aka.ms/AzureNERCGuide)는 FedRAMP에 대한 기본을 구성하는 [NIST SP 800-53 수정 사항 4](https://nvd.nist.gov/800-53/Rev4)의 콘트롤 집합과 NERC CIP 표준 요구 사항 간의 컨트롤 매핑을 제공하는 지침서입니다. 이 지침서는 등록된 개체가 클라우드에 배포된 자산에 대한 NERC CIP 규정 준수 요구 사항을 다루는데 도움을 주기 위한 기술적 방법의 지침으로서 준비되었습니다. 이 문서는 Azure 컨트롤이 NERC CIP 요구 사항을 처리하는 방법에 대한 설명에 도움이 되는 사전에 작성된 [신뢰성 표준 감사 워크시트(RSAW)](https://www.nerc.com/pa/comp/Pages/Reliability-Standard-Audit-Worksheets-\(RSAWs\).aspx)와 등록된 개체를 위한 Azure 서비스를 사용하여 소유한 컨트롤을 구현하는 방법에 대한에 지침을 포함하고 있습니다.

NERC ERO Enterprise는 지정된 BCSI 저장소 위치로의 액세스와 등록된 개체가 구현한 모든 컨트롤을 승인하는 등록된 개체의 프로세스를 평가 시 ERO Enterprise CMEP 직원에 지침을 제공하기 위해 규정 준수 모니터링 및 적용 프로그램(CMEP) [연습 가이드](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf)를 [발행했습니다](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx). 추가로 NERC는 Azure 컨트롤 구현의 세부 정보와 NERC CIP-004-6 및 BCSI에 적용되는 CIP-011-2 표준과 관련된 FedRAMP 감사 증거를 검토하였습니다. 등록된 개체의 데이터 암호화를 확인하기 위한 ERO에서 발행한 연습 가이드와 검토된 FedRAMP 컨트롤에 기반하여 등록된 개체가 BCSI 및 관련 작업을 클라우드에 배포하는데 추가적 지침이나 설명은 필요하지 않습니다. 그러나 등록된 개체는 고유의 사실와 상황에 따라 NERC CIP 표준의 준수에 대해 최종적으로 책임이 있습니다. 등록된 개체는 [NERC 감사에 대한 클라우드 구현 가이드](https://aka.ms/AzureNERCGuide)를 검토하여 Azure 및 Azure Government에서의 BCSI 암호화에 사용되는 암호화 키 관리를 포함하여 BCSI 저장소 위치로의 전자적 액세스 권한을 부여하는 데 사용되는 프로세스와 증거를 문서화하는데 도움을 받도록 합니다.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

- [Azure 및 Azure Government](https://aka.ms/AzureCompliance)

## <a name="audits-reports-and-certificates"></a>감사, 보고서 및 인증서

Microsoft는 P-ATOs 및 ATOs를 유지하기 위해 매년 클라우드 서비스를 재인증해야 합니다. 이를 위해 Microsoft는 계속해서 보안 컨트롤을 모니터링 및 평가하고 규정의 준수를 유지하고 있음을 입증해야 합니다.

- [Microsoft 클라우드 서비스 인증](https://marketplace.fedramp.gov/?sort=productName&productNameSearch=azure#/product/azure-government)
- [Microsoft FedRAMP 감사 보고서](https://aka.ms/MicrosoftFedRAMPAuditDocuments)

## <a name="how-to-implement"></a>구현 방법

### <a name="nerc-cip-standards-and-cloud-computing"></a>NERC CIP 표준 및 클라우드 컴퓨팅

NERC CIP 표준의 적용을 받는 작업의 클라우드 도입을 고려하는 등록된 개체를 위한 규정 준수를 다룹니다.

[자세한 정보](https://aka.ms/AzureNERC)

### <a name="cloud-implementation-guide-for-nerc-audits"></a>NERC 감사에 대한 클라우드 구현 가이드

기술적 지침은 Azure 또는 Azure Government에서 배포된 자산의 NERC 감사와 관련하여 등록된 개체에 도움을 줍니다. 

[자세한 정보](https://aka.ms/AzureNERCGuide)

## <a name="frequently-asked-questions"></a>자주하는 질문

**NERC CIP 표준을 준수할 책임은 누구에게 있나요?**

모든 대량의 전력 시스템 소유자, 운영자 및 사용자는 [NERC CIP 표준을 준수](https://www.nerc.com/pa/comp/Pages/default.aspx)해야 합니다. 이들은 NERC에 등록을 해야 합니다. 클라우드 서비스 공급업체와 제3자 공급업체는 NERC CIP 표준의 적용 대상이 아닙니다. 그러나 CIP 표준에는 [등록된 개체](https://www.nerc.com/pa/comp/Pages/Registration.aspx)가 대량 전력 시스템(BES)을 사용하는 경우 고려할 목표가 포함 되어 있습니다. 대량 전기 시스템을 운영하는 Microsoft 고객은 자체 NERC CIP 표준의 준수를 보장할 전체적 책임이 있습니다. Azure나 Azure Government 모두 BES 또는 BES 사이버 자산을 구성하지는 않습니다.

NERC CIP 표준의 적용을 받는 데이터 및 작업에 대한 Azure 및 Azure Government의 적합성을 평가하기 위해 등록된 개체는 자체 규정 준수 관리자 및 NERC 감사자와 상담을 하도록 합니다. 이들은 [NERC 감사에 대한 클라우드 구현 가이드](https://aka.ms/AzureNERCGuide)를 검토하여 클라우드에 배포된 자산에 대 한 프로세스와 정보를 문서화하는 데 도움을 받아야 합니다.

**등록된 개체가 Azure 및 Azure Government에서 배포할 수 있는 작업은 무엇인가요?**

NERC [CIP 표준](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf) 및 [용어 사전](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf)에서 설명하듯이 BES 사이버 자산은 BES의 실시간 모니터링 또는 컨트롤 기능을 수행하고 장애가 발생하는 경우 15분 내에 BES의 안정적 운영에 영향을 줍니다. 클라우드 컴퓨팅에서 BES 사이버 자산과 보호 되는 사이버 자산을 제대로 활용하려면 NERC CIP 표준에 있는 기존의 정의를 [수정할 필요가 있습니다](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx). 그러나 CIP의 중요한 데이터를 처리하는 작업 부하가 많고 이들은 BES 사이버 시스템 정보(BCSI)의 광범위한 범주를 포함하여 15분 규칙의 적용을 받지 않습니다.

NERC ERO Enterprise는 지정된 BCSI 저장소 위치로의 액세스와 등록된 개체가 구현한 모든 컨트롤을 승인하는 등록된 개체의 프로세스를 평가 시 ERO Enterprise CMEP 직원에 지침을 제공하기 위해 규정 준수 모니터링 및 적용 프로그램(CMEP) [연습 가이드](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf)를 [발행했습니다](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx). 추가로 NERC는 Azure 컨트롤 구현의 세부 정보와 NERC CIP-004-6 및 BCSI에 적용되는 CIP-011-2 표준과 관련된 FedRAMP 감사 증거를 검토하였습니다. 등록된 개체의 데이터 암호화를 확인하기 위한 ERO에서 발행한 연습 가이드와 검토된 FedRAMP 컨트롤에 기반하여 등록된 개체가 BCSI 및 관련 작업을 클라우드에 배포하는데 추가적 지침이나 설명은 필요하지 않습니다. 그러나 등록된 개체는 고유의 사실와 상황에 따라 NERC CIP 표준의 준수에 대해 최종적으로 책임이 있습니다.

## <a name="resources"></a>리소스

- [NERC 규정 준수 가이드](https://www.nerc.com/pa/comp/guidance/)
- [NERC 규정 준수 및 적용](https://www.nerc.com/pa/comp/Pages/default.aspx)
- [NERC 조직 및 인증](https://www.nerc.com/pa/comp/Pages/Registration.aspx)
- [Microsoft 및 FedRAMP](offering-fedramp.md)
- Microsoft 및 CSA STAR [증명](offering-csa-star-attestation.md) 및 [인증](offering-csa-star-certification.md)
- [Microsoft 및 SOC 2 보고서](offering-soc.md)
- [Microsoft 보안 센터에 대한 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)
