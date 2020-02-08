---
title: 민감도 레이블을 콘텐츠에 자동으로 적용
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: 12/13/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: 민감도 레이블을 만들 때 문서 또는 전자 메일에 레이블을 자동으로 할당하거나 사용자에게 권장 레이블을 선택하라는 메시지를 표시할 수 있습니다.
ms.openlocfilehash: ff4a236a56fc2e8259204e7a0202d67176d44964
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596055"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>민감도 레이블을 콘텐츠에 자동으로 적용

민감도 레이블을 만들 때 민감한 정보가 포함된 콘텐츠에 해당 레이블을 자동으로 할당하거나 사용자에게 권장 레이블을 적용하라는 메시지를 표시할 수 있습니다.

콘텐츠에 자동으로 민감도 레이블을 적용하는 기능도 다음과 같은 이유로 중요합니다.

- 사용자에게 모든 분류를 교육할 필요가 없습니다.

- 모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.

- 사용자가 더 이상 정책을 알아야 할 필요가 없으며, 그 대신 업무에 집중할 수 있습니다.

라이선스 요구 사항에 대 한 자세한 내용은 [민감도 레이블에 대한 구독 및 라이선스 요구 사항](sensitivity-labels-office-apps.md#subscription-and-licensing-requirements-for-sensitivity-labels)을 참조하세요.

자동 라벨링 설정은 **분류** > **민감도 레이블**에 준하여 Microsoft 365 규정 준수 센터, Microsoft 365 보안 센터 또는 Office 365 보안 및 규정 준수 센터에서 민감도 레이블을 만들 때 사용할 수 있습니다.

![민감도 레이블에 대한 자동 레이블 지정 옵션](media/Sensitivity-labels-Auto-labeling-options.png)

## <a name="apply-a-sensitivity-label-automatically-based-on-conditions"></a>조건에 따라 자동으로 민감도 레이블 적용

민감도 레이블의 가장 강력한 기능 중 하나는 특정 조건과 일치하는 콘텐츠에 자동으로 레이블을 적용하는 기능입니다. 이 경우 조직의 사용자는 민감도 레이블을 적용할 필요가 없습니다. Office 365에서 이 작업을 수행합니다.

특정 종류 민감 정보가 포함된 콘텐츠에 대해 민감도 레이블을 자동으로 적용하도록 선택할 수 있습니다. 민감도 레이블을 자동으로 적용하도록 구성하면 DLP(데이터 손실 방지) 정책을 만들 때처럼 민감 정보 유형 목록이 나타납니다. 예를 들어 신용 카드 번호나 주민등록번호와 같이 고객의 개인 식별 정보(PII)가 포함된 모든 컨텐츠에 고기밀 레이블을 자동으로 적용할 수 있습니다.

![인스턴스 개수 및 일치 정확도 옵션](media/Sensitivity-labels-instance-count-match-accuracy.png)

민감 정보 유형을 선택하면 인스턴스 수 또는 일치 정확도를 변경하여 조건을 구체화 할 수 있습니다. 자세한 내용은 [규칙을 조정하여 더욱 쉽게 또는 더욱 일치하기 어렵게 하기](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)를 참조하세요.

또한 조건이 모든 민감 정보 유형을 감지해야 하는지 또는 한 가지 유형만 감지하면 되는지를 선택할 수 있습니다. 조건을 더 유연하게 만들거나 복잡하게 만들려면 그룹을 추가하고 그룹 간에 논리 연산자를 사용할 수 있습니다. 자세한 내용은 [그룹화 및 논리 연산자](data-loss-prevention-policies.md#grouping-and-logical-operators)를 참조하세요.

민감도 레이블이 자동으로 적용되면 사용자는 Office 앱에서 알림을 보게 됩니다. ** OK **를 선택하여 알림을 닫을 수 있습니다.

![문서에 레이블이 자동 적용되었다는 알림](media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a>사용자가 민감도 레이블을 적용할 것을 권장합니다

원하는 경우 사용자에게 레이블을 적용할 것을 권장할 수 있습니다. 이 옵션을 사용하면 사용자가 분류 및 관련 보호를 수락하거나, 레이블이 문서 또는 전자 메일에 적합하지 않은 경우에는 권장 사항을 취소할 수 있습니다.

권장 레이블은 Word, PowerPoint 및 Excel에서 지원됩니다(또한 Azure Information Proteciton 통합 레이블 클라이언트가 설치되어 있어야 합니다).

![사용자에게 민감도 레이블 권장 옵션](media/Sensitivity-labels-Recommended-label-option.png)

다음은 사용자 지정 정책 팁을 사용하여 레이블을 맞춤 정책 팁과 함께 권장 작업으로 적용하도록 조건을 구성 할때 프롬프트가 표시되는 예입니다. 정책 팁에 표시될 텍스트를 선택할 수 있습니다.

![권장된 레이블을 적용하라는 메시지 표시](media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a>자동 또는 권장 레이블이 적용되는 방식

- 자동 레이블은 문서를 저장할 때는 Word, Excel 및 PowerPoint에 적용되고, 전자 메일을 보낼 때는 Outlook에 적용됩니다. 이러한 조건은 문서 및 전자 메일의 본문 텍스트와 머리글 및 바닥글에서 중요한 정보를 검색하지만, 전자 메일의 제목 줄이나 첨부 파일에서는 중요한 정보를 검색하지 않습니다.

- 이전에 수동으로 레이블을 지정했거나, 이전에 더 높은 분류로 레이블이 자동으로 지정된 문서 및 전자 메일에는 자동 분류를 사용할 수 없습니다. 문서 또는 전자 메일에는 단일 보존 레이블 외에 단일 민감도 레이블만 적용할 수 있습니다.

- 권장된 분류는 문서를 저장할 때는 Word, Excel 및 PowerPoint에 적용됩니다.

- 이전에 더 높은 분류로 레이블이 지정된 문서에는 권장 분류를 사용할 수 없습니다. 콘텐츠에 더 높은 분류로 레이블이 지정되면 사용자에게 권장 사항 및 정책 팁이 포함된 프롬프트가 표시되지 않습니다.

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>두 개 이상 레이블에 적용했을 때 여러 조건의 평가 방식

레이블은 정책에서 지정한 위치에 따라 평가되도록 정렬됩니다. 먼저 배치된 레이블은 가장 낮은 위치에 있고(가장 민감하지 않음) 마지막에 위치한 레이블은 가장 높은 위치에 배치됩니다(가장 민감합니다). 우선 순위에 대한 자세한 내용은 [레이블 우선 순위 (순서 관련 문제)](sensitivity-labels.md#label-priority-order-matters)를 참조하십시오.

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>상위 레이블이 자동으로 적용되거나 권장되도록 구성하지 않음

상위 레이블(하위 레이블이 있는 레이블)은 콘텐츠에 적용할 수 없습니다. 상위 레이블은 Azure Information Protection 통합 레이블 지정 클라이언트를 사용하는 Office 앱에서 콘텐츠에 적용되지 않으므로 상위 레이블이 자동으로 적용되거나 권장되도록 구성하지 않도록 합니다. 상위 레이블 및 하위 레이블에 대한 자세한 내용은 [하위 레이블(레이블 그룹화)](sensitivity-labels.md#sublabels-grouping-labels)을 참조하세요.
