---
title: SaaS 앱에 대한 권장 Microsoft Cloud App Security 정책 - Microsoft 365 Enterprise | Microsoft Docs
description: Microsoft Cloud App Security와의 통합을 위한 권장 정책에 대해 설명
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: Admin
ms.author: bcarter
ms.date: 03/22/2021
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: e9a52ca8cd46c0e9f590da7df94ee6d4c30289f4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071332"
---
# <a name="recommended-microsoft-cloud-app-security-policies-for-saas-apps"></a><span data-ttu-id="41c29-103">SaaS 앱에 대한 권장 Microsoft Cloud App Security 정책</span><span class="sxs-lookup"><span data-stu-id="41c29-103">Recommended Microsoft Cloud App Security policies for SaaS apps</span></span>
<span data-ttu-id="41c29-104">Microsoft Cloud App Security는 Azure AD 조건부 액세스 정책을 토대하여 다운로드, 업로드, 복사 및 붙여넣기, 인쇄 차단과 같은 SaaS 앱을 사용하여 세부적인 작업을 실시간으로 모니터링하고 제어할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-104">Microsoft Cloud App Security builds on Azure AD conditional access policies to enable real-time monitoring and control of granular actions with SaaS apps, such as blocking downloads, uploads, copy and paste, and printing.</span></span> <span data-ttu-id="41c29-105">이 기능은 관리되지 않는 장치나 게스트 사용자가 회사 리소스에 액세스하는 경우와 같이 내재된 위험을 수반하는 세션에 보안을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-105">This feature adds security to sessions that carry inherent risk, such as when corporate resources are accessed from unmanaged devices or by guest users.</span></span> 

<span data-ttu-id="41c29-106">또한 Microsoft Cloud App Security는 Microsoft Information Protection과 기본적으로 통합되어 중요한 정보 유형 및 민감도 레이블을 기반으로 중요한 데이터를 찾고 적절한 조치를 취하기 위해 실시간 콘텐츠 검사를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-106">Microsoft Cloud App Security also integrates natively with Microsoft Information Protection, providing real-time content inspection to find sensitive data based on sensitive information types and sensitivity labels and to take appropriate action.</span></span> 

<span data-ttu-id="41c29-107">이 지침에는 다음 시나리오에 대한 권장 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-107">This guidance includes recommendations for these scenarios:</span></span>
- <span data-ttu-id="41c29-108">IT 관리에 SaaS 앱 가져오기</span><span class="sxs-lookup"><span data-stu-id="41c29-108">Bring SaaS apps into IT management</span></span>
- <span data-ttu-id="41c29-109">특정 SaaS 앱에 대한 보호 조정</span><span class="sxs-lookup"><span data-stu-id="41c29-109">Tune protection for specific SaaS apps</span></span>
- <span data-ttu-id="41c29-110">데이터 보호 규정을 준수하도록 DLP(데이터 손실 방지) 구성</span><span class="sxs-lookup"><span data-stu-id="41c29-110">Configure data loss prevention (DLP) to help comply with data protection regulations</span></span>

## <a name="bring-saas-apps-into-it-management"></a><span data-ttu-id="41c29-111">IT 관리에 SaaS 앱 가져오기</span><span class="sxs-lookup"><span data-stu-id="41c29-111">Bring SaaS apps into IT management</span></span>

<span data-ttu-id="41c29-112">Microsoft Cloud App Security를 사용하여 SaaS 앱을 관리하는 첫 번째 단계는 이러한 앱을 검색한 다음 Azure AD 테넌트에 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-112">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="41c29-113">검색에 도움이 필요한 경우 [네트워크에서 SaaS 앱](https://docs.microsoft.com/cloud-app-security/tutorial-shadow-it)검색 및 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41c29-113">If you need help with discovery, see [Discover and manage SaaS apps in your network](https://docs.microsoft.com/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="41c29-114">앱을 검색한 후 Azure AD 테넌트에 [추가합니다.](https://docs.microsoft.com/azure/active-directory/manage-apps/add-application-portal)</span><span class="sxs-lookup"><span data-stu-id="41c29-114">After you've discovered apps, [add these to your Azure AD tenant](https://docs.microsoft.com/azure/active-directory/manage-apps/add-application-portal).</span></span>  

<span data-ttu-id="41c29-115">다음을 수행하여 이러한 관리 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-115">You can begin to manage these by doing the following:</span></span>
1. <span data-ttu-id="41c29-116">먼저 Azure AD에서 새 조건부 액세스 정책을 만들고 "조건부 액세스 앱 제어 사용"으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-116">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="41c29-117">그러면 요청을 Cloud App Security로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-117">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="41c29-118">하나의 정책을 만들고 모든 SaaS 앱을 이 정책에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-118">You can create one policy and add all SaaS apps to this policy.</span></span>
1. <span data-ttu-id="41c29-119">다음으로 Cloud App Security에서 세션 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-119">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="41c29-120">적용할 각 컨트롤에 대해 정책을 하나씩 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-120">Create one policy for each control you want to apply.</span></span> 

<span data-ttu-id="41c29-121">SaaS 앱에 대한 사용 권한은 일반적으로 앱에 대한 액세스에 대한 비즈니스 필요성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-121">Permissions to SaaS apps are typically based on business need for access to the app.</span></span> <span data-ttu-id="41c29-122">이러한 권한은 매우 동적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-122">These permissions can be highly dynamic.</span></span> <span data-ttu-id="41c29-123">Cloud App Security 정책을 사용하면 사용자가 기준, 중요 또는 높은 규제 대상 보호와 연결된 Azure AD 그룹에 할당되어 있는지 여부에 관계없이 앱 데이터를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-123">Using Cloud App Security policies ensures protection to app data, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="41c29-124">SaaS 앱 컬렉션 전체에서 데이터를 보호하기 위해 다음 다이어그램에서는 필요한 Azure AD 조건부 액세스 정책과 Cloud App Security에서 만들 수 있는 제안된 정책을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-124">To protect data across your collection of SaaS apps, the following diagram illustrates the necessary Azure AD conditional access policy plus suggested policies you can create in Cloud App Security.</span></span> <span data-ttu-id="41c29-125">이 예제에서는 Cloud App Security에서 만든 정책이 관리되는 모든 SaaS 앱에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-125">In this example, the policies created in Cloud App Security apply to all SaaS apps you are managing.</span></span> <span data-ttu-id="41c29-126">이러한 컨트롤은 장치에 관리되는지 여부와 파일에 이미 적용된 민감도 레이블에 따라 적절한 컨트롤을 적용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-126">These are designed to apply appropriate controls based on whether devices are managed as well as sensitivity labels that are already applied to files.</span></span> 

<br>

![Cloud App Security에서 SaaS 앱 관리 정책](../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png)

<span data-ttu-id="41c29-128">다음 표에는 Azure AD에서 만들어야 하는 새 조건부 액세스 정책이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-128">The following table lists the new conditional access policy you must create in Azure AD.</span></span>

|<span data-ttu-id="41c29-129">보호 수준</span><span class="sxs-lookup"><span data-stu-id="41c29-129">Protection level</span></span>|<span data-ttu-id="41c29-130">정책</span><span class="sxs-lookup"><span data-stu-id="41c29-130">Policy</span></span>|<span data-ttu-id="41c29-131">추가 정보</span><span class="sxs-lookup"><span data-stu-id="41c29-131">More information</span></span>|
|---|---|---|
|<span data-ttu-id="41c29-132">모든 보호 수준</span><span class="sxs-lookup"><span data-stu-id="41c29-132">All protection levels</span></span> | [<span data-ttu-id="41c29-133">Cloud App Security에서 조건부 액세스 앱 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="41c29-133">Use Conditional Access App Control in Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad) |<span data-ttu-id="41c29-134">그러면 Azure AD(IdP)가 Cloud App Security와 함께 작동하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-134">This configures your IdP (Azure AD) to work with Cloud App Security.</span></span> |

<span data-ttu-id="41c29-135">다음 표에는 위에 설명된 예제 정책이 나열되어 있습니다. 모든 SaaS 앱을 보호하기 위해 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-135">This next table lists the example policies illustrated above that you can create to protect all SaaS apps.</span></span> <span data-ttu-id="41c29-136">자체 비즈니스, 보안 및 규정 준수 목표를 평가한 다음 환경에 가장 적합한 보호를 제공하는 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-136">Be sure to evaluate your own business, security, and compliance objectives and then create policies that provide the most appropriate protection for your environment.</span></span> 

|<span data-ttu-id="41c29-137">보호 수준</span><span class="sxs-lookup"><span data-stu-id="41c29-137">Protection level</span></span>|<span data-ttu-id="41c29-138">정책</span><span class="sxs-lookup"><span data-stu-id="41c29-138">Policy</span></span>|
|---|---|
|<span data-ttu-id="41c29-139">기준</span><span class="sxs-lookup"><span data-stu-id="41c29-139">Baseline</span></span> | <span data-ttu-id="41c29-140">관리되지 않는 장치의 트래픽 모니터링</span><span class="sxs-lookup"><span data-stu-id="41c29-140">Monitor traffic from unmanaged devices</span></span><br><br><span data-ttu-id="41c29-141">관리되지 않는 장치에서 파일 다운로드에 보호 추가</span><span class="sxs-lookup"><span data-stu-id="41c29-141">Add protection to file downloads from unmanaged devices</span></span> | 
|<span data-ttu-id="41c29-142">중요</span><span class="sxs-lookup"><span data-stu-id="41c29-142">Sensitive</span></span>  | <span data-ttu-id="41c29-143">중요하거나 관리되지 않는 장치에서 분류된 파일 다운로드 차단(브라우저 전용 액세스 제공)</span><span class="sxs-lookup"><span data-stu-id="41c29-143">Block download of files labeled with sensitive or classified from unmanaged devices (this provides browser only access)</span></span>  | 
| <span data-ttu-id="41c29-144">매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="41c29-144">Highly regulated</span></span> | <span data-ttu-id="41c29-145">모든 장치에서 분류된 레이블이 붙은 파일 다운로드 차단(브라우저 전용 액세스 제공)</span><span class="sxs-lookup"><span data-stu-id="41c29-145">Block download of files labeled with classified from all devices (this provides browser only access)</span></span>  |   
|  |   |  

<span data-ttu-id="41c29-146">조건부 액세스 앱 컨트롤을 설정하는 전체 지침은 추천 앱에 대한 조건부 [액세스 앱 컨트롤 배포를 참조하세요.](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)</span><span class="sxs-lookup"><span data-stu-id="41c29-146">For end-to-end instructions for setting up Conditional Access App Control, see [Deploy Conditional Access App Control for featured apps](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad).</span></span> <span data-ttu-id="41c29-147">이 문서에서는 Azure AD에서 필요한 조건부 액세스 정책을 만들고 SaaS 앱을 테스트하는 프로세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-147">This article walks you through the process of creating the necessary conditional access policy in Azure AD and testing your SaaS apps.</span></span>




<span data-ttu-id="41c29-148">자세한 내용은 Microsoft Cloud App Security 조건부 액세스 앱 제어로 앱 [보호를 참조하세요.](https://docs.microsoft.com/cloud-app-security/proxy-intro-aad)</span><span class="sxs-lookup"><span data-stu-id="41c29-148">For more information, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](https://docs.microsoft.com/cloud-app-security/proxy-intro-aad).</span></span> 


## <a name="tune-protection-for-specific-saas-apps"></a><span data-ttu-id="41c29-149">특정 SaaS 앱에 대한 보호 조정</span><span class="sxs-lookup"><span data-stu-id="41c29-149">Tune protection for specific SaaS apps</span></span>
<span data-ttu-id="41c29-150">환경의 특정 SaaS 앱에 추가 모니터링 및 컨트롤을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-150">You might want to apply additional monitoring and controls to specific SaaS apps in your environment.</span></span> <span data-ttu-id="41c29-151">Cloud App Security를 사용하면 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-151">Cloud App Security allows you to accomplish this.</span></span> <span data-ttu-id="41c29-152">예를 들어 Box와 같은 앱이 환경에서 많이 사용되는 경우 추가 컨트롤을 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-152">For example, if an app like Box is used heavily in your environment, it makes sense to apply additional controls.</span></span> <span data-ttu-id="41c29-153">또는 법무 또는 재무 부서에서 중요한 비즈니스 데이터에 대해 특정 SaaS 앱을 사용하는 경우 이러한 앱에 대한 추가 보호를 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-153">Or, if your legal or finance department is using a specific SaaS app for sensitive business data, you can target extra protection to these apps.</span></span> 

<span data-ttu-id="41c29-154">예를 들어 다음과 같은 유형의 기본 제공 이상 검색 정책 템플릿으로 Box 환경을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-154">For example, you can protect your Box environment with these types of built-in anomaly detection policy templates:</span></span>
- <span data-ttu-id="41c29-155">익명 IP 주소의 활동</span><span class="sxs-lookup"><span data-stu-id="41c29-155">Activity from anonymous IP addresses</span></span>
- <span data-ttu-id="41c29-156">비어 있는 국가의 활동</span><span class="sxs-lookup"><span data-stu-id="41c29-156">Activity from infrequent country</span></span>
- <span data-ttu-id="41c29-157">의심스러운 IP 주소의 활동</span><span class="sxs-lookup"><span data-stu-id="41c29-157">Activity from suspicious IP addresses</span></span>
- <span data-ttu-id="41c29-158">불가능한 이동</span><span class="sxs-lookup"><span data-stu-id="41c29-158">Impossible travel</span></span>
- <span data-ttu-id="41c29-159">종료된 사용자가 수행한 활동(IdP로 AAD 필요)</span><span class="sxs-lookup"><span data-stu-id="41c29-159">Activity performed by terminated user (requires AAD as IdP)</span></span>
- <span data-ttu-id="41c29-160">맬웨어 검색</span><span class="sxs-lookup"><span data-stu-id="41c29-160">Malware detection</span></span>
- <span data-ttu-id="41c29-161">로그인 시도가 여러 번 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-161">Multiple failed login attempts</span></span>
- <span data-ttu-id="41c29-162">랜섬웨어 활동</span><span class="sxs-lookup"><span data-stu-id="41c29-162">Ransomware activity</span></span>
- <span data-ttu-id="41c29-163">위험한 Oauth 앱</span><span class="sxs-lookup"><span data-stu-id="41c29-163">Risky Oauth App</span></span>
- <span data-ttu-id="41c29-164">비정상적인 파일 공유 활동</span><span class="sxs-lookup"><span data-stu-id="41c29-164">Unusual file share activity</span></span>

<span data-ttu-id="41c29-165">이러한 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-165">These are examples.</span></span> <span data-ttu-id="41c29-166">추가 정책 템플릿은 정기적으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-166">Additional policy templates are added on a regular basis.</span></span> <span data-ttu-id="41c29-167">특정 앱에 추가 보호를 적용하는 방법에 대한 예제는 연결된 앱 [보호를 참조하세요.](https://docs.microsoft.com/cloud-app-security/protect-connected-apps)</span><span class="sxs-lookup"><span data-stu-id="41c29-167">For examples of how to apply additional protection to specific apps, see [Protecting connected apps](https://docs.microsoft.com/cloud-app-security/protect-connected-apps).</span></span> 

<span data-ttu-id="41c29-168">[Cloud App Security가 Box](https://docs.microsoft.com/cloud-app-security/protect-box) 환경을 보호하는 방법 Box 및 기타 앱에서 중요한 데이터를 사용하여 비즈니스 데이터를 보호하는 데 도움이 되는 컨트롤 유형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-168">[How Cloud App Security helps protect your Box environment](https://docs.microsoft.com/cloud-app-security/protect-box) demonstrates the types of controls that can help you protect your business data in Box and other apps with sensitive data.</span></span>


## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a><span data-ttu-id="41c29-169">데이터 보호 규정을 준수하도록 DLP(데이터 손실 방지) 구성</span><span class="sxs-lookup"><span data-stu-id="41c29-169">Configure data loss prevention (DLP) to help comply with data protection regulations</span></span>

<span data-ttu-id="41c29-170">Cloud App Security는 규정 준수 규정에 대한 보호를 구성하는 데 유용한 도구가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-170">Cloud App Security can be a valuable tool for configuring protection for compliance regulations.</span></span> <span data-ttu-id="41c29-171">이 경우 규정이 적용되는 특정 데이터를 찾아 적절한 조치를 취하도록 각 정책을 구성하는 특정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-171">In this case, you create specific policies to look for specific data that a regulation applies to and configure each policy to take appropriate action.</span></span> 

<span data-ttu-id="41c29-172">다음 그림과 표에서는 GDPR(일반 데이터 보호 규정)을 준수하도록 구성할 수 있는 정책의 몇 가지 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-172">The following illustration and table provide several examples of policies that can be configured to help comply with  the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="41c29-173">이러한 예에서 정책은 특정 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-173">In these examples, policies look for specific data.</span></span> <span data-ttu-id="41c29-174">데이터의 민감도에 따라 각 정책은 적절한 조치를 취하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="41c29-174">Based on the sensitivity of the data, each policy is configured to take appropriate action.</span></span> 

![데이터 손실 방지를 위한 Cloud App Security 정책 예제](../../media/microsoft-365-policies-configurations/mcas-dlp.png)

|<span data-ttu-id="41c29-176">보호 수준</span><span class="sxs-lookup"><span data-stu-id="41c29-176">Protection level</span></span>|<span data-ttu-id="41c29-177">정책 예</span><span class="sxs-lookup"><span data-stu-id="41c29-177">Example policies</span></span>|
|:---------------|:-------|
| <span data-ttu-id="41c29-178">기준</span><span class="sxs-lookup"><span data-stu-id="41c29-178">Baseline</span></span> |<span data-ttu-id="41c29-179">이 중요한 정보 유형("신용 카드 번호")이 포함된 파일이 조직 외부에서 공유되는 경우 경고</span><span class="sxs-lookup"><span data-stu-id="41c29-179">Alert when files containing this sensitive information type ("Credit Card Number") are shared outside the organization</span></span> <br><br><span data-ttu-id="41c29-180">이 중요한 정보 유형("신용 카드 번호")을 포함하는 파일의 관리되지 않는 장치에 대한 다운로드 차단</span><span class="sxs-lookup"><span data-stu-id="41c29-180">Block downloads of files containing this sensitive information type (”Credit card number") to unmanaged devices</span></span>|
| <span data-ttu-id="41c29-181">중요</span><span class="sxs-lookup"><span data-stu-id="41c29-181">Sensitive</span></span>  | <span data-ttu-id="41c29-182">관리되는 장치에 이 중요한 정보 유형("신용 카드 번호")이 포함된 파일의 다운로드 보호</span><span class="sxs-lookup"><span data-stu-id="41c29-182">Protect downloads of files containing this sensitive information type ("Credit card number") to managed devices</span></span> <br><br><span data-ttu-id="41c29-183">이 중요한 정보 유형("신용 카드 번호")을 포함하는 파일의 관리되지 않는 장치에 대한 다운로드 차단</span><span class="sxs-lookup"><span data-stu-id="41c29-183">Block downloads of files containing this sensitive information type ("Credit card number") to unmanaged devices</span></span> <br><br><span data-ttu-id="41c29-184">이러한 레이블이 있는 파일이 비즈니스용 OneDrive 또는 Box에 업로드될 때 경고(고객 데이터, 인사: 급여 데이터, 인사, 직원 데이터)</span><span class="sxs-lookup"><span data-stu-id="41c29-184">Alert when a file with on of these labels is uploaded to OneDrive for Business or Box (Customer data, Human Resources: Salary Data,Human Resources, Employee data)</span></span>|
| <span data-ttu-id="41c29-185">매우 엄격한 규제</span><span class="sxs-lookup"><span data-stu-id="41c29-185">Highly regulated</span></span> |<span data-ttu-id="41c29-186">이 레이블이 있는 파일("높은 분류")이 관리 장치에 다운로드될 때 경고</span><span class="sxs-lookup"><span data-stu-id="41c29-186">Alert when files with this label ("Highly classified") are downloaded to managed devices</span></span> <p><span data-ttu-id="41c29-187">이 레이블을 통해 관리되지 않는 장치에 대한 파일 다운로드 차단("높은 분류")</span><span class="sxs-lookup"><span data-stu-id="41c29-187">Block downloads of files with this label ("Highly classified") to unmanaged devices</span></span> |
| | |



## <a name="next-steps"></a><span data-ttu-id="41c29-188">다음 단계</span><span class="sxs-lookup"><span data-stu-id="41c29-188">Next steps</span></span>

<span data-ttu-id="41c29-189">Cloud App Security 사용에 대한 자세한 내용은 [Microsoft Cloud App Security 설명서를 참조하세요.](https://docs.microsoft.com//cloud-app-security/)</span><span class="sxs-lookup"><span data-stu-id="41c29-189">For more information about using Cloud App Security, see [Microsoft Cloud App Security documentation](https://docs.microsoft.com//cloud-app-security/).</span></span> 