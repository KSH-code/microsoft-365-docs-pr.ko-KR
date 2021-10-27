---
title: Microsoft 준수 관리자에서 평가 템플릿 작업
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 준수 관리자에서 평가를 작성하기 위해 템플릿을 사용 및 관리하는 방법을 이해합니다. 서식 있는 파일 형식을 사용하여 서식 있는 서식 Excel 수정합니다.
ms.openlocfilehash: 74b896f6c0fdd625cf50cc04a31fa79d48dc3a4e
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587684"
---
# <a name="learn-about-assessment-templates-in-compliance-manager"></a>준수 관리자의 평가 템플릿에 대해 자세히 알아보기

**이 문서의 예는** 템플릿의 작동 **방식과** 평가 템플릿 페이지에서 템플릿을 **관리하는** 방법을 이해합니다. 새 템플릿 **만들기,** 기존  서식  파일 확장 및 수정, 서식 파일 데이터 서식 지정 및 서식 **Excel** 내보내기 위한 지침을 **얻습니다.**

> [!IMPORTANT]
> 조직에서 사용할 수 있는 평가 템플릿은 사용권 계약에 따라 달라 하게 됩니다. [세부 정보를 검토합니다.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="templates-overview"></a>서식 파일 개요

템플릿은 준수 관리자에서 평가를 만들기 위한 컨트롤 프레임워크입니다. 당사의 포괄적인 템플릿 집합은 조직이 데이터 수집 및 사용에 대한 국가, 지역 및 산업별 요구 사항을 준수하는 데 도움이 될 수 있습니다.

EU GDPR 템플릿 및 ISO/IEC 27701:2019 템플릿과 같은 기본 인증 또는 규정과 동일한 이름으로 템플릿을 참조합니다. 준수 관리는 다양한 유형의 제품을 평가하는 데 사용할 수 있으며 각 템플릿은 두 가지 버전으로 제공됩니다. 하나는 Microsoft 365, 선택한 제품에 맞게 조정할 수 있는 유니버설 버전입니다.

미국 정부 Community(GCC) 보통, GCC High 및 DoD(국방부) 고객은 현재 Microsoft 365 템플릿 버전을 사용할 수 있지만 유니버설은 사용할 수 없습니다.

## <a name="template-availability-and-licensing"></a>서식 파일 가용성 및 라이선스

준수 관리자에는 포함 및 프리미엄 템플릿의 두 가지 범주가 있습니다.

1. **포함된 템플릿은** 준수 관리자 라이선스를 통해 부여하며 주요 규정 및 요구 사항을 충족합니다. 라이선스 계약에 따라 사용할 수 있는 템플릿에 대한 자세한 내용은 라이선스 세부 [정보를 참조합니다.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
2. **Premium 수 있는** 템플릿을 추가 요구 사항을 충족하고 시나리오는 템플릿 라이선스를 구입하여 얻을 수 있습니다.

평가 만들기를 시작하면 준수 관리자가 사용 현황을 모니터링할 수 있도록 활성 상태인 서식 파일 수를 추적합니다. 자세한 내용은 활성 및 비활성 [템플릿을 참조합니다.](compliance-manager-templates.md#active-and-inactive-templates)

준수 [관리자에서 사용할 수](compliance-manager-templates-list.md) 있는 서식 파일 전체 목록을 하세요.

### <a name="purchase-premium-template-licenses"></a>프리미엄 템플릿 라이선스 구입

템플릿 라이선스는 준수 관리자 라이선스 계약에 따라 이러한 방법 중 하나 이상을 통해 얻을 수 있습니다. 구매가 마무리된 후 48시간 이내에 테넌트에서 템플릿을 사용할 수 있습니다.

**상업용 및 GCC 보통**

상업용 및 GCC 보통 계정은 관리 센터에서 템플릿 라이선스를 구매할 수 있습니다( 구독, 라이선스 및 청구에 대해[자세히 알아보시고).](/microsoft-365/commerce/) 구매할 라이선스 수량과 결제 계획을 선택합니다.

구매 링크:

- [상업용](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/46E9BF2A-3C8D-4A69-A7E7-3DA04687636D)
- [GCC 보통](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/3129986d-5f4b-413b-a34b-b706db5a7669)

또한 클라우드 솔루션 공급자 프로그램 또는 볼륨 [라이선싱에](https://partner.microsoft.com/membership/cloud-solution-provider) 참여하여 라이선스를 [취득할 수도 있습니다.](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)

**GCC 높음 및 DOD 계정**

GCC 높음 및 DOD 계정은 볼륨 라이선스를 통해 템플릿 [라이선스를 구입해야 합니다.](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)

### <a name="try-out-premium-templates"></a>고급 템플릿 사용해기

구매하기 전에 프리미엄 템플릿을 사용해 보시고 평가판 버전의 라이선스를 취득할 수도 있습니다. 평가판 라이선스는 90일 동안 최대 25개 템플릿에 좋습니다. 평가판 라이선스를 획득하면 48시간 이내에 테넌트에서 템플릿을 사용할 수 있습니다.

평가판을 시작하려면 조직에 적합한 링크를 선택하세요.

- [상업용](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/e320704d-b7c9-4012-b6a6-0a2679790360)
- [GCC 보통](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/87ed2908-0a8d-430a-9635-558ed42b581f)
- [GCC High](https://portal.office365.us/SubscriptionDetails?OfferId=e14362d7-2c11-4a43-9c92-59f1b499b96a)
- [DOD](https://portal.apps.mil/Commerce/Trial.aspx?OfferId=17e28290-7de6-41a9-af30-f6497396ab2e)

#### <a name="active-and-inactive-templates"></a>활성 및 비활성 템플릿

템플릿은 활성화 상태를 활성 또는 비활성으로 표시합니다.

- 템플릿에서 **평가를** 만들면 템플릿이 활성으로 간주됩니다.
- 조직에서 **평가에** 템플릿을 사용하지 않는 경우 템플릿이 비활성으로 간주됩니다.

평가를 구매한 프리미엄 템플릿에 연결하는 경우 해당 템플릿은 1년 동안 활성화됩니다. 취소하지 않으면 구매가 자동으로 갱신됩니다.

#### <a name="activated-templates-counter"></a>활성화된 템플릿 카운터

평가 페이지 및 평가 템플릿 페이지에는 위쪽 근처에 활성화된 **템플릿** 카운터가 있습니다. 카운터에는 사용권 계약에 따라 사용할 자격이 있는 수의 사용 대상 서식 파일 수가 표시됩니다. 템플릿 사용은 인증 수준에서 계산됩니다.

예를 들어 카운터에 2/5가 표시되면 조직에서 사용할 수 있는 5개 중 2개 템플릿을 활성화한 것입니다.

카운터에 5/2가 표시되면 이는 조직이 제한을 초과하고 사용 중이 있는 프리미엄 템플릿 3개를 구입해야 하다는 것을 나타냅니다.

Microsoft 365 및 유니버설 버전의 템플릿에는 공동 라이선스가 있으므로 두 개 이상의 제품에서 동일한 기본 인증을 사용할 수 있습니다. 동일한 템플릿 중 하나 또는 두 버전을 모두 사용하면 하나의 활성화된 템플릿으로 계산됩니다.

자세한 내용은 준수 관리자 라이선스 [지침을 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

## <a name="view-and-manage-templates"></a>서식 파일 보기 및 관리

준수 관리자의 평가 템플릿 페이지에 템플릿 목록과 템플릿에 대한 주요 세부 정보가 표시됩니다. 목록에는 준수 관리자가 제공한 서식 파일과 조직에서 수정하거나 만든 모든 템플릿이 포함됩니다. 필터를 적용하여 인증, 제품 범위, 국가, 산업, 해당 템플릿을 만든 사람 및 템플릿이 평가를 만들 수 있는지 여부에 따라 템플릿을 찾을 수 있습니다.

해당 행에서 템플릿을 선택하여 세부 정보 페이지를 표시합니다. 이 페이지에는 템플릿에 대한 설명과 인증, 범위 및 컨트롤 세부 정보에 대한 추가 정보가 포함되어 있습니다. 이 페이지에서 평가를 만들거나 템플릿 데이터를 내보낼 적절한 단추를 선택하거나 템플릿을 Excel 수 있습니다.

## <a name="create-an-assessment-template"></a>평가 템플릿 만들기

준수 관리자에서 사용자 지정 평가를 위한 사용자 지정 평가를 위한 새 템플릿을 만들기 위해 특수하게 형식이 Excel 스프레드시트를 사용하여 필요한 컨트롤 데이터를 어셈블합니다. 스프레드시트를 완료한 후 준수 관리자로 가져올 것입니다. 자세한 내용은 평가 템플릿 [만들기를 참조합니다.](compliance-manager-templates-create.md)

## <a name="modify-an-assessment-template"></a>평가 템플릿 수정

준수 관리자에서 평가를 사용할 때 만든 평가 템플릿을 수정할 수 있습니다. 이 프로세스는 서식 파일 데이터를 사용하여 서식 있는 Excel 업로드하는 템플릿 만들기 프로세스와 비슷합니다. 변경하는 방법 및 유지 관리하려는 데이터를 보존하는 방법에 대한 자세한 내용은 평가 템플릿 [수정을 참조합니다.](compliance-manager-templates-modify.md)

## <a name="extend-an-assessment-template"></a>평가 템플릿 확장

준수 관리자는 기존 템플릿에 자체 컨트롤 및 개선 작업을 추가하는 옵션을 제공합니다. 이 프로세스를 템플릿 확장이라고 합니다. 템플릿을 확장하기 위해 평가 템플릿 또는 유니버설 평가 템플릿을 확장하는지 여부에 따라 템플릿 데이터에 Microsoft 365 특별한 지침을 사용하게 됩니다. 자세한 내용은 평가 템플릿 [확장을 참조합니다.](compliance-manager-templates-extend.md)

## <a name="format-assessment-template-data-in-excel"></a>평가 템플릿 데이터 형식을 Excel

준수 관리자에서 평가 템플릿을 만들거나 수정하거나 확장하는 경우 특정 형식 및 Excel 사용하는 스프레드시트에서 작업하게 됩니다. 파일을 올바르게 가져오기 위해 이러한 사양을 따라야 합니다. 자세한 내용은 에서 평가 템플릿 데이터 [형식을 Excel.](compliance-manager-templates-format-excel.md)

## <a name="export-a-template"></a>서식 파일 내보내기

템플릿의 Excel 포함된 파일 형식을 내보낼 수 있습니다. 템플릿을 수정하려면 템플릿을 내보내야 합니다. 수정 프로세스에서 편집하고 업로드하는 Excel 파일이기 때문에 템플릿을 [내보내야 합니다.](compliance-manager-templates-modify.md) 새 사용자 지정 서식 파일을 구성하는 동안 해당 서식 파일에서 데이터를 사용하려는 경우 참조할 서식 파일을 내보낼 수도 있습니다.

템플릿을 내보내기 위해 템플릿 세부 정보 페이지로 이동한 다음 내보낼 Excel **선택합니다.**

준수 관리자 템플릿에서 확장한 템플릿을 내보낼 때 내보낼 파일에는 템플릿에 추가한 특성만 포함되어 있습니다. 내보낼 파일에는 Microsoft에서 제공하는 원본 서식 파일 데이터가 포함되어지 않습니다. 이러한 보고서를 얻었다면 평가 보고서 내보내기 [지침을 참조하세요.](compliance-manager-assessments.md#export-an-assessment-report)