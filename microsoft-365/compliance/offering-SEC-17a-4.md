---
title: 증권 및 Exchange 위원회 (SEC) 규칙 17a-4 (미국)
description: 독립적인 평가 기업에서는 Azure 및 Office 365에서 재무 기업이 초 규칙 17a-4 (f) 레코드 보존 및 불변의 저장소 요구 사항을 충족 하도록 도울 수 있음을 확인 했습니다.
keywords: Microsoft 365, 규정 준수, 제품
localization_priority: None
ms.prod: Microsoft-365-enterprise
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
ms.openlocfilehash: 5bbc8e8e39e28a020864d705489d704acd0c012b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602065"
---
# <a name="securities-and-exchange-commission-sec-rule-17a-4f-united-states"></a>증권 및 Exchange 위원회 (SEC) 규칙 17a-4 (미국)

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft 및 SEC 규칙 17a-4 (f)

[Us 증권 및 Exchange 위원회 (초)](https://www.sec.gov/) 는 미국 연방 정부의 독립 에이전시와 미국 증권의 주요 감독 및 조절기입니다. It는 연방 유가 증권 법을 통해 집행 기관을 wields 하 고, 새 유가 증권 규칙을 제안 하며, 유가 증권 업계 시장 규정을 oversees 합니다.

초는 전자 저장소 미디어에 있는 서적과 레코드를 보존 하도록 선택한 규정 된 엔터티에 대 한 엄격한 및 명시적 요구 사항을 정의 합니다. [CFR 240.17 a-3](https://www.govinfo.gov/app/details/CFR-2012-title17-vol3/CFR-2012-title17-vol3-sec240-17a-3) 및 [17 CFR 240.17 a-4](https://www.ecfr.gov/cgi-bin/text-idx?mc=true&node=pt17.4.240&rgn=div5#se17.4.240_117a_64) 를 설정 하 여 보존 기간을 포함 하 여 유가 증권 대리점에 대 한 recordkeeping를 규제 합니다. 나중에, 1 초는 17 CFR 240.17 a-4 단락 (f)을 [수정](https://www.sec.gov/rules/interp/34-47806.htm) 했으며, 이러한 경우에는 특정 조건이 충족 되 면 전자 저장소 미디어에서 책 및 레코드를 보존 하기 위한 두 개의 interpretive 릴리스가 명시적으로 사용 됩니다.

필요한 보존 기간 동안 레코드를 변경 하거나 지울 수 없는 경우에는 전자 저장소 시스템이 이러한 조건을 충족 합니다. 보존 기간은 레코드 종류를 기준으로 3 ~ 6 년 동안, 처음 2 년 동안 즉각적인 접근성이 적용 됩니다. 또한 interpretive 릴리스 중 하나를 사용 하려면 저장소 시스템이 구성 된 보존 기간을 초과 하는 레코드를 유지 하 여 subpoenas, 법률 보존 또는 기타 요구 사항을 준수 해야 합니다.

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft 및 SEC 규칙 17a-4 (f)

전 세계에서 가장 높은 규제 업계 중 하나를 대표 하는 금융 서비스 고객은 재무 트랜잭션과 관련 된 erasable 및 수정 불가능 한 상태와 같은 복잡 한 규정을 준수 해야 합니다. 대부분의 규정 중에는 전자 저장소 미디어에 있는 서적 및 기록을 보존 하도록 선택한 규정 된 엔터티에 대 한 엄격한 요구 사항을 충족 하는 미국 보안 및 Exchange 위원회 (stipulates)의 Rule 17a-4 (f)가 있습니다. 저장 된 레코드는 지정 된 보존 기간 후에만 변경 하거나 삭제할 수 있는 변조 가능한 증거 여야 합니다.

Microsoft Azure 불변 Blob Storage with Policy Lock 및 Microsoft Office 365 with 보존이 Lock을 사용 하는 경우 금융 기관은 SEC 규칙 17a-4 (f)의 불변의 저장소 요구 사항을 충족 하는 데 도움이 될 수 있습니다.

SEC 규칙 17a-4 (f)를 사용 하 여 Azure 및 Office 365 준수를 평가 하기 위해 Microsoft는 레코드 관리 및 정보 거 버 넌 스를 전문적으로 담당 하는 독립 평가 회사를 보유 하 고 있습니다. 결과 보고서에서 다음을 수행 합니다.

- **Azure**: [초 17a-4 (f) 준수 평가: Microsoft azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports), With Hasset는 정책 잠금 옵션으로 시간 기반 blob을 유지 하는 데 사용 되는 경우 erasable 및 비 다시 쓰기가 가능한 (웜) 형식의 [AZURE 불변 blob 저장소](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) 에서 SEC 규칙의 변경 불가능 한 저장소 요구 사항을 충족 하는지 확인 했습니다. 필요한 보존 기간이 만료 되 고 연결 된 법적 보유가 출시 될 때까지 각 Blob (레코드)은 수정 하거나 덮어쓰거나 삭제 되지 않도록 보호 됩니다. 이제 중요 한 작업을 포함 하는 소프트웨어 공급자와 파트너가 Azure 불변의 Blob 저장소를 레코드 보존 및 불변 저장소 용 onestop 솔루션으로 사용할 수 있습니다. 이제 금융 기관은 나머지 규격에 따라 이러한 기능을 활용 하 여 자체 응용 프로그램을 작성할 수 있습니다.
- **Office 365**: [Exchange Online을 사용 하 여 초 17a-4를 준수 하](https://docs.microsoft.com/office365/securitycompliance/use-exchange-online-to-comply-with-sec-rule-17a-4)고, [보존 잠금](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy) 기능을 사용 하 여 Office 365에 데이터를 저장 하는 데 도움이 되는 정보를 제공 하는 보관 기능이 포함 되어 있는지 확인 합니다. Office 365의 보존 정책은 전자 메일, 음성 메일, 공유 문서, 인스턴트 메시지 및 타사 데이터를 비롯 한 광범위 한 데이터를 보존 하는 데 도움이 됩니다. 특히, Office 365의 보관을 통해 고객은 전체 또는 세분화 된 메시징 보존 정책을 설정 하 여, 정의 되지 않은 기간에 대 한 데이터를 저장 하지 않는 nonerasable 형식으로 저장할 수 있습니다.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>감사, 보고서 및 인증서

### <a name="azure--sec-rule-17"></a>Azure & SEC 규칙 17

[초 17a-4 (f) & CFTC 1.31 (c-d) 준수 평가 Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--sec-rule-17"></a>Office 365 & SEC 규칙 17

[SEC 17a-4 (f) 준수 평가: Exchange Online을 사용한 Microsoft 보안 & 준수 센터](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

## <a name="how-to-implement"></a>구현 방법

### <a name="financial-services-regulation"></a>금융 서비스 규정

클라우드 컴퓨팅 및 Microsoft online services에 대 한 주요 US 규정 원칙의 준수 맵입니다. [자세한 정보](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

### <a name="risk-assessment--compliance-guide"></a>위험 요소 분석 & 준수 가이드

Microsoft 클라우드 서비스에 대 한 위험 평가를 위한 거 버 넌 스 모델 및 조정기 알림을 만듭니다. [자세한 정보](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

### <a name="financial-use-cases"></a>재무 사용 사례

금융 서비스용 Azure 솔루션을 작성 하는 데 사용 사례 개요, 자습서 및 기타 리소스 [자세한 정보](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>리소스

- [Microsoft Office 365, 데이터 보존 및 규칙 17a-4의 보관](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)
- [준수 Microsoft 금융 서비스](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [준수 프로그램 Microsoft business cloud services 및 금융 서비스](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Azure에서의 금융 서비스 규정 준수](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 금융 서비스 클라우드 위험 평가 도구](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Microsoft Office 365 보존 정책](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 금융 서비스 블로그](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft 보안 센터에 대한 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>제공 사항의 배경 설명 다운로드

이 제공 사항에 대한 배경 설명 문서가 필요한가요? [PDF](https://download.microsoft.com/download/E/5/2/E52103E7-C1BB-4118-9725-4452FEA931D8/SEC17a-4(f)-Compliance.pdf)를 다운로드합니다.
