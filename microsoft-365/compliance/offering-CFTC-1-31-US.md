---
title: 필수품 퓨처 거래 위원회 (CFTC) Rule 1.31 (c 차원) 미국
description: 독립적인 평가 회사에서는 Azure 및 Office 365이 재무 기업이 CFTC Rule 1.31 레코드 보존 및 불변의 저장소 요구 사항을 충족 하도록 도울 수 있음을 확인 했습니다.
keywords: Microsoft 365, 규정 준수, 제공
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 72b5f8301dd32ed9188f52153498853720d883c1
ms.sourcegitcommit: 4612c270867c148818eaa4008f45ca793f5d2a2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2019
ms.locfileid: "38690807"
---
# <a name="compliance-offering-commodity-futures-trading-commission-cftc-rule-131c-d-united-states"></a>규정 준수 제공: 필수품 퓨처 거래 위원회 (CFTC) Rule 1.31 (c-d) 미국

## <a name="about-cftc-rule-13c-d"></a>About CFTC Rule 1.3 (c-d)

[상품 퓨처 거래 위원회](https://www.cftc.gov/) (CFTC)는 독립 미국 연방 에이전시 이며, 필수품 퓨처 및 옵션 시장의 최근 및 이전 교체 시장을 규정 합니다.  
  
장기간 CFTC 규칙 1.31은 SEC 규칙 17a-4 (f)로 설정 된 레코드 보존 요구 사항을 정의 합니다. 또한 전자 레코드가 5 년 동안 유지 관리 되어야 하 고, 처음 2 년 동안 원본에 "쉽게 액세스할 수" 있고, 전체 작업 중에 위원회 또는 미국 지정 부서에서 검사 가능 하도록 지정 합니다. 보존 기간  
  
2017에서 CFTC는 해당 [규칙](https://www.cftc.gov/sites/default/files/idc/groups/public/@lrfederalregister/documents/file/2017-11014a.pdf)을 수정 하 고 해당 레코드를 유지 관리 하는 방법을 보다 유연 하 게 제공 하는 원칙 기반 표준을 채택 하 고 있습니다. 이를 통해 규칙을 강화 하 여 규정 된 엔터티가 비즈니스에 가장 적합 한 기술을 선택할 수 있으며 "레코드를 유지 관리 프로세스의 안정성을 보장 합니다." 수정 된 규칙은 조직에서 2 년 동안 원본 레코드를 유지 관리 하는 요구 사항을 제거 하지만, CFTC 및 초에 따라 기업에 대 한 harmonizes 사례에 해당 하는 5 년의 유지 관리 기간을 유지 합니다.

## <a name="microsoft-and-cftc-rule-131c-d"></a>Microsoft 및 CFTC Rule 1.31 (c 차원)

전 세계에서 가장 높은 규제 업계 중 하나를 대표 하는 금융 서비스 고객은 재무 트랜잭션과 관련 된 erasable 및 수정 불가능 한 상태와 같은 복잡 한 규정을 준수 해야 합니다. 대부분의 규정 중에는 전자 저장소 미디어에 있는 서적 및 기록을 보존 하도록 선택한 규정 된 엔터티에 대 한 엄격한 요구 사항을 stipulates 하는 미국 CFTC (퓨처 거래 위원회)의 규칙 1.31입니다. 저장 된 레코드는 지정 된 보존 기간 후에만 변경 하거나 삭제할 수 있는 변조 가능한 증거 여야 합니다. Microsoft Azure 불변 Blob Storage with Policy Lock 및 Microsoft Office 365 with 보존이 Lock을 사용 하는 경우 금융 기관이 CFTC Rule 1.31 (c-d)의 저장소 요구 사항을 충족 하는 데 도움이 될 수 있습니다.

### <a name="microsoft-azure"></a>Microsoft Azure

CFTC Rule 1.31 (c 차원)을 사용 하 여 Azure 준수를 평가 하기 위해 Microsoft는 레코드 관리 및 정보 거 버 넌 스를 전문적으로 담당 하는 독립 평가 회사를 보유 하 고 있습니다. 결과 보고서에서 [CFTC 1.31 (c) – (d) 준수 평가: Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports), 정책 잠금 옵션을 사용 하 여 [Azure 불변 blob 저장소](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) 를 erasable 및 비 다시 쓰기가 가능 하지 않은 (웜) 형식으로 유지 하는 데 사용 하는 경우 CFTC 규칙의 원칙 기반 요구 사항을 충족 하는지 확인 합니다. 필요한 보존 기간이 만료 되 고 연결 된 법적 보유가 출시 될 때까지 각 Blob (레코드)은 수정 하거나 덮어쓰거나 삭제 되지 않도록 보호 됩니다. 이제 중요 한 작업을 포함 하는 소프트웨어 공급자와 파트너가 Azure 불변의 Blob 저장소를 레코드 보존을 위한 단일 stop 샵 클라우드 솔루션으로 사용할 수 있습니다. 이제 금융 기관은 나머지 규격에 따라 이러한 기능을 활용 하 여 자체 응용 프로그램을 작성할 수 있습니다.

### <a name="microsoft-office-365"></a>Microsoft Office 365

CFTC Rule 1.31 (c 차원)을 사용 하 여 Office 365 준수를 평가 하기 위해 Microsoft는 규정 관련 문제를 전문적으로 담당 하는 Covington & Burling, LLP와 함께 하는 주요을 담당 합니다. 결과 보고서에서 보관 되는 [Microsoft office 365, 데이터 보존 및 규칙 17a-4 준수 규정](https://go.microsoft.com/fwlink/?linkid=830440)에서는 Covington가 [보존 잠금 기능이 있는 Office 365](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy) 에 데이터를 저장 하는 데 사용할 수 있는 보관 기능을 포함 하 고 있습니다.

Office 365의 보관 기능은 전자 메일, 음성 메일, 공유 문서, 인스턴트 메시지 및 타사 데이터를 포함 하는 광범위 한 데이터를 보존 하는 데 도움이 됩니다. 특히, Office 365의 보관을 통해 고객은 정의 된 기간에 대 한 데이터를 저장 하 고, erasable이 아닌 다른 형식으로 저장할 수 있도록 전역 또는 세분화 메시징 보존 정책을 설정 합니다.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

- [Azure](https://aka.ms/AzureCompliance)
- [Office 365](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a>감사, 보고서 및 인증서

[Azure & CFTC Rule 1.31-CFTC 1.31 (c 차원) 준수 평가 (Azure Storage의 1-& 4)

[Office 365 & CFTC Rule 1.31-Office 365, 데이터 보존 및 SEC 규칙 17a-4 준수

## <a name="how-to-implement"></a>구현 방법

- [금융 서비스 규정](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides): 클라우드 컴퓨팅 및 Microsoft online 서비스에 대 한 주요 US 규정 원칙을 준수 합니다.
- [위험 요소 분석 & 준수 가이드](https://aka.ms/RiskGovernanceGuide): Microsoft 클라우드 서비스의 위험 요소를 평가 하는 거 버 넌 스 모델을 만들고, 조정기 알림을 만듭니다.
- [재무 사용 사례](https://docs.microsoft.com/azure/industry/financial/): 사례 개요, 자습서 및 기타 리소스를 사용 하 여 금융 서비스용 Azure 솔루션을 작성 합니다.

## <a name="resources"></a>리소스

- [Microsoft 금융 서비스 준수 프로그램](https://aka.ms/FSCP-Print)
- [Microsoft business cloud services 및 금융 서비스](https://www.microsoft.com/trustcenter/cloudservices/financialservices)
- [Azure의 금융 서비스 준수](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 금융 서비스 클라우드 위험 평가 도구](https://aka.ms/FFIEC-CSDT)
- [Microsoft Office 365 보존 정책](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 금융 서비스 블로그](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft 보안 센터 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>제공 backgrounder 다운로드

이 제품에 대 한 backgrounder 문서가 필요 한가요? [PDF](https://download.microsoft.com/download/9/A/9/9A9847FE-164A-4321-8112-50719D9EA877/CFTC1.31-Compliance.pdf)를 다운로드 합니다.
