---
title: US 수출 관리 규정 (귀)
description: Microsoft 클라우드 서비스 지원 고객이 미국 수출 관리 규정 (귀)이 준수 요구 사항을 충족 하 고 수출 통제 위험을 관리 하는 데 도움이 됩니다.
keywords: Microsoft 365, 규정 준수, 제안
localization_priority: None
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
ms.openlocfilehash: 4ad12f785a76f6ee733cb3b459ad58370a330f51
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416064"
---
# <a name="us-export-administration-regulations-ear"></a>US 수출 관리 규정 (귀)

## <a name="about-the-ear"></a>귀 정보

Commerce의 미국 부서에서는 [업계 및 보안 기관 (BIS)](https://www.bis.doc.gov/)을 통해 귀를 들을 때 관리 규정을 적용 합니다. 귀는 상업용 및 군사 목적 및 특정 방어 아이템에 모두 사용할 수 있는 "이중 사용" 항목을 포함 하 여 대부분의 상업용 상품, 소프트웨어 및 기술에 대 한 내보내기 및 다시 내보내기에 대 한 제어를 제어 하 고 적용 합니다.

BIS 지침은 데이터 나 소프트웨어가 클라우드에 업로드 되거나 사용자 노드 간에 전송 되는 경우, 즉 클라우드 공급자가 아닌 고객은 해당 데이터 또는 소프트웨어에 대 한 전송, 저장 및 액세스를 보장 하는 "내보내기"를 담당 합니다.

[BIS에 따르면](https://www.bis.doc.gov/index.php/documents/regulation-docs/412-part-734-scope-of-the-export-administration-regulations/file) *export* 는 보호 된 기술 또는 기술 데이터를 외부 대상에 전송 하거나 미국 내에 있는 외부 사용자에 게 배포 하는 것을 의미 합니다 (이 *내보내기가*라고도 함). 대체로 다음과 같은 사항을 제어 합니다.

- 미국에서 내보냅니다.
- 미국-원본 항목 및 특정 외부 원본 항목을 US-원본 콘텐츠의 *de-de minimis* 부분으로 다시 가져오거나 전송 합니다.
- 다른 국가에서 사용자에 게 전송 또는 공개

귀를 들을 수 있는 항목은 각 항목이 고유한 [수출 통제 분류 번호 (ECCN)](https://www.bis.doc.gov/index.php/licensing/commerce-control-list-classification/export-control-classification-number-eccn)를 할당 하는 CCL (Commerce Control 목록)에서 찾을 수도 있습니다. CCL에 나열 되지 않은 항목은 EAR99으로 지정 되며 대부분의 EAR99 상업용 제품에는 라이선스가 필요 하지 않습니다. 그러나 대상, 최종 사용자 또는 최종 사용에 따라 항목을 EAR99 항목에도 BIS 내보내기 라이선스가 필요할 수 있습니다.

7 월 2016에 게시 된 [최종 규칙](https://www.federalregister.gov/documents/2016/06/03/2016-12734/revisions-to-definitions-in-the-export-administration-regulations)은 FIPS 140-2 유효성이 검사 된 암호화 모듈을 사용 하 여 암호화 되지 않은 종단간 기술 데이터 및 소프트웨어의 전송 및 저장에도 일반 라이선스 요구 사항이 적용 되지 않는다는 것을 명확 하 게 설명 했으며, 사용자가 군사-수출 금지 국가 또는 러시아어 연합에 고의적으로 저장 되지 않았습니다.

## <a name="microsoft-and-the-ear"></a>Microsoft 및 귀

Microsoft 기술, 제품 및 서비스는 귀를 들을 수 있습니다. 귀, Microsoft Azure, Microsoft Azure 정부 및 Microsoft Office 365 정부 (GCCHigh 및 DoD 환경)에 대 한 준수 인증을 제공 하는 경우에는 적절 한 고객이 귀 관리 및 해당 준수 요구 사항을 충족 하는 데 도움이 되는 중요 한 기능과 도구를 소개 합니다.

귀를 적용 하는 미국 Commerce 부서는 고객 들이 Microsoft와 같은 클라우드 서비스 공급자가 아닌 고객에 게 해당 사용자의 내보내기 도구으로 간주 되는 위치를 결정 했습니다. 대부분의 고객 데이터는 귀 수출 통제의 "기술" 또는 "기술 데이터"로 간주 되지 않지만 Microsoft의 범위 내 클라우드 서비스는 고객이 직면 하는 잠재적 수출 통제 위험을 관리 하 고 크게 완화 하는 데 도움이 되도록 구성 됩니다. Microsoft는 단독으로 사용 하는 경우에만 정부 클라우드 서비스를 사용할 것을 권장 합니다. 적절 한 계획을 통해 고객은 다음 도구와 자체 내부 절차를 사용 하 여 US 수출 통제를 완벽 하 게 준수 하도록 할 수 있습니다.

- **데이터 위치에 대 한 컨트롤** 고객은 데이터를 저장 하 고 강력한 도구에 액세스 하 여 저장소를 제한 하는 것을 볼 수 있습니다. 따라서 데이터를 미국에 저장 하 고, 제어 되는 기술 또는 미국 이외의 기술 데이터의 전송을 최소화할 수 있습니다. 또한 고객 데이터는 순응 하지 않는 위치에 저장 되지 않으며, 데이터를 "의도적으로 저장" 하는 위치에 대 한 귀 prohibitions와 일치 합니다.
- **종단 간 암호화** 귀에 지정 된 실제 저장소 위치에 대 한 종단 간 암호화 안전한 harbor를 활용 하 여 Microsoft의 범위 내 클라우드 서비스는 내보내기 제어 위험 으로부터 보호 하는 데 도움이 되는 암호화 기능을 제공 합니다. 또한 전송 및 휴지에서 [데이터를 암호화 하는 다양 한 옵션과](https://aka.ms/Azure-Encryption-Overview) 암호화 옵션 중에서 선택할 수 있는 유연성을 제공 합니다.
- **인증 되지 않은 것으로 간주 되는 내보내기를 방지 하기 위한 도구 및 프로토콜** 또한 암호화를 사용 하면 비 US 사용자에 게 암호화 된 데이터에 대 한 액세스 권한이 있더라도 암호화 된 데이터를 읽거나 이해할 수 없는 경우에도 확인 되지 않는 잠재적으로 간주 되는 내보내기 (또는 다시 내보내기)를 방지할 수 있습니다. 따라서 제어 되는 데이터는 "릴리스" 되지 않습니다.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

- [Azure 및 Azure Government](https://aka.ms/AzureCompliance)
- [Office 365 정부 (GCC-High 및 DoD)](https://aka.ms/Office-365-Export-Controls)
- Intune

## <a name="how-to-implement"></a>구현 방법

사용자의 귀에 대 한 의무를 평가 하는 고객을 위한 US 수출 통제 및 지침 개요

- [Azure](https://aka.ms/Azure-Export-Controls)
- [Office 365](https://aka.ms/Office-365-Export-Controls)

## <a name="frequently-asked-questions"></a>자주하는 질문

**Microsoft 클라우드 서비스를 사용할 때 내보내기 컨트롤을 준수 하려면 어떻게 해야 하나요?**

귀에서 Microsoft 클라우드와 같은 클라우드 서버로 데이터를 업로드 하는 경우 클라우드 서비스 공급자가 아닌 데이터를 소유 하는 고객은 내보내기로 간주 됩니다. 이러한 이유 때문에 데이터 소유자 (즉, Microsoft 고객)는 Microsoft 클라우드의 사용에 따라 제어를 implicate 수 있는 방법을 신중히 평가 해야 하며, 사용 하거나 저장 하려는 데이터 중에 귀 컨트롤이 있을 수 있으며, 그렇다면 어떤 컨트롤이 적용 되는지를 결정할 수도 있습니다. [Azure](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) 및 [Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE1s5kI) 클라우드 서비스를 통해 고객이 US 수출 통제를 완벽 하 게 준수 하는 데 도움이 되는 방법에 대해 자세히 알아보세요.

**Microsoft 기술, 제품 및 서비스가 귀를 들을 수 있나요?**

대부분의 Microsoft 기술, 제품 및 서비스는 다음과 같습니다.

- 은 귀를 받지 않으므로 Commerce 컨트롤 목록에 없으며 ECCN을 포함 하지 않습니다.
- 또는 Microsoft의 자체 분류에 적합 한 EAR99 또는 5D992 대규모 시장 이며 라이선스 없이 라이선스가 필요 하지 않은 (NLR) 인 비 수출 금지 국가로 내보낼 수 있습니다.

즉, 라이선스가 필요 하지 않을 수 있는 ECCN이 할당 된 Microsoft 제품이 몇 개 있습니다. 적절 한 라이선스 유형 및 내보내기 목적으로 적합 한 국가를 확인 하려면 귀 또는 legal 자문 위원를 참조 하세요.

**ITAR (무장 규정)의 귀와 국제 트래픽 간의 차이점은 무엇 인가요?**

가장 넓은 응용 프로그램을 사용 하는 기본 US 수출 통제는 미국 상업 부서에서 관리 하는 귀입니다. 귀는 상업용 및 군사 응용 프로그램을 모두 포함 하는 이중 사용 항목 및 모든 상업용 응용 프로그램을 포함 하는 항목에 적용 됩니다.

또한 미국의 가장 중요 한 항목 및 기술을 제어 하는 ITAR 같은 별도의 특수 수출 통제 규정이 있습니다. 미국 부서에서 관리 하 고, 관련 기술 데이터를 포함 하 여 다양 한 군사, 방어 및 인텔리전스 항목 ("방어 기사" 라고도 함)의 내보내기, 임시 가져오기, 다시 내보내기 및 전송에 대 한 제어를 부여 합니다.

## <a name="resources"></a>리소스

- [Microsoft Products 내보내기: 개요](https://www.microsoft.com/exporting/overview.aspx)
- [Microsoft 제품 내보내기: FAQ](https://www.microsoft.com/exporting/faq.aspx)
- [Microsoft 제품 내보내기: 제품 조회](https://www.microsoft.com/exporting/exporting-information.aspx)
- [암호화에 대 한 수출 제한 사항](https://docs.microsoft.com/windows/uwp/security/export-restrictions-on-cryptography)
- [Microsoft 및 FIPS 140-2](offering-fips-140-2.md)
- [Microsoft 및 ITAR](offering-itar.md)
- [Microsoft 보안 센터에 대한 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)
