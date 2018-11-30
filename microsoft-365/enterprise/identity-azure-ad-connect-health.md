---
title: '8단계: 동기화 상태 모니터링'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD Connect Health를 이해하고 구성합니다.
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870141"
---
# <a name="step-8-monitor-synchronization-health"></a><span data-ttu-id="fbb42-103">8단계: 동기화 상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="fbb42-103">Step 8: Monitor synchronization health</span></span>

<span data-ttu-id="fbb42-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="fbb42-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="fbb42-p101">이 단계에서는 각 온-프레미스 ID 서버에 Azure AD Connect Health 에이전트를 설치하여 Azure AD Connect에서 제공하는 ID 인프라 및 동기화 서비스를 모니터링합니다. 모니터링 정보는 Azure AD Connect Health 포털에서 제공되며, 여기에서 경고, 성능 모니터링, 사용 현황 분석 및 기타 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb42-p101">In Step 4, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect. The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Azure AD Connect Health의 구성 요소](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="fbb42-108">Azure AD Connect Health 사용 방법에 대한 주요 디자인 의사 결정은 Azure AD Connect 사용 방법을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb42-108">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="fbb42-109">**관리되는 인증** 옵션을 사용하는 경우 [동기화와 함께 Azure AD Connect Health 사용](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)을 시작하여 Azure AD Connect Health를 이해하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb42-109">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="fbb42-110">AD FS(Active Directory Federation Services)에서 **페더레이션 인증**을 사용하여 계정 및 그룹의 이름만 동기화하는 경우 [AD FS와 함께 Azure AD Connect Health 사용](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)을 시작하여 Azure AD Connect Health를 이해하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb42-110">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="fbb42-111">이 단계를 완료하면 다음과 같은 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb42-111">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="fbb42-112">온-프레미스 ID 서버에 Azure AD Connect Health 에이전트가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbb42-112">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="fbb42-113">Office 365 및 EMS 구독에 대한 Azure AD 테넌트와 함께 온-프레미스 인프라 및 동기화 활동의 현재 상태가 Azure AD Connect Health 포털에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbb42-113">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="fbb42-114">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-sync-health)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb42-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="fbb42-115">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fbb42-115">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="fbb42-116">암호 업데이트 간소화</span><span class="sxs-lookup"><span data-stu-id="fbb42-116">Simplify password updates</span></span>](identity-password-writeback.md) |

