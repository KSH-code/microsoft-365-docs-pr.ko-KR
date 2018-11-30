---
title: '13단계: 테넌트 및 로그인 활동 모니터링'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD 액세스 및 사용 현황 보고를 이해하고 구성합니다.
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869705"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="62980-103">13단계: 테넌트 및 로그인 활동 모니터링</span><span class="sxs-lookup"><span data-stu-id="62980-103">Step 13: Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="62980-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="62980-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="62980-p101">이 단계에서는 Azure AD 보고를 사용하여 감사 로그 및 로그인 활동을 검토합니다. 두 가지 유형의 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62980-p101">In Step 13, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="62980-p102">**감사 로그 활동 보고서**는 Azure AD 테넌트에서 수행된 모든 작업 내역을 기록합니다. 이 보고서는 다음과 같은 질문에 대한 답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="62980-p102">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="62980-109">관리자 그룹에 다른 사용자를 추가한 사람은 누구인가요?</span><span class="sxs-lookup"><span data-stu-id="62980-109">Who added someone to an admin group?</span></span>
- <span data-ttu-id="62980-110">특정 앱에 로그인 중인 사용자는 누구인가요?</span><span class="sxs-lookup"><span data-stu-id="62980-110">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="62980-111">발생한 암호 재설정 횟수는 몇 회인가요?</span><span class="sxs-lookup"><span data-stu-id="62980-111">How many password resets are happening?</span></span>

<span data-ttu-id="62980-p103">**로그인 활동 보고서**는 감사 로그 보고서에서 보고한 작업을 수행한 사람을 기록합니다. 이 보고서는 다음과 같은 질문에 대한 답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="62980-p103">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="62980-114">조사 중인 특정 사용자의 로그인 패턴은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="62980-114">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="62980-115">하루, 일주일 또는 한 달 동안 몇 번 로그인했나요?</span><span class="sxs-lookup"><span data-stu-id="62980-115">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="62980-116">이러한 로그인 시도에 실패한 횟수와 그 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="62980-116">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="62980-117">보고서 및 보고서 액세스 방법에 대한 자세한 내용은 [Azure Active Directory 보고](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62980-117">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="62980-118">이 단계를 마치면 이러한 보고서에 대해 알게 되고, 계획 및 보안을 위해 보고서를 사용하여 Azure AD 이벤트 및 활동에 대한 이해를 넓힐 수 있는 방법을 파악하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62980-118">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="62980-119">다음 단계</span><span class="sxs-lookup"><span data-stu-id="62980-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="62980-120">사용자가 자신의 그룹을 만들고 관리하도록 허용</span><span class="sxs-lookup"><span data-stu-id="62980-120">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
