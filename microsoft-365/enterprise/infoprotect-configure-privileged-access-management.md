---
title: '7 단계: 권한이 부여 된 액세스 관리 구성'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: 권한이 부여 된 액세스 관리를 이해 하 고 구성 합니다.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636991"
---
# <a name="step-7-configure-privileged-access-management"></a><span data-ttu-id="63d5d-103">7 단계: 권한이 부여 된 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="63d5d-103">Step 7: Configure privileged access management</span></span>

<span data-ttu-id="63d5d-104">*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 및 Advanced Compliance 버전에만 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="63d5d-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![6단계: 정보 보호](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="63d5d-106">권한 있는 액세스 관리는 테 넌 트에서 작업 기반 작업에 대 한 just-in-time 액세스를 지정 하는 정책을 구성 하 여 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63d5d-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant.</span></span> <span data-ttu-id="63d5d-107">중요 한 데이터에 대 한 액세스 권한이 있거나 중요 한 구성 설정에 대 한 액세스 권한이 있는 기존 권한 있는 관리자 계정을 사용 하는 조직을 보호 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63d5d-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="63d5d-108">예를 들어 테 넌 트에서 조직 사서함 설정에 액세스 하 고 변경 하기 위해 명시적 승인이 필요한 권한이 부여 된 액세스 관리 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63d5d-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="63d5d-109">이 단계에서는 테 넌 트에서 권한이 부여 된 액세스 관리를 사용 하도록 설정 하 고 조직에 대 한 데이터 및 구성 설정에 대 한 작업 기반 액세스에 대 한 추가 보안을 제공 하는 권한 있는 액세스 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="63d5d-109">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization.</span></span> <span data-ttu-id="63d5d-110">조직에서 권한이 부여 된 액세스를 시작 하려면 다음 세 가지 기본 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63d5d-110">There are three basic steps to get started with privileged access in your organization:</span></span>
- <span data-ttu-id="63d5d-111">승인자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="63d5d-111">Creating an approver's group</span></span>
- <span data-ttu-id="63d5d-112">권한 있는 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="63d5d-112">Enabling privileged access</span></span>
- <span data-ttu-id="63d5d-113">승인 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="63d5d-113">Creating approval policies</span></span>

<span data-ttu-id="63d5d-p103">일단 구성되고 나면, 권한이 부여된 액세스 관리는 대기 없는 관리 액세스 권한 때문에 조직이 대기 없는 권한으로 작업하고, 발생하는 취약성에 대한 보안 계층을 제공할 수 있도록 합니다. 권한이 부여된 액세스의 경우 연결된 승인 정책이 정의된 작업을 실행하려면 승인이 필요합니다. 승인 정책에 포함된 작업을 실행해야 하는 사용자는 정책에 정의된 작업을 실행하는 데 필요한 권한을 얻기 위해 액세스 승인을 요청하고 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63d5d-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="63d5d-117">권한이 부여 된 액세스 관리를 사용 하도록 설정 하려면 [Configure permissions access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="63d5d-117">To enable privileged access management, see the [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="63d5d-118">자세한 내용은 [권한이 부여 된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="63d5d-118">For more information, see the [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="63d5d-120">테스트 랩 환경에서 이 구성을 연습하려면 [권한이 부여된 액세스 관리 테스트 랩 가이드](privileged-access-microsoft-365-enterprise-dev-test-environment.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63d5d-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="63d5d-121">중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step7)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="63d5d-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="63d5d-122">다음 단계</span><span class="sxs-lookup"><span data-stu-id="63d5d-122">Next Step</span></span>

[<span data-ttu-id="63d5d-123">정보 보호 인프라 종료 조건</span><span class="sxs-lookup"><span data-stu-id="63d5d-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
