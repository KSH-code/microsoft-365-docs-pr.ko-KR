---
title: 임상, 실험실 및 제조 모범 사례 (GxP)
description: Azure 및 Office 365는 생명과학 조직이 GxP 규정 요구 사항을 충족하도록 도울 수 있습니다.
keywords: Microsoft 365, 규정 준수, 제안
localization_priority: Priority
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
ms.openlocfilehash: 7a130275588b765514162cd08e37d9d5e512a409
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44066163"
---
# <a name="good-clinical-laboratory-and-manufacturing-practices-gxp"></a>임상, 실험실 및 제조 모범 사례 (GxP)

## <a name="about-gxp"></a>GxP 정보

*GxP*라는 용어는 '모범 사례' 지침 및 규정의 일반적인 약어입니다. 'x'는 임상(GCP), 제조(GMP), 유통(GDP), 실험실(GLP), 농업(GAP) 등의 특정 분야를 나타냅니다. 단일 규제 기관이나 관리는 없습니다. 요구 사항은 국가마다 다르지만 각 국가마다 고유한 지침과 규제 기관이 있습니다. GxP 규정에는 [미국 FDA CFR Title 21 Part 11](https://aka.ms/FDA-CFR) 및 EU의 [EudraLex Volume 4 — GMP 지침, 부속서 11](https://ec.europa.eu/health/documents/eudralex/vol-4_en)에 요약된 규정이 포함됩니다.

규제 목표는 규제 산업에서 기업이 생산 과정에서 사용하기에 안전하고 엄격한 품질 표준을 충족하는 제품을 제조하도록 하는 것입니다. GxP 프로세스를 사용하는 컴퓨터 시스템은 GxP 요구 사항 준수 확인이 필요하며, 시스템이 이를 충족시키는 능력을 보여줄 수 있을 때 자격을 갖춘 것으로 간주됩니다.

## <a name="microsoft-and-gxp"></a>Microsoft와 GxP

Microsoft는 리서치, 임상 연구, 유지 관리, 제조 및 생명 과학 제품 및 서비스의 배포를 다루는 조직에게 규제 측면에서 임상, 실험실 및 제조 모범 사례 (GxP)의 요구 사항을 충족하도록 도울 수 있습니다. 여기에는 CFR Title 21 Part 11 하의 미국 FDA (식품의약국)에 적용되는 컴퓨터 시스템의 보안 및 전자 기록의 신뢰성에 대한 규정과 EU에서 컴퓨터 시스템에 대한 지침인 EudraLex, Volume 4, 부속서 11을 포함합니다.

클라우드 서비스 제공 업체에 대한 GxP 인증은 없습니다. 그러나

- Microsoft Azure 및 Microsoft Office 365는 ISO 9001 (QMS) 및 ISO/IEC 27001 (ISMS)을 포함하여 품질 관리 및 정보 보안에 대한 많은 독립적인 감사를 받았습니다. 여기에는 Microsoft 절차 및 기술 제어에 대한 정기 감사가 포함되며 효과가 검증되었습니다.
- Microsoft 자격 접근 방식은 또한 *자동화 제조 모범 사례* (GAMP) 시리즈의 모범 사례 가이드(ISPE(International Society for Pharmaceutical Engineering)로 부터) 및 *규제되는 GxP 환경의 컴퓨터 시스템에 대한 모범 사례*(Pharmaceutical Inspection Cooperation Scheme (PIC/S) PI 011-3로 부터)를 기반으로 합니다.

이러한 표준과 모범 사례는 GxP 규정 준수에 특별히 초점을 맞추지 않지만, 그 목적과 목표는 유사하며 Microsoft 클라우드 서비스에 저장된 데이터의 기밀성, 무결성 및 가용성을 보장하는 데 도움이됩니다.

Microsoft는 생명 과학 산업의 품질 보증 및 규제 GxP 준수를 전문으로 하는 독립 기관인 [Montrium](https://www.montrium.com/)을 유지하여 Microsoft에 대한 GxP 자격 검토를 수행했습니다. 결과적인 자격 지침 ([Azure](https://aka.ms/gxpcompliance) 및 [Office 365](https://aka.ms/o365-qualification-guideline))은 이러한 클라우드 서비스를 사용하여 GxP 규제 컴퓨터 시스템을 호스팅 및 지원하려는 생명 과학 조직을 위한 것입니다. 이 지침은 GxP 요구 사항을 충족하기 위해 Microsoft와 고객이 공유하는 책임을 식별하고, 범위 내 Microsoft 클라우드 서비스를 사용하는 고객이 GxP 컴퓨터 시스템에 대한 제어를 유지하기 위해 설정할 수 있는 활동 및 컨트롤을 권장합니다.

Azure 및 Office 365에서 GxP 솔루션을 구축하는 생명 과학 조직은 클라우드 효율성을 활용하면서 환자 안전, 제품 품질 및 데이터 무결성을 보호할 수 있습니다. 고객은 특정 수준에서 데이터 개인 정보 보호 및 무결성을 강화하는 여러 계층의 보안 및 거버넌스 기술, 운영 관행 및 규정 준수 정책의 혜택을 받습니다.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

- [Azure](https://aka.ms/AzureCompliance)
- [Office 365](https://aka.ms/o365-compliance-framework)

## <a name="how-to-implement"></a>구현 방법

- [Azure GxP 지침](https://aka.ms/gxpcompliance): GxP 모범 사례 및 규정을 준수하면서 Azure를 사용하기 위한 포괄적인 도구 집합입니다.
- [GxP 시스템과 함께 Azure 사용](https://aka.ms/GXP-Azure-Strategies): 생명 과학 조직이 GxP 응용 프로그램을 구축하기 위한 전략을 수립하는 데 도움이됩니다.
- FDA CFR Title 21 Part 11 가이드: 전자 기록에 대한 FDA 지침을 준수하는 [Azure](https://aka.ms/Azure-FDA-Guidelines) 및 [Office 365](https://aka.ms/o365-qualification-guideline) 인증 전략 수립에 대한 도움을 받으세요.

## <a name="frequently-asked-questions"></a>자주하는 질문

**조직의 GxP 규정 준수 노력에 Microsoft GxP 규정 준수를 사용할 수 있나요?**

Azure에 응용 프로그램을 배포하는 고객은 의도 된 용도에 따라 컴퓨터 시스템에 적용되는 GxP 요구 사항을 확인한 다음 자격 및 유효성 검사 프로세스를 관리하는 내부 절차를 따라 해당 요구 사항을 충족했음을 증명해야 합니다.

## <a name="resources"></a>리소스

- [Microsoft와 FDA CFR Title 21 Part 11](offering-fda-cfr-title-21-part-11.md)
- [Microsoft와 ISO/IEC 27001](offering-iso-27001.md)
- [Microsoft와 ISO 9001](offering-iso-9001.md)
- [Microsoft 보안 센터에 대한 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)
