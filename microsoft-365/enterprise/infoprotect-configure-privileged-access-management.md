---
title: '6 단계: Office 365에 대 한 권한이 부여 된 액세스 관리 구성'
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Office 365에 대한 권한이 부여된 액세스 관리를 이해하고 구성합니다.
ms.openlocfilehash: 60b52825ead068cd0f068f78c1bbce263e8d7720
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33399952"
---
# <a name="step-6-configure-privileged-access-management-for-office-365"></a><span data-ttu-id="c7c4a-103">6 단계: Office 365에 대 한 권한이 부여 된 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="c7c4a-103">Step 6: Configure privileged access management for Office 365</span></span>

<span data-ttu-id="c7c4a-104">*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 및 Advanced Compliance 버전에만 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="c7c4a-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="c7c4a-p101">권한이 부여된 액세스 관리는 Office 365 테넌트의 태스크 기반 활동에 대해 JIT(Just-In-Time) 액세스를 지정하는 정책을 구성하여 적용됩니다. 이 기능은 중요한 데이터에 대한 대기 없는 액세스 권한 또는 중요한 구성 설정에 대한 액세스 권한이 부여된 기존 관리자 계정을 사용할 수 있는 보안 위반으로부터 조직을 보호하는 데 도움이 될 수 있습니다. 예를 들어, Office 365 테넌트의 조직 사서함 설정을 액세스 및 변경하기 위해 명시적 승인을 요구하는 권한이 부여된 액세스 관리 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c4a-p101">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="c7c4a-p102">이 단계에서는 Office 365 테넌트에서 액세스 권한이 부여된 액세스 관리를 사용하도록 설정하고, 조직의 Office 365 데이터 및 구성 설정에 대한 태스크 기반 액세스에 대해 추가 보안을 제공하는 권한이 부여된 액세스 정책을 구성합니다. Office 365 조직에서 권한이 부여된 액세스로 시작하려면 다음과 같은 3가지 기본 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c4a-p102">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>
- <span data-ttu-id="c7c4a-110">승인자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="c7c4a-110">Creating an approver's group</span></span>
- <span data-ttu-id="c7c4a-111">권한 있는 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="c7c4a-111">Enabling privileged access</span></span>
- <span data-ttu-id="c7c4a-112">승인 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c7c4a-112">Creating approval policies</span></span>

<span data-ttu-id="c7c4a-p103">일단 구성되고 나면, 권한이 부여된 액세스 관리는 대기 없는 관리 액세스 권한 때문에 조직이 대기 없는 권한으로 작업하고, 발생하는 취약성에 대한 보안 계층을 제공할 수 있도록 합니다. 권한이 부여된 액세스의 경우 연결된 승인 정책이 정의된 작업을 실행하려면 승인이 필요합니다. 승인 정책에 포함된 작업을 실행해야 하는 사용자는 정책에 정의된 작업을 실행하는 데 필요한 권한을 얻기 위해 액세스 승인을 요청하고 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c4a-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="c7c4a-116">Office 365 권한이 부여된 액세스 관리를 사용하도록 설정하려면 [Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7c4a-116">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="c7c4a-117">자세한 내용은 [Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7c4a-117">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>

## <a name="results"></a><span data-ttu-id="c7c4a-118">결과</span><span class="sxs-lookup"><span data-stu-id="c7c4a-118">Results</span></span>

<span data-ttu-id="c7c4a-119">이 단계에서는 조직의 핵심 데이터 및 구성 설정에 대해 JIT(Just-In-Time) 액세스 제어를 사용하도록 설정하여 Office 365의 보안이 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c4a-119">The result of this step is that you've increased the security of Office 365 by enabling just-in-time access control for key data and configuration settings for your organization.</span></span>

<span data-ttu-id="c7c4a-120">중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step6)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c7c4a-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c7c4a-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c7c4a-121">Next Step</span></span>

[<span data-ttu-id="c7c4a-122">정보 보호 인프라 종료 조건</span><span class="sxs-lookup"><span data-stu-id="c7c4a-122">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)