---
title: PCI(Payment Card Industry) DSS(Data Security Standard)
description: Azure, SharePoint Online 및 비즈니스용 OneDrive는 Payment Card Industry Data Security 표준 수준 1 버전 3.2를 준수합니다.
keywords: Microsoft 365, 규정 준수, 제안
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: cb4d1a4c4632763506fd2d3b05431acb9233f744
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071973"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a>PCI(Payment Card Industry) DSS(Data Security Standard)

## <a name="pci-dss-overview"></a>PCI DSS 개요

지급 카드 산업(PCI) 데이터 보안 표준(DSS)는 신용 카드 데이터 통제 수준을 높여 사기를 방지하도록 디자인 된 글로벌 정보 보안 표준입니다. 만약 5대 대형 신용 카드사- 미자, 마스터카드, 아메리칸 익스프레스, 디스커버 및 JCB의 신용 카드 지급을 승인하려면 모든 조직은 크기에 상관 없이 PCI DSS 표준을 따라야 합니다. 지급 및 카드 소유주 데이터를 저장, 처리 혹은 전달 하는 모든 조직은 PCI DSS를 준수해야 합니다.

## <a name="microsoft-and-pci-dss"></a>Microsoft와 PCI DSS

Microsoft는 적격 품질 검사자(QSA)의 승인을 사용하여 연간 PCI DSS 평가를 완료 했습니다. 감사가 인프라, 개발, 운영, 관리 지원 및 서비스 범위 확인 등을 포함하는 Microsoft Azure, 비즈니스용 Microsoft OneDrive 및 Microsoft SharePoint Online 환경을 검토하였습니다. PCI DSS는 거래 규모에 따라 4단계의 준수 수준을 지정합니다. Azure, 비즈니스용 OneDrive 및 SharePoint Online은 서비스 제공자 레벨 1(최대 거래 규모 - 연간 6백만건 이상)에서 PCI DSS 버전 3.2 준수 인증을 받았습니다.

평가 결과는 고객에게 제공되고 QSA가 의해 준수 보고서(RoC)를 발행하는 규정 준수 증명서(AoC)로 제공됩니다. 준수 결과는 감사를 통과하고 검사자로부터 AoC를 발급받고 AoC에 서명되어 있는 날짜로부터 1년 동안 유효합니다. 

카드 데이터 전용 네트워크(CDE) 또는 카드 처리 서비스를 개발하려는 고객은 많은 기본적인 부분에서 이러한 검증을 사용할 수 있습니다. 이를 통해 자체적으로 PCI DSS 인증을 얻기 위한 관련된 작업과 비용을 줄일 수 있습니다.

Azure, 비즈니스용 OneDrive 및 SharePoint Online는 이 플랫폼을 사용하는 사용자가 빌드 혹은 호스트 하는 서비스를 PCI DSS 인증서로 자동으로 번역 하지 않기 때문에 PCI DSS 준수 상태를 이해하는 것은 중요합니다. 사용자는 PCI DSS 요구 사항을 준수 할 책임이 있습니다.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

- [Azure 및 Azure Government](https://azure.microsoft.com/global-infrastructure/government/)
- Microsoft Cloud App Security
- 독립 실행형 서비스 혹은 Office 365 혹은 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Flow 클라우드 서비스
- Microsoft Graph
- Intune
- [엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- 독립 실행형 서비스 혹은 Office 365 또는 Dynamics 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 PowerApps 클라우드 서비스
- 독립 실행형 서비스 혹은 Office 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Power BI 클라우드 서비스
- 비즈니스용 OneDrive 및 SharePoint Online(미국에만 해당)

## <a name="audit-reports-and-certificates"></a>감사, 보고서 및 인증서

- [Azure PCI DSS 준수 증명(AoC)](https://aka.ms/azure-pci)
- [비즈니스용 OneDrive 및 SharePoint Online PCI DSS 준수 증명(AoC)](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a>Azure에서 실행되는 PCI DSS 솔루션 받기

Azure 보안 및 PCI DSS 준수 청사진으로 PCI DSS 솔루션을 클라우드에서 더 빠르게 빌드하고 배포해보세요. 참고 아키텍처, 배포 지침, 수행 매핑 통제, 자동 스크립트 등을 얻어보세요. [Azure PCI DSS 청사진을 사용하여 시작하기](https://aka.ms/pciblueprint).

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**AoC(Attestation on Compliance) 표지 페이지에 ‘2018년 6월’이 표시된 이유는 무엇인가요?**

커버 페이지의 2018년 6월 날짜는 AoC 서식 파일이 게시된 날짜입니다. 평가 날짜는 섹션 2를 참조하세요.

**Azure 규정 준수 증명서가 여러 개인 이유는 무엇인가요?**

Azure AoC 패키지에는 Azure 공개, 독일, 정부 클라우드에 해당하는 AoC가 있습니다. 고객은 Azure 환경에 해당하는 AoC를 사용해야 합니다.  

**PA DSS와 PCI DSS는 서로 어떤 관계인가요?**

지급 응용 프로그램 데이터 보안 표준(PA DSS)는 PCI DSS를 준수하고 비자의 지급 응용 프로그램 모범 사례를 대체하며 다른 주 카드 발행자에 대한 준수 요구 사항을 통합하는 일련의 요구 사합니다. PA DSS는 소프트웨어 공급자가 타드 인증 혹은 정산 절차의 일환으로 카드 소유자 및 지급 데이터를 저장, 처리 혹은 전달 하는 제3자 응용 프로그램 개발을 할 수 있도록 도와줍니다. 소매 업체는 효율적은 PCI DSS 준수를 위하여 PA DSS 인증 응용 프로그램을 사용해야 합니다. PA DSS는 Azure에는 적용되지 않습니다.

**전표 매입 업체란 무엇인가요? Azure는 매입업체를 이용하나요?**

전표 매입 업체 카드 지급 거래를 수행하는 은행 혹은 다른 주체입니다. Azure는 지급 카드 처리를 서비스로 제공하지 않기 때문에 전표 매입 업체를 사용하지 않습니다.

**PCI DSS는 어떤 회사 및 판매자에게 적용되나요?**

PCI DSS는 회사의 규모 혹은 카드 소유자 데이터를 승인, 전달 혹은 저장 하는 수에 상관 없이 모든 회사에 적용됩니다. 어떤 고객이 신용카드나 직불 카드를 사용하여 회사에 결제를 하면 PCI DSS 요구사항이 적용된다는 의미입니다. 총 12개월간의 회사의 총 거래 규모에 기반하여 4단계 중 한 단계가 적용됩니다. 레벨 1은 1년에 총 6백만건 이상의 거래를 하는 회사를 의미하고, 레벨 2는 1백만건 이상 6백만건 이하의 거래, 레벨 3은 2만이상 1백만건 이상의 거래, 레벨 4는 2만건 미만의 거래를 의미합니다.

**Azure에 배포된 솔루션에 대한 우리 회사의 PCI DSS 규정 준수 활동은 어느 것부터 시작해야 하나요?**

PCI 보안 표준 위원회는 특정 준수 요구사항을 알기 위한 좋은 정보를 제공합니다. 위원회는 상인과 다른 지불 카드 처리 관련자들을 위하여 [PCI DSS 빠른 참고 가이드](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)를 발간합니다. 이 가이드는 PCI DSS가 지불 카드 거래 환경을 보호하는 방법과 이를 적용하는 방법에 대해 설명합니다.

준수에는 Azure에서 호스트 하지 않는 시스템을 평가하고 처리하는 것을 포함하여 다양한 요소가 적용됩니다. 어떤 Azure 서비스를 사용하는지에 따라 그리고 솔루션내에서 사용되는 방식에 따라 요구 사항이 상이합니다.

**비즈니스용 OneDrive 및 SharePoint Online가 미국 이외의 지역에서 PCI DSS를 준수할 계획이 있나요?**

현재 비즈니스용 OneDrive 및 SharePoint Online은 미국에서만 PCI DSS 준수 대상입니다. Microsoft는 미국 외 지역에 요구되는 사항과 요구 시기를 평가하고 다른 지역이 로드맵에 추가된다면 그 때 업데이트를 제공할 예정입니다.

**무엇이 비즈니스용 OneDrive 및 SharePoint Online 범위 내에 있나요?**

현재 비즈니스용 OneDrive 및 SharePoint Online에 업로드된 파일과 문서만 PCI DSS를 준수합니다.

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>Microsoft 준수 관리자를 사용하여 위험 평가

[Microsoft 준수 관리자](compliance-manager.md)는 사용자 조직의 준수 상태를 이해하고 위험을 줄이기 위한 활동에 도움을 주는 [Microsoft 365 규정 준수 센터](microsoft-365-compliance-center.md)의 기능입니다. 준수 관리자는 이 규정에 관한 평가를 작성하기 위한 프리미엄 문서 서식을 제공합니다. 준수 관리자의 **평가 문서 서식 페이지** 에서 문서 서식을 찾을 수 있습니다. [준수 관리자에서 평가를 빌드](compliance-manager-assessments.md)하는 방법에 대해 알아봅니다.

## <a name="resources"></a>리소스

- [PCI 보안 표준 심의회(영문)](https://www.pcisecuritystandards.org/)
- [PCI 데이터 보안 표준(영문)](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [Azure PCI DSS 3.2.1 청사진](https://docs.microsoft.com/azure/governance/blueprints/samples/pci-dss-3.2.1/)
- [PCI DSS 빠른 참조 설명서(영문)](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [Microsoft 보안 센터에 대한 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)
