---
title: '2단계: 사용자 환경에 대한 분류 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 조직에서 데이터를 분류하는 다양한 방법을 이해하고 구성합니다.
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869917"
---
# <a name="step-2-configure-classification-for-your-environment"></a>2단계: 사용자 환경에 대한 분류 구성

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

이 단계에서는 법률 및 준수 팀과 함께 조직의 데이터에 대한 분류 체계를 정의합니다.

## <a name="microsoft-classifications"></a>Microsoft 분류

Microsoft 365에는 세 가지 유형의 분류가 포함되어 있습니다.

- Office 365의 중요한 정보 유형
- Office 365 레이블
- Azure Information Protection 레이블 및 보호

### <a name="sensitive-information-types-for-office-365"></a>Office 365의 중요한 정보 유형

Office 365의 중요한 정보 유형은 검색과 같은 자동화된 프로세스에서 건강 보험 번호 및 신용 카드 번호와 같은 특정 정보 유형을 인식하는 방법을 정의합니다. 중요한 정보 유형을 사용하여 중요한 데이터를 찾고 데이터 손실 방지 규칙을 적용하여 이 데이터를 보호할 수 있습니다. 자세한 내용은 [데이터 손실 방지 정책 개요](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)를 참조하세요. 예를 들어 중요한 정보 유형은 GDPR(일반 데이터 보호 규정)과 같은 준수 및 규정 요구 사항을 준수하는 데 특히 유용합니다.

### <a name="office-365-labels"></a>Office 365 레이블
개인 데이터뿐 아니라 SharePoint Online 및 비즈니스용 OneDrive에 저장된 높은 규제 및 영업 비밀 파일에 Office 365 레이블을 사용할 수 있습니다. 레이블을 만드는 방법을 포함하여 자세한 내용은 [레이블 개요](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30)를 참조하세요.

Office 365 레이블을 사용하려면 각 보호 수준에 대해 하나 이상을 구성해야 합니다. 예를 들어 다음에 대한 세 가지 레이블을 만듭니다.

- 기준
- 중요
- 높은 규제

### <a name="azure-information-protection-labels-and-protection"></a>Azure Information Protection 레이블 및 보호

Azure Information Protection 레이블을 사용하여 조직의 문서와 전자 메일을 분류하고 필요에 따라 보호할 수 있습니다. 이러한 레이블은 Office 365 외부에 저장된 문서에 적용될 수 있으며, 규칙 및 조건을 정의하는 관리자가 자동으로 적용하거나, 사용자가 수동으로 적용하거나, 사용자에게 권장 사항을 제공하는 상황에서 두 가지 방법을 조합하여 적용할 수 있습니다.

Azure Information Protection 레이블 및 보호를 계획하고 배포하려면 다음을 수행합니다.

1. [Azure Information Protection에 대한 요구 사항](https://docs.microsoft.com/information-protection/get-started/requirements)을 검토합니다.
2. [분류, 레이블 지정 및 보호에 대한 배포 로드맵](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)을 따릅니다.

자세한 내용은 [Azure Information Protection 설명서 라이브러리](https://docs.microsoft.com/information-protection/)를 참조하세요.

## <a name="classification-for-gdpr"></a>GDPR에 대한 분류

GDPR에 대한 개인 데이터를 포함하는 예제 분류 체계는 [개인 데이터에 대한 분류 체계 설계](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)를 참조하세요.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 데이터 분류](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step3)을 확인하세요.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[Office 365에 대한 향상된 보안 구성](infoprotect-configure-increased-security-office-365.md)|

