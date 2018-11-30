---
title: '4단계: 암호 재설정 간소화'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD에 대한 SSPR(셀프 서비스 암호 재설정)을 이해하고 구성합니다.
ms.openlocfilehash: fa946ca6da8a6c45caaf12be9dd1b79550e39bb6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870204"
---
# <a name="step-4-simplify-password-resets"></a><span data-ttu-id="f44a3-103">4단계: 암호 재설정 간소화</span><span class="sxs-lookup"><span data-stu-id="f44a3-103">Step 4: Simplify password resets</span></span>

<span data-ttu-id="f44a3-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="f44a3-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="f44a3-p101">이 단계에서는 사용자가 암호 또는 계정을 다시 설정하거나 잠금을 해제할 수 있도록 하기 위해 SSPR(셀프 서비스 암호 재설정)을 사용하도록 설정합니다. 오용이나 남용에 대한 경고를 생성하려면 알림과 함께 사용자가 시스템에 액세스한 시간을 추적하는 상세 보고를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f44a3-p101">In Step 10, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts. To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span>

<span data-ttu-id="f44a3-107">[암호 재설정을 사용하도록 설정하는 방법에 대한 지침](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-best-practices)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f44a3-107">See the [instructions to enable password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-best-practices).</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="f44a3-109">테스트 랩 가이드: 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="f44a3-109">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||


<span data-ttu-id="f44a3-110">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pw-reset)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f44a3-110">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f44a3-111">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f44a3-111">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="f44a3-112">다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="f44a3-112">Set up multi-factor authentication</span></span>](identity-multi-factor-authentication.md) |


