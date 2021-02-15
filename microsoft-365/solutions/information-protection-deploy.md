---
title: Microsoft 365를 사용하여 데이터 개인 정보 보호 규정에 대한 정보 보호 배포
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: 정보를 보호하고 데이터 개인 정보 보호 규정을 준수하도록 보안 및 서비스 인프라를 구성합니다.
ms.openlocfilehash: 9af0a113d9b0eb2cbca07fdf457cd8bb7db3e094
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842299"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Microsoft 365를 사용하여 데이터 개인 정보 보호 규정에 대한 정보 보호 배포

조직은 사용자가 IT 인프라에 저장된 개인 정보 보호, 관리 및 제어 권한을 제공해야 하는 지역별 데이터 개인 정보 보호 규정의 적용을 을(를) 따라야 할 수 있습니다(이 경우, 조직은 클라우드와 같은 IT 인프라에 저장된 개인 정보를 보호, 관리 및 제어해야 합니다. 데이터 개인 정보 보호 규정의 가장 좋은 예는 유럽 연합의 GDPR(일반 데이터 보호 규정)입니다. 데이터 개인 정보 규정을 준수하지 못하면 상당한 벌금이 부과될 수 있습니다.

Microsoft 365의 데이터 유형의 예로는 Microsoft Teams의 채팅 세션, Exchange의 전자 메일 및 SharePoint 및 OneDrive의 파일이 있습니다. 이 솔루션은 위험을 평가하고, 데이터 개인 정보 규정이 적용된 Microsoft 365 서비스에 저장된 개인 데이터에 대한 데이터 개인 정보 보호 인시던트의 보호, 관리 및 대응 방법에 대한 지침을 제공합니다.

![데이터 개인 정보 보호 규정에 대한 정보 보호](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png)

데이터 개인 정보 보호 요구에 대한 Microsoft 365 ID, 장치 및 위협 방지 컨트롤을 사용하는 데 관한 추가 정보도 제공됩니다. 

데이터 개인 정보 보호 규정을 준수하기 위한 정보를 보호하기 위한 기준을 충족하기 위해 이러한 Microsoft 365 기능 및 기능을 사용하세요.

| 기능 또는 특징 | 설명 | 라이선싱 |
|:-------|:-----|:-------|
| 규정 관리자 | 규정 준수 활동을 관리하고, 현재 준수 구성의 전체 점수를 얻은 다음 Microsoft 365 규정 준수 센터에서 이 워크플로 기반 위험 평가 도구의 개선을 위한 권장 사항을 찾아야 합니다. | Microsoft 365 E3 및 E5 |
| Office 365용 Microsoft Defender | 전자 메일 메시지, 사무실 문서 및 협업 도구와 같은 Microsoft 365 앱과 데이터를 공격으로부터 보호합니다. | Microsoft 365 E3 및 E5 | 
| 민감도 레이블 | 전자 메일, 파일 또는 사이트에 다양한 수준의 보호 기능을 갖춘 레이블을 배치하여 사용자의 생산성과 협업 능력을 저해하지 않고 조직의 데이터를 분류하고 보호합니다. | Microsoft 365 E3 및 E5 |
| 데이터 손실 방지(DLP). | 개인 정보가 포함된 데이터 공유와 같은 위험하거나 부주의하거나 부적절한 공유를 내외부적으로 탐지, 경고 및 차단합니다. | Microsoft 365 E3 및 E5 | 
| 데이터 보존 레이블 및 정책. | 조직의 정책 또는 데이터 규정을 준수하기 위해 고객의 개인 데이터 스토리지에 대한 데이터 및 요구사항을 보관하는 기간과 같은 정보 거버넌스 제어를 구현합니다. | Microsoft 365 E3 및 E5 |
| 전자 메일 암호화 | 고객의 개인 데이터와 같이 규제 데이터가 들어 있는 조직 내외부의 사용자 간에 암호화된 전자 메일 메시지를 주고 받습니다. | Microsoft 365 E3 및 E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>이 솔루션의 지침 구성

하나 이상의 개인 정보 관련 규정에 따라 개인 데이터를 식별, 관리, 제어 및 모니터링하는 데 사용할 수 있는 Microsoft 365 도구를 이해하기 위해 이 지침은 섹션으로 구성됩니다.
 
![데이터 개인 정보 보호 규정에 대한 정보 보호를 구현하는 단계](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

이러한 각 섹션은 이 솔루션의 별도 문서에 해당합니다.

>[!Note]
>데이터 개인 정보 보호 의무에 이미 익숙하고 기존 요금제에 대해 실행되고 있는 경우 금지, 보호, 보존 및 조사 지침에 집중할 수 있습니다.

>[!Important]
>이 지침에 따라 반드시 데이터 개인 정보 보호 규정을 준수할 필요는 없습니다. 특히 기능의 컨텍스트 외부에 있는 필요한 단계의 수를 고려합니다. 귀하는 규정 준수를 보장하고 법률 및 규정 준수 팀에 문의하거나 규정 준수를 전문적으로 하는 타사의 지침과 조언을 구할 책임이 있습니다.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>계획: 데이터 개인 정보 보호 위험을 평가하고 중요한 항목 식별

조직에 적용될 데이터 개인 정보 규정 및 위험을 평가하는 것은 Microsoft 365 구성을 통해 달성할 수 있는 개선을 포함하여 개선을 구현하기 전에 먼저 취할 주요 첫 번째 단계입니다. 여기에는 조직에서 준수해야 하는 규정 제어가 적용된 특정 중요한 정보 유형의 전반적인 준비 평가 또는 식별과 Microsoft 365 환경에서 이러한 유형의 발생이 포함됩니다.

자세한 내용은 데이터 개인 정보 보호 위험 평가 및 [중요한 항목 식별을 참조하세요.](information-protection-deploy-assess.md)

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>추적: 위험 평가 실행 및 준수 점수 확인

Microsoft 365 규정 준수 센터에서 제공되는 준수 관리자는 사용자에게 적용되는 여러 데이터 개인 정보 보호 규정과 관련된 것뿐만 아니라 전반적인 개선 작업을 추적하고 관리할 수 있는 기본 제공 기능을 제공합니다.

선택한 각 평가 템플릿에 대한 작업 항목을 추적하고 특정 규제 컨트롤을 보고 특정 작업과 관련될 수 있는 각 규정과 관련된 기본 제공 평가 템플릿을 활용합니다.

자세한 내용은 준수 관리자를 사용하여 개선 [작업을 관리하세요.](information-protection-deploy-compliance.md)

## <a name="prevent-protect-personal-data"></a>방지: 개인 데이터 보호

Microsoft 365는 데이터 개인 정보 보호 규정 준수를 준수하는 데 사용할 수 있는 다양한 ID, 장치 및 위협 방지 기능을 제공합니다. 

자세한 내용은 데이터 개인 정보 보호 규정에 대한 ID, 장치 및 [위협 보호 사용을 참조하세요.](information-protection-deploy-identity-device-threat.md)

이 문서에서는 이러한 영역에서 데이터 개인 정보 규정이 일반적으로 요구하는 사항에 대해 간략하게 설명하고 관련 Microsoft 365 솔루션 목록을 제공합니다. 또한 구현 요구 사항을 충족하는 데 도움이 되는 추가 정보로 연결되는 링크를 제공합니다. 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>데이터 개인 정보 보호 규정을 준수하는 정보 보호

데이터 개인 정보 보호 규정은 GDPR, 캘리포니아 소비자 보호법(CCPA), HIPAA-HITECH(미국 의료 개인 정보 보호법) 및 브라질 데이터 보호법(LGPD)의 샘플 집합에 있는 4개의 데이터 개인 정보 보호 규정에 대한 4개 이상의 정보 보호 컨트롤을 포함하여 사용자 환경에 사용할 수 있는 다양한 개인 정보 보호 제어를 규정합니다.

자세한 내용은 조직의 데이터 개인 [정보 보호 규정을 준수하는 정보 보호를 참조하세요.](information-protection-deploy-protect-information.md)

이 문서에서는 조직의 데이터 개인 정보 보호에 대한 정보 보호 요구 사항을 해결하기 위해 사용할 수 있는 주요 제어 체계를 제공합니다.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>보존: 데이터 개인 정보 보호 규정이 적용된 정보 관리

데이터 개인 정보 규정은 GDPR, CCPA, HIPAA-HITECH 및 LGPD 샘플 집합의 네 가지 데이터 개인 정보 보호 규정에 대한 24개 이상의 컨트롤을 포함하여 사용자 환경에서 사용할 수 있는 개인 정보 거버넌스 제어를 요구합니다.

자세한 내용은 조직의 데이터 개인 [정보 보호 규정이 적용된 관리 정보를 참조하세요.](information-protection-deploy-govern.md)

데이터 개인 정보 보호 규정은 의도적인 보존과 같은 정보 거버넌스와 관련하여 모호할 수 있는 반면, 이 문서의 삭제 및 보관에서는 조직의 데이터 개인 정보 보호에 대한 주소 정보 거버넌스 요구 사항을 사용할 수 있는 기본 제어 체계를 세우고 &mdash; &mdash; 있습니다.

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>조사: 데이터 개인 정보 보호 인시던트 모니터링, 조사 및 대응

관련 기능을 작동할 때 조직의 데이터 개인 정보 인시던트 모니터링, 조사 및 대응에 도움이 되는 Microsoft 365 기능이 있습니다. 

이러한 각 기관에 대한 프로세스, 절차 및 기타 문서가 있는 것은 규제 기관의 규정 준수를 입증하는 데 중요할 수 있습니다.

자세한 내용은 조직의 데이터 개인 정보 인시던트 모니터링 및 [대응을 참조하세요.](information-protection-deploy-monitor-respond.md)
