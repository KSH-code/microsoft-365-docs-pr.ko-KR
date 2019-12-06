---
title: 미국 내부 수익 서비스 게시 1075
description: Microsoft에는 미국 내부 수익 서비스 게시 1075의 요구 사항을 충족 하는 컨트롤이 있습니다.
keywords: Microsoft 365, 규정 준수, 제품
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 30509260e83f1aaa59c57365357e18a3f12097c4
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859728"
---
# <a name="us-internal-revenue-service-publication-1075"></a>미국 내부 수익 서비스 게시 1075

## <a name="us-internal-revenue-service-publication-1075-overview"></a>미국 내부 수익 서비스 게시 1075 개요

내부 수익 서비스 게시 1075 (IRS 1075)에서는 정책, 사례 및 컨트롤을 사용 하 여 기밀을 보호할 수 있도록 US 정부 기관 및 FTI (연방 세금 정보)에 액세스 하는 에이전트에 대 한 지침을 제공 합니다. IRS 1075은 외부 정부 기관에서 보유 하 고 있는 FTI의 손실, 침해 또는 오용 위험을 최소화 하는 데 목적이 있습니다. 예를 들어 세금에 대 한 FTI를 처리 하는 주, 즉 FTI에 액세스 하는 상태 서비스 기관은 해당 정보를 보호 하기 위한 프로그램이 마련 되어 있어야 합니다.  
  
FTI을 보호 하기 위해 IRS 1075은 응용 프로그램, 플랫폼 및 데이터 센터 서비스에 대 한 보안 및 개인 정보 취급 방침을 제어 합니다. 예를 들어 FTI의 적절 한 처리와 같은 데이터 센터 활동의 보안을 우선적으로 취급 하 고, 데이터 센터 계약 자가 항목을 제한할 수 있도록 합니다. 정부 기관에서 이러한 제어를 적용 하는 FTI를 수신 하도록 하기 위해 IRS에서는 이러한 기관과 해당 계약자에 대 한 정기적인 검토가 포함 된 보호책 프로그램을 설정 했습니다.

## <a name="microsoft-and-us-internal-revenue-service-publication-1075"></a>Microsoft 및 미국 내부 수익 서비스 게시 1075

Microsoft Azure 정부 및 [Microsoft Office 365 U.S. 정부](https://products.office.com/government/office-365-web-services-for-government) 클라우드 서비스는 적절 한 컨트롤을 보유 하 고 있는 계약 약정을 제공 하 고, Microsoft 에이전시 고객이 IRS 1075의 substantive 요구 사항을 충족 하는 데 필요한 보안 기능에 대해 설명 합니다.  
  
정부에 대 한 이러한 Microsoft 클라우드 서비스는 고객이 솔루션을 작성 하 고 운영할 수 있는 플랫폼을 제공 하지만, 고객은 해당 특정 솔루션이 IRS 1075에 따라 운영 되는지 여부를 직접 확인 해야 하며, 따라서 IRS 감사에 따라 달라 집니다.  
  
정부 기관에서 규정 준수를 지원 하기 위해 Microsoft는 다음과 같은 작업을 수행 합니다.

- 기관에서 책임을 이해 하는 데 도움이 되는 자세한 지침을 제공 하 고 Azure 정부 및 Office 365 U.S. 정부의 다양 한 IRS 컨트롤의 기능에 어떻게 매핑되는지 설명 합니다. IRS 1075 보호 보안 보고서 (SSR)는 Microsoft 서비스가 해당 IRS 컨트롤을 구현 하는 방법과 Azure 정부 및 Office 365 U.S. 정부의 FedRAMP 패키지를 기반으로 하는 방법을 철저히 문서화 합니다. IRS 1075 및 FedRAMP는 모두 NIST 800-53를 기반으로 하므로 IRS 1075에 대 한 준수 경계는 FedRAMP 인증과 동일 합니다.
- IRS는 IRS 보호 문서의 릴리스를 명시적으로 승인 해야 하므로 NDA에 거주 하는 정부 고객만 SSR를 검토할 수 있습니다.
- 클라우드 서비스에 대 한 독립 평가자에서 생성 하는 사용 가능한 감사 보고서 및 모니터링 정보를 만듭니다.
- IRS Azure 정부 준수 고려 사항 및 Office 365 미국 정부 준수 고려 사항에 대해 설명 하 고,이를 통해 에이전시에서 IRS 1075을 준수 하는 방식으로 정부 서비스용 Microsoft 클라우드를 사용 하는 방법을 대략적으로 소개 합니다. NDA에 거주 하는 정부 고객은 이러한 문서를 요청할 수 있습니다.
- 고객에 게 필요한 경우 Microsoft 주제별 전문가 또는 외부 감사자와 정보를 교환할 기회를 제공 합니다.

Microsoft 클라우드에서 IRS 1075의 혜택에 대해 알아봅니다. [IRS 1075 backgrounder를 다운로드 합니다](https://aka.ms/irs1075-backgrounder) .

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

FedRAMP 인증은 NIST 지침 (낮음, 중간, 높음)에 따라 세 가지 영향 수준으로 부여 됩니다. 이러한 경우 기밀성, 무결성 또는 가용성의 손실로 인 한 영향을 조직에 미칠 수 있는 영향은 낮음 (제한적 효과), 중간 (심각한 부정적 효과), 높음 (심각 또는 치명적 효과)

- [Azure 및 Azure Government](https://azure.microsoft.com/global-infrastructure/government/)
- Dynamics 365 미국 정부
- [Office 365 및 Office 365 U.S. Government](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- Office 365 US Government Defense
- 독립 실행형 서비스 혹은 Office 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Power BI 클라우드 서비스

## <a name="audits-reports-and-certificates"></a>감사, 보고서 및 인증서

IRS 1075의 substantive 요구 사항을 준수 하는 기능은 FedRAMP 감사의 각 해에 설명 되어 있습니다.

- [FedRAMP 권한 부여](https://marketplace.fedramp.gov/#/product/azure-government?sort=productName&productNameSearch=azure)
- [Azure IRS 1075 보호 보안 보고서](https://aka.ms/AzureIRS1075SafeguardSecurityReport)

## <a name="frequently-asked-questions"></a>자주하는 질문

**Microsoft는 IRS 1075의 요구 사항을 해결 하는 방법을 설명 합니다.**

Microsoft는 보안, 개인 정보, 운영 체제 및 NIST 800-53 rev를 정기적으로 모니터링 합니다. FedRAMP 초기 계획에 필요한 4 개의 컨트롤 지속적인 모니터링 보고서를 통해이 정보에 대 한 분기별 액세스를 제공 합니다. Azure 정부 및 Office 365 미국 정부 고객은 [서비스 보안 포털](https://aka.ms/stphelp)을 통해이 중요 준수 정보에 액세스할 수 있습니다.

또한 Microsoft는 Azure 정부 및 Office 365 U.S. 정부에 대 한 마스터 컨트롤 집합에 IRS 1075 컨트롤을 포함 하 고 매년 감사 합니다.

**FedRAMP 패키지 또는 시스템 보안 계획을 검토할 수 있나요?**

예 (조직이 Azure 정부 및 Office 365 U.S. 정부에 대 한 자격 요구 사항을 충족 하는 경우) Microsoft 계정 담당자에 게 직접 문의 하 여 이러한 문서를 검토 하세요. 또한 준수 클라우드 서비스 공급자의 FedRAMP 목록을 참조할 수도 있습니다.

**Azure 또는 Office 365 공용 클라우드 환경을 사용할 수 있으 나 계속 해 서 IRS 1075을 준수 하나요?**

아니요. FTI을 저장 하 고 처리할 수 있는 유일한 환경은 Azure 정부 또는 Office 365 U.S. 정부입니다. 정부 고객은 이러한 환경을 사용 하기 위해 자격 요구 사항을 충족 해야 합니다.

## <a name="resources"></a>리소스

- [IRS 발행물 1075](https://www.irs.gov/pub/irs-pdf/p1075.pdf)
- [IRS 보호책 프로그램](https://www.irs.gov/uac/Safeguards-Program)
- [Microsoft 공통 컨트롤 허브 규정 준수 프레임 워크](https://www.microsoft.com/trust-center/compliance/compliance-overview)
- [Microsoft Cloud for Government](https://enterprise.microsoft.com/industries/government/start-your-microsoft-cloud-for-government-trial-today)
- [Microsoft 보안 센터에 대한 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>제공 사항의 배경 설명 다운로드

이 제공 사항에 대한 배경 설명 문서가 필요한가요? [PDF](https://download.microsoft.com/download/D/1/8/D1825AE2-4FDA-4A4B-8D4F-9B7D2976D54A/IRS1075_Compliance_Backgrounder.pdf)를 다운로드합니다.
