---
title: GDPR용 DPIA Azure
description: ''
keywords: DPIA, Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
hideEdit: true
titleSuffix: Microsoft GDPR
ms.openlocfilehash: cb2b9251a7b4fdaa987a803075f0040b93b2f59a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073365"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-azure"></a>데이터 보호 영향 평가: Microsoft Azure를 사용하는 데이터 컨트롤러의 참고 자료

일반 데이터 보호 규정(GDPR)에 따라 데이터 컨트롤러는 “자연인의 권리와 자유에 대한 높은 위험을 초래할 수 있는” 작업 처리를 위해 데이터 보호 영향 평가(DPIA)를 준비해야 합니다. Microsoft Azure에는 내재되지 않았으므로 DPIA를 사용하는 데이터 컨트롤러에서 DPIA 만들기가 필요합니다. 더 정확히 말하자면, DPIA가 필요한지 여부는 데이터 컨트롤러가 Microsoft Azure를 배포, 구성, 사용하는 *방법*의 세부 정보와 컨텍스트에 따라 달라집니다.

이 문서의 목적은 Microsoft Azure에 대한 정보와 데이터 컨트롤러를 제공하여 DPIA 필요 여부, 필요한 경우 포함할 세부 사항을 결정할 수 있도록 지원하는 것입니다.

> [!Note]
> Microsoft는이 문서에 법적 자문을 제공하지 않습니다. 이 문서는 정보 제공의 목적으로만 제공됩니다. 고객은 개인 정보 책임자와 관리 담당자 및 법적 자문과 함께 Microsoft Azure 또는 기타 Microsoft 온라인 서비스 사용과 관련된 DPIA의 필요 여부 및 콘텐츠를 결정하는 것이 좋습니다.

## <a name="part-1--determining-whether-a-dpia-is-needed"></a>1부 – DPIA 필요 여부 결정

GDPR의 35조를 준수하려면 데이터 컨트롤러에서 데이터 보호 영향 평가(DPIA) "이 때 특히 신기술을 사용하고, 특성, 범위, 컨텍스트 및 처리 목적을 고려하는 처리 유형은 자연인의 권리와 자유에 많은 위험을 초래할 수 있습니다"를 만들어야 합니다. 다음 표에 설명된 높은 위험을 나타내는 특정 요인을 자세하게 정리합니다. DPIA가 필요한지를 결정할 때, 데이터 컨트롤러는 컨트롤러의 Microsoft Azure에 대한 특정 구현과 사용의 관점에서 관련 요인과 함께 이 요인을 고려해야 합니다.

|||
|:----|:----|
|**높은 위험 요인**|**Microsoft Azure에 대한 관련 정보**|
| 프로파일링을 포함한 자동화된 처리의 기반이 되고 자연인에 관한 법적 영향을 행사하거나 유사하게 자연인에게 중대한 영향을 주는 의사 결정의 기반이 되는 자연인과 관련된 개인 측면의 체계적이고 광범위한 평가.| Microsoft Azure는 특정 데이터의 자동화된 처리를 수행할 수 있는 기능을 제공하지 않습니다. <br><br> *그러나 Azure는 고도로 사용자 정의가 가능한 서비스이므로 데이터 컨트롤러가 Azure를 잠재적으로 이러한 처리에 사용되도록 구성할 수 있습니다*. 컨트롤러는 Azure의 사용 현황에 따라 결정해야 합니다. |
| 특정 범주의 대규모* 데이터(인종 또는 민족 태생, 정치적 견해, 종교적 또는 철학적 신념, 노동 조합 회원 및 유전자 데이터, 자연인의 고유한 식별을 목적으로 하는 생체 데이터, 건강 또는 자연인의 성생활이나 성적 취향에 관한 데이터의 처리) 처리 또는 범죄 유죄 판결 및 범죄와 관련된 개인 데이터 처리. | Microsoft Azure는 특수한 범주의 개인 데이터를 처리하도록 특별히 설계되지 않았으며 Azure의 사용으로 인해 컨트롤러 처리의 내재 위험이 증가하지 않습니다. <br><br> *그러나 데이터 컨트롤러는 Microsoft Azure를 사용하여 열거된 특정 범주의 데이터를 처리할 수 있습니다*. Microsoft Azure는 고도로 사용자 지정 가능한 서비스이므로 고객이 특정 범주의 개인 데이터와 같은 모든 유형의 데이터를 추적하거나 처리할 수 있습니다. 그러나 데이터 프로세서로 Microsoft는 그러한 사용을 제어할 수 없으며 그러한 사용에 대한 정보를 거의 또는 전혀 가지고 있지 않습니다. 데이터 컨트롤러 데이터의 적절한 사용을 결정하는 것은 데이터 컨트롤러의 책임입니다. |
| 공개적으로 액세스할 수 있는 영역을 대규모로 체계적으로 모니터링.  | Microsoft Azure는 이러한 모니터링을 수행하거나 용이하게 하도록 설계되지 않았습니다. <br><br> *그러나 데이터 컨트롤러는 Azure를 사용하여 이러한 모니터링을 통해 수집된 데이터를 처리할 수 있습니다.* Microsoft Azure는 고도로 사용자 지정 가능한 서비스이므로 고객이 모니터링 데이터와 같은 모든 유형의 데이터를 추적하거나 처리할 수 있습니다. 그러나 데이터 프로세서로 Microsoft는 그러한 사용을 제어할 수 없으며 그러한 사용에 대한 정보를 거의 또는 전혀 가지고 있지 않습니다. 데이터 컨트롤러 데이터의 적절한 사용을 결정하는 것은 데이터 컨트롤러의 책임입니다. |

## <a name="part-2--contents-of-a-dpia"></a>2부 - DPIA의 내용

문서 35(7)는 데이터 보호 영향 평가가 처리의 목적과 계획된 처리에 대한 체계적인 설명을 명시하도록 규정하고 있습니다. 포괄적인 DPIA에 대한 체계적인 설명에는 처리되는 데이터의 유형, 데이터 보관 기간, 데이터 위치 및 전송 위치, 제 3자가 데이터에 액세스 할 수있는 요소 등의 요소가 포함될 수 있습니다. 또한 DPIA에는 다음이 포함되어야 합니다.

- 목적과 관련한 처리 작업의 필요성 및 비례의 원칙 평가;
- 자연인의 권리와 자유에 대한 위험 평가;
- 위험을 해결하기 위한 세이프가드, 보안 조치 등의 계획된 조치, 개인 데이터의 보호를 보장하고 데이터 주체 및 기타 관련자의 권리와 합법적 이익을 고려하여 이 규정을 준수함을 입증하기 위한 메커니즘.

아래 테이블에는 각 요소와 관련된 Microsoft Azure에 대한 정보가 포함됩니다. 1부에서와 같이 데이터 컨트롤러는 Microsoft Azure의 특정 구현 및 사용의 컨텍스트에서 기타 관련 요인과 함께 아래에 제공된 세부 정보를 고려해야 합니다.

||||
|:---|:---|:--|
|**DPIA의 요소**|**Microsoft Azure에 대한 관련 정보**| |
| 처리 목적 | Microsoft Azure를 사용하여 데이터를 처리하는 목적은 컨트롤러를 구현, 구성 및 사용하는 방식에 따라 결정됩니다. <br><br> [온라인 서비스 약관(OST)](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)에 명시된 바와 같이, Microsoft는 데이터 프로세서로서 요청된 서비스를 고객과 데이터 컨트롤러에게 제공하기 위해 고객 데이터를 처리합니다. Microsoft는 광고 또는 유사한 상업적 목적으로 고객 데이터 또는 파생된 정보를 사용하지 않습니다. |   |
| 처리된 개인 데이터의 범주  | *고객 데이터* – 엔터프라이즈 서비스를 사용하여 고객이 Microsoft에 제공하거나 고객 대신에 Microsoft에 제공된 모든 데이터(모든 텍스트, 소리, 동영상 또는 이미지 파일 포함)입니다.  고객 데이터에는 (1) 최종 사용자의 식별 가능한 정보(예: Azure Active Directory의 사용자 이름 및 연락처 정보) 및 고객이 특정 서비스에 업로드하거나 해당 서비스에서 만드는 고객 콘텐츠(예: Azure Storage 계정의 고객 콘텐츠, Azure SQL Database의 고객 콘텐츠 또는 Azure 가상 머신에 있는 고객의 가상 머신 이미지)가 포함되어 있습니다.<br><br> *시스템 생성 로그* — Microsoft에서 생성한 로그 및 관련 데이터이며, 이는 Microsoft에서 엔터프라이즈 서비스를 제공하도록 도와줍니다. 시스템 생성 로그에는 주로 가명 처리된 데이터(예: 시스템에서 생성된 고유한 ID)가 있으며, 이 데이터는 개인을 직접 식별할 수 없지만 엔터프라이즈 서비스를 사용자에게 전달하는 데 사용됩니다.  시스템 생성 로그에는 사용자 이름과 같은 최종 사용자에 대한 식별 가능한 정보가 포함될 수도 있습니다. <br><br> *지원 데이터* — 온라인 서비스에 대한 기술 지원을 얻기 위해 Microsoft와의 계약을 통해 고객이 Microsoft 또는 고객을 대신하여 Microsoft에서 제공한 데이터(또는 고객이 Microsoft가 온라인 서비스에서 얻도록 허가한 데이터)입니다. <br><br> Azure에서 처리하는 데이터와 관련된 자세한 내용은 [온라인 서비스 약관](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) 및 [Microsoft 보안 센터](https://www.microsoft.com/trustcenter)에서 확인하세요.</p> |   |
| 데이터 보존 | Microsoft는 고객이 온라인 서비스를 사용할 수있는 기간 동안 그리고 모든 고객 데이터가 고객에 의해 검색되거나 OST의 조건에 따라 삭제될 때까지 고객 데이터를 보유 및 처리합니다.  고객의 구독 기간 동안 항상 고객은 각 온라인 서비스에 저장된 고객 데이터를 액세스하고 추출할 수 있습니다. 무료 평가판 및 LinkedIn 서비스를 제외하고 Microsoft는 고객이 데이터를 추출할 수 있도록 고객의 구독이 만료 또는 종료된 이후 90일 동안 기능이 제한된 계정에서 온라인 서비스에 저장된 고객 데이터를 보유하게 됩니다. 90일의 보유 기간이 종료되면 Microsoft는 고객의 계정을 비활성화하고 고객 데이터를 삭제합니다. 고객은 [Azure Data Subject Request GDPR 문서](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)에 설명 된 기능을 사용하여 데이터 주체 요청에 따라 개인 데이터를 삭제할 수 있습니다. |   |
| 개인 데이터의 위치 및 전송 | 고객은 지정된 [지역](https://azuredatacentermap.azurewebsites.net/) 내에서 사용하지 않는 고객 데이터를 프로비저닝할 수 있으며 OST에 명시된 대로 특정 예외 사항을 적용합니다. 데이터 보존은 [Azure 전역 인프라](https://azure.microsoft.com/global-infrastructure/) 웹 페이지에서 찾을 수 있습니다.<br><br>유럽 경제 지역 및 스위스의 개인 데이터의 경우, Microsoft는 GDPR 제 46조에 따라 개인 데이터가 타국가 또는 국제 기구로 전송되는 과정에 적절한 세이프가드가 적용되도록 보장합니다. 프로세서 및 기타 모델 계약에 대한 표준 계약 조항에 따른 Microsoft의 약속 외에도 Microsoft는 유럽-미국, 스위스-미국, 개인 정보 보호 방화벽 및 수반한 약속에 대해 인증되었습니다. |   |
| 타사와 데이터 공유 | Microsoft는 고객 및 기술 지원, 서비스 유지 보수 및 기타 운영과 같은 기능을 지원하기 위해 하위 프로세스(즉, 개인 데이터를 처리하는 하도급업체) 역할을 하는 타사와 데이터를 공유합니다. Microsoft가 고객 데이터 또는 지원 데이터를 전송하는 하도급업자는 [온라인 서비스 약관](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)의 데이터 보호 약관보다 덜 안전하지만 Microsoft와 서면 계약을 체결하게 됩니다. 고객 데이터 또는 지원 데이터가 공유되는 모든 타사 하위 프로세서는 [하도급업자 목록](https://www.microsoft.com/trustcenter/privacy/who-can-access-your-data-and-on-what-terms#subcontractors)(하도급업자 목록 보기)에 포함됩니다. <br><br> 고객 데이터 및 지원 데이터에 대한 법 집행 및 제3자 요청에 대한 Microsoft의 대응에 관한 정보는 온라인 서비스 약관에 나와 있습니다. Microsoft가 법적으로 금지하지 않는 한 Microsoft는 법 집행 기관 또는 제 3자를 고객에게 직접 리디렉션하려고 시도합니다. |   |
| 데이터 주체 권리 | 프로세서로 작동할 때 Microsoft는 고객(즉, 데이터 컨트롤러)이 데이터 주체의 개인 데이터를 사용할 수 있도록 하고 고객이 GDPR에 따라 권리를 행사할 때 데이터 주체 요청을 수행할 수 있는 기능을 제공합니다. Microsoft는 제품의 기능과 프로세서로의 역할에 있어 일관된 방식으로 진행합니다. Microsoft가 고객의 데이터 주체로부터 GDPR에 따라 권리 중 하나를 행사하도록 요청을 받으면 데이터 컨트롤러에게 요청이 리디렉션됩니다.<br><br>[Azure 데이터 주체 요청 GDPR 설명서](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)는 Azure의 기능을 사용하여 데이터 주체 권한을 지원하는 방법에 대한 설명을 제공합니다. |   |
| 목적과 관련한 처리 작업의 필요성 및 비례의 원칙 평가 | 이러한 평가는 데이터 컨트롤러의 요구와 처리 목적에 따라 달라집니다.<br><br>Microsoft에서 수행하는 처리와 관련하여 이러한 처리는 데이터 컨트롤러에 서비스를 제공하기 위한 목적에 필수적이며 비례합니다. Microsoft는 OST 준수를 약속합니다. | |
| 데이터 주체의 권리와 자유에 대한 위험 평가 | Microsoft Azure 사용으로 인한 데이터 주체의 권리와 자유에 대한 주요 위험은 데이터 컨트롤러가 Microsoft Azure를 구현, 구성, 사용하는 방법과 상황의 기능입니다.<br><br> 그러나 다른 서비스와 마찬가지로 서비스에서 보관하는 개인 정보는 권한이 없는 액세스나 부주의한 공개의 위험이 있습니다. 이러한 위험을 해결하기 위해 Microsoft에서 취하는 조치는 OST에 설명되어 있으며 아래에서 세부 정보를 확인할 수 있습니다. | |
| 위험을 해결하기 위한 세이프가드, 보안 조치 등의 계획된 조치, 개인 데이터의 보호를 보장하고 데이터 주체 및 기타 관련자의 권리와 합법적 이익을 고려하여 GDPR을 준수함을 입증하기 위한 메커니즘 | Microsoft는 고객 데이터 보안을 보호하기 위해 노력합니다. Microsoft에서 취하는 보안 조치는 OST의 세부 정보에 설명되어 있습니다. <br><br> Microsoft는 엄격한 보안 표준 및 업계 선도적인 데이터 보호 방법론을 준수합니다. Microsoft는 새로운 위협에 대응하기 위해 지속해서 시스템을 개선하고 있습니다. 클라우드 거버넌스 및 개인 정보 보호 규정 관련 세부 정보는 [보안 센터의 클라우드 거버넌스 및 개인 정보 보호](https://www.microsoft.com/trustcenter/guidance/ensure-compliance) 페이지에서 제공됩니다. <br><br> Microsoft는 처리하는 개인 데이터를 보호하기 위해 합리적이고 적합한 기술적 및 조직적 조치를 취합니다. 이러한 조치에는 내부 개인 정보 보호 정책 및 규정, 계약상의 약속, 국제 및 지역 표준 인증이 포함되나 국한되지 않습니다. 자세한 정보는 [보안 센터의 개인 정보 보호 표준 페이지](https://www.microsoft.com/trustcenter/privacy/we-set-and-adhere-to-stringent-standards)에서 제공됩니다. <br><br> Microsoft는 Microsoft의 개인 데이터 사용 및 처리를 설명하는 데 도움이 되는 중요하고 투명한 고객 관련 보안 및 개인 정보 보호 자료를 제공합니다. 고객은 질문 사항을 준비하여 Microsoft에 문의하는 것이 좋습니다. <br><br> 또한 Microsoft는 데이터 보호 영향 평가 및 기록 유지를 포함하지만 국한되지 않는 데이터 프로세스에 적용되는 모든 기타 GDPR 의무를 준수합니다. |  |

## <a name="learn-more"></a>자세한 정보

- [Microsoft 보안 센터](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
