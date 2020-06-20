---
title: 금융 업계의 FINRA (규정 기관) Rule 4511 (c) 미국
description: 독립적인 평가 회사에서는 Azure 및 Office 365에서 재무 기업이 FINRA 규칙 4511 레코드 보존 및 불변의 저장소 요구 사항을 충족 하도록 도울 수 있음을 확인 했습니다.
keywords: Microsoft 365, 규정 준수, 제안
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
ms.openlocfilehash: af2e5986530ae6b1eb558ed3389f0927d5f912e9
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773759"
---
# <a name="financial-industry-regulatory-authority-finra-rule-4511c-united-states"></a>금융 업계의 FINRA (규정 기관) Rule 4511 (c) 미국

## <a name="about-finra-rule-4511"></a>정보-FINRA 규칙 4511

[금융 업계 규정 기관 (FINRA)](https://www.finra.org/#/) 은 미국에서 4500 개 이상의 brokerage 기업에 대 한 감독을 갖는 가장 큰 독립 바디 규정 증권 기업입니다. Congress "이 (가) 투자자를 보호 하기 위해 US를 사용 하 여 honestly를 운영 하 고 있는지 확인 합니다."

2011에서 US 보안 및 Exchange 위원회 (초)는 전자 저장소 미디어에 있는 서적 및 레코드 보존을 제어 하는 초 규칙 채택을 승인 했습니다. [Finra Rule 4511 (c)](https://www.finra.org/sites/default/files/NoticeDocument/p123548.pdf) "" (증권 Exchange Act) 규칙 17a-4 "를 준수 하는 형식 및 미디어에는 finra 규칙에 따라 수행 해야 하는 모든 서적 및 레코드가 보존 되도록 지정 합니다.

또한 FINRA Rule 4511 (c)를 사용 하려면 해당 하는 FINRA 또는 바다 규칙에 보존 기간이 지정 되어 있지 않은 해당 서적 및 레코드에 대해 6 년 이상의 기간 동안 보존 해야 합니다. 실제로 책과 레코드가 거래처와 관련 된 경우 보존 기간은 계정 마감 후 6 년 후에 야 합니다. 그렇지 않으면 보존 기간은 해당 책과 레코드가 만들어진 후 6 년이 됩니다.

## <a name="microsoft-and-finra-rule-4511c"></a>Microsoft 및 FINRA Rule 4511 (c)

전 세계에서 가장 높은 규제 업계 중 하나를 대표 하는 금융 서비스 고객은 재무 트랜잭션과 관련 된 erasable 및 수정 불가능 한 상태와 같은 복잡 한 규정을 준수 해야 합니다. 여기에서 stipulates는 전자 저장소 미디어에 있는 서적 및 기록을 보존 하도록 선택한 규정 된 엔터티에 대 한 엄격한 요구 사항을 충족 하는 FINRA (금융 업계 규정 기관)의 규칙 4511입니다. 저장 된 레코드는 지정 된 보존 기간 후에만 변경 하거나 삭제할 수 있는 변조 가능한 증거 여야 합니다.

Microsoft Azure 불변 Blob Storage with Policy Lock 및 Microsoft Office 365 with 보존이 Lock을 사용 하는 경우 금융 기관이 4511 (c)의 불변의 저장소 요구 사항을 충족 하는 데 도움이 될 수 있습니다.

## <a name="microsoft-azure"></a>Microsoft Azure

FINRA Rule 4511 (c)를 사용한 Azure 준수를 평가 하기 위해 Microsoft는 레코드 관리 및 정보 거 버 넌 스에 대 한 전문적인 평가 회사를 담당 합니다. 결과 보고서, [sec 17a-4 (f) & CFTC 1.31 (c-d) 준수 평가: Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports), Azure 규정 준수 규칙 4511 (c)를 포함 하 여 초당 1 초 규칙 17a-4 (f)에 해당 하는 형식 및 미디어 요구 사항에 따라 결정 됩니다.

Cohasset는 정책 잠금 옵션을 사용 하 여 [Azure 불변 Blob 저장소](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) 를 사용 하는 경우 시간 기반 blob을 erasable 및 비 다시 쓰기가 가능한 (웜) 형식으로 유지 하는 데 사용할 때 관련 하 여 적절 한 finra 저장소 요구 사항을 충족 하는지 확인 했습니다. 필요한 보존 기간이 만료 되 고 연결 된 법적 보유가 출시 될 때까지 각 Blob (레코드)은 수정 하거나 덮어쓰거나 삭제 되지 않도록 보호 됩니다.

이제 중요 한 작업을 포함 하는 소프트웨어 공급자와 파트너가 Azure 불변의 Blob 저장소를 레코드 보존 및 불변 저장을 위한 단일 stop 샵 클라우드 솔루션으로 사용할 수 있습니다. 이제 금융 기관은 나머지 규격에 따라 이러한 기능을 활용 하 여 자체 응용 프로그램을 작성할 수 있습니다.

## <a name="microsoft-office-365"></a>Microsoft Office 365

FINRA Rule 4511 (c)를 사용 하 여 Office 365 준수를 평가 하기 위해 Microsoft는 규정 관련 문제를 전문적으로 Covington & Burling, LLP로 유지 하는 주요 독립적 법칙을 보유 하 고 있습니다. 결과 보고서에서 보관 되는 Microsoft Office 365, 데이터 보존 및 규칙 17a-4 준수 규정에 따라, [365](retention-policies.md) Covington에 게는 브로커를 포함 한 규제 된 고객이 레코드 보존 요구 사항을 준수 하는 데 도움이 되는 정보를 저장할 수 있도록 하는 보관 기능이 포함 되어 있습니다.

Office 365의 보관 기능은 전자 메일, 음성 메일, 공유 문서, 인스턴트 메시지 및 타사 데이터를 포함 하는 광범위 한 데이터를 보존 하는 데 도움이 됩니다. 특히, Office 365의 보관을 통해 고객은 정의 된 기간에 대 한 데이터를 저장 하 고, erasable이 아닌 다른 형식으로 저장할 수 있도록 전역 또는 세분화 메시징 보존 정책을 설정 합니다.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>감사, 보고서 및 인증서

### <a name="azure--finra-rule-4511c"></a>Azure & FINRA Rule 4511 (c)

[초 17a-4 (f) & CFTC 1.31 (c-d) 준수 평가 Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--finra-rule-4511c"></a>Office 365 & FINRA Rule 4511 (c)

[Office 365, 데이터 보존 및 SEC 규칙 17a-4 준수에 대 한 보관](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)

## <a name="how-to-implement"></a>구현 방법

- **금융 서비스 규정**: 클라우드 컴퓨팅 및 Microsoft online 서비스에 대 한 주요 US 규정 원칙을 준수 합니다. [자세한 정보](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- **위험 평가 및 준수 가이드**: Microsoft 클라우드 서비스의 위험 평가와 규제 기관 공지에 대한 거버넌스 모델을 만들 수 있습니다. [자세한 정보](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- **금융 유스케이스**: 금융 서비스용 Azure 솔루션을 구축하기 위한 유스케이스 개요, 자습서 및 기타 리소스.. [자세한 정보](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>리소스

- [Microsoft 금융 서비스 준수 프로그램](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [Microsoft 비즈니스 클라우드 서비스 및 금융 서비스](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Azure에서의 금융 서비스 규정 준수](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 금융 서비스 클라우드 위험 평가 도구](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Microsoft Office 365 보존 정책](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 금융 서비스 블로그](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft 보안 센터에 대한 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)
