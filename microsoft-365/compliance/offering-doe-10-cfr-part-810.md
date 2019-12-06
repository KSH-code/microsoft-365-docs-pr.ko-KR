---
title: US DoE 10 CFR 부분 810
description: 고객은 Azure 정부를 사용할 수 있는 US DoE 10 CFR 파트 810의 수출 관리 요구 사항을 따릅니다.
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
ms.openlocfilehash: fe87cde60847a0f5d935b50f433cd9b95702bebf
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859408"
---
# <a name="us-doe-10-cfr-part-810"></a>US DoE 10 CFR 부분 810

## <a name="microsoft-and-doe-10-cfr-part-810"></a>Microsoft 및 DoE 10 CFR 부분 810

Microsoft Azure 정부에서는 고객을 지원 하 여 귀하의 미국 에너지 (홍길동) 10 CFR 부분 810, 두 가지 인증을 통해 다음과 같은 수출 관리 요구 사항에 따라 도움을 받을 수 있습니다.

- JAB (공동 인증 위원회)에서 실행 되는 FedRAMP High Provisional 권한 부여 (P-ATO)
- 수준 4 및 5 Provisional (DoD) 방어 정보 시스템 에이전시의 권한 부여

FedRAMP에서는 Azure 정부에서 엄격한 NIST 컨트롤로 설계 된 계산, 저장소 및 네트워킹 같은 서비스를 핵심 인프라 및 가상화 기술과 제공 하는 것을 보장 하는 적절 한 기준을 제공 합니다. 이러한 도움말은 고객 데이터 분리 요구 사항을 충족 하 고 고객의 온-프레미스 환경에 대 한 보안 연결을 설정 하는 데 도움이 됩니다.

또한 Azure 정부는 Azure 클라우드와 물리적으로 분리 된 미국 정부 커뮤니티 클라우드입니다. Azure 운영 직원 중에 정보 및 시스템에 대 한 액세스를 차단 하는 특정 제어 기능을 포함 하 여 US 정부의 특정 백그라운드 차단 요구 사항에 대 한 추가 보증을 제공 합니다.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

- [Azure 정부](https://aka.ms/AzureCompliance)
- Intune

## <a name="how-to-implement"></a>구현 방법

- 클라우드 컴퓨팅에 대 한 자세한 [c CIP 표준 &](https://aka.ms/AzureNERC): 전기 유틸리티 및 등록 된 엔터티에 대 한 지침 Azure 또는 azure 정부에 작업을 배포 합니다.

## <a name="about-doe-10-cfr-part-810"></a>DoE 10 CFR Part 810

미국 에너지 (DoE) 수출 통제 규정 [10 CFR 부분 810](https://www.govinfo.gov/content/pkg/FR-2015-02-23/pdf/2015-03479.pdf) 에서는 분류 되지 않은 핵 기술 및 지원의 수출을 제어 합니다. 이를 통해 미국에서 내보내진 핵 기술이 peaceful 목적 으로만 사용 되도록 할 수 있습니다. 수정 된 부분 810 (Final Rule)은 3 월 2015에 적용 되 고 [국내 핵 보안 관리](https://www.energy.gov/nnsa/national-nuclear-security-administration)에 의해 관리 됩니다. 810.6 섹션에서는 특정 권한 부여를 요구 하는 모든 지원 및 중요 한 기밀 기술 (예: 지원에 대 한 제공)을 제공 하기 위해 특정 DoE 권한 부여가 필요 하다는 것을 설명 합니다. 향상 및 중형 온수와 같은 중요 한 핵 기술이 포함 되어 있습니다.

## <a name="frequently-asked-questions"></a>자주하는 질문

**미국 핵 규제 위원회에 대 한 10 CFR 부분 110 규정은 Azure 정부에 적용 됩니까?**

아니요. [미국 핵 규제 위원회](https://www.nrc.gov/) (nrc)는 [CFR 부분 110](https://www.nrc.gov/reading-rm/doc-collections/cfr/part110/)에서 핵 설비 및 관련 장비 및 자료의 [수출 및 가져오기를](https://www.nrc.gov/about-nrc/ip/export-import.html) 조절 합니다. NRC는 DoE에 속하는 이러한 항목과 관련 된 이러한 항목에 대 한 핵 기술 및 지원을 규제 하지 않습니다. 따라서 NRC 10 CFR Part 110 규정은 Azure 정부에 적용 되지 않습니다.

**DoE 10 CFR Part 810을 준수 하 고 있는 증거를 제공 하려면 어떻게 해야 하나요?**

조직에서 Azure 정부에 데이터를 배포 하는 경우 적절 한 제한 된 방식으로 데이터를 처리 하는 증거로 Azure 정부 FedRAMP High P ATO을 사용 하도록 설정할 수 있습니다. 그러나 클라우드 서비스 사용을 비롯 하 여 사용자의 시스템에 대 한 DoE 권한 부여를 담당 해야 합니다.

**Azure 정부에 배포 된 데이터를 분류 하기 위한 책임은 무엇 인가요?**

Azure 정부에 데이터를 배포 하는 고객은 자체 보안 분류 프로세스를 담당 합니다. DoE export 컨트롤을 대상으로 하는 고객 데이터의 경우, 분류 시스템은 [미국 원자성 에너지 Act](https://www.epa.gov/laws-regulations/summary-atomic-energy-act)의 148 섹션으로 설정 된 분류 되지 않은 제어 되는 컨트롤에 따라 확장 됩니다.

## <a name="resources"></a>리소스

- [Azure 클라우드 서비스 및 US 수출 컨트롤](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- [Microsoft 및 FedRAMP](offering-fedramp.md)
- [Microsoft 및 DoD](offering-dod-disa-l2-l4-l5.md)
- [Microsoft Government 클라우드](https://www.microsoft.com/enterprise/government)
- [Microsoft 보안 센터에 대한 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>제공 사항의 배경 설명 다운로드

이 제공 사항에 대한 배경 설명 문서가 필요한가요? [PDF](https://download.microsoft.com/download/A/E/3/AE309D0E-F8D5-42C9-9B36-86FF51464AFC/DOE_10CFR_Part810-Compliance.pdf)를 다운로드합니다.
