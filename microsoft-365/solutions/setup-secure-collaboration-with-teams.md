---
title: Microsoft 365를 사용하여 안전한 공동 작업 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Teams에서 보안 콘텐츠 공동 작업을 설정하여 민감도에 따라 데이터를 보호하는 방법을 알아보겠습니다.
ms.openlocfilehash: f65657125fef8b8cf7e4e229d70d8fe211153392
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613587"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a><span data-ttu-id="37e5b-103">Microsoft 365를 사용하여 안전한 공동 작업 설정</span><span class="sxs-lookup"><span data-stu-id="37e5b-103">Set up secure collaboration with Microsoft 365</span></span>

<span data-ttu-id="37e5b-104">조직에서 과도하게 공유하는 것을 방지하면서 올바른 사용자와 정보를 쉽게 공유할 수 있는 것이 조직의 성공에 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-104">Being able to easily share information with the right people while preventing oversharing is key to an organization's success.</span></span> <span data-ttu-id="37e5b-105">여기에는 중요한 데이터를 액세스 권한이 있는 사용자와만 안전하게 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-105">This includes being able to share sensitive data safely with only those who should have access to it.</span></span> <span data-ttu-id="37e5b-106">프로젝트에 따라 조직 외부의 사용자와 중요한 데이터를 공유하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-106">Depending on the project, this might include sharing sensitive data with people outside your organization.</span></span>

<span data-ttu-id="37e5b-107">이 공동 작업 솔루션 지침에는 다음 두 가지 구성 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-107">This collaboration solution guidance includes two components to help you:</span></span>
- <span data-ttu-id="37e5b-108">각 프로젝트에 대한 올바른 보호 수준을 통해 Microsoft Teams 배포</span><span class="sxs-lookup"><span data-stu-id="37e5b-108">Deploy Microsoft Teams with the right level of protection for each project</span></span>
- <span data-ttu-id="37e5b-109">각 프로젝트에 대해 적절한 보안 설정을 사용하여 외부 공유 구성</span><span class="sxs-lookup"><span data-stu-id="37e5b-109">Configure external sharing with appropriate security settings for each project</span></span>

![적절한 보호를 사용하여 Teams 배포 및 적절한 보안 설정으로 외부 공유 구성](..\media\solutions-architecture-center\secure-collaboration-overview.png)

<span data-ttu-id="37e5b-111">다용도 및 사용하기 쉬운 콘텐츠 공동 작업 도구를 사용할 수 없는 경우 사용자는 문서를 전자 메일로 보내 공동 작업을 하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-111">If versatile and easy-to-use content collaboration tools aren't available, users will often collaborate by emailing documents.</span></span> <span data-ttu-id="37e5b-112">이는 공동 작업의 지우고 오류가 발생할 수 있는 방법으로, 부적절한 정보 공유의 위험을 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-112">This is a tedious and error-prone method of collaboration, and can increase the risk of inappropriate sharing of information.</span></span> <span data-ttu-id="37e5b-113">공유 정보가 너무 어렵다는 것을 발견하면 IT에서 관리하지 않는 소비자 제품을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-113">If people find sharing information too difficult, they could revert to using consumer products that are not governed by IT.</span></span> <span data-ttu-id="37e5b-114">이는 훨씬 더 큰 위험을 내포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-114">This can pose an even greater risk.</span></span>

<span data-ttu-id="37e5b-115">Microsoft 365를 사용하면 다음을 도와주는 다양한 구성으로 Teams를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-115">With Microsoft 365, you can deploy Teams with a variety of configurations that help:</span></span>

- <span data-ttu-id="37e5b-116">지적 재산 보호</span><span class="sxs-lookup"><span data-stu-id="37e5b-116">Protect your intellectual property</span></span>
- <span data-ttu-id="37e5b-117">간편한 공동 작업 사용</span><span class="sxs-lookup"><span data-stu-id="37e5b-117">Enable easy collaboration</span></span>
- <span data-ttu-id="37e5b-118">보안과 사용성 간의 균형을 유지하여 사용자 만족도를 향상하고 섀도 IT의 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-118">Create a balance between security and usability that increases user satisfaction and reduces the risk of shadow IT</span></span>

<span data-ttu-id="37e5b-119">대부분의 조직에서는 정보가 부적절하게 공유되는 경우 민감도 및 비즈니스 영향 정도가 다양한 다양한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-119">Most organizations have a variety of information, with varying degrees of sensitivity and varying degrees of business impact if the information is inappropriately shared.</span></span> <span data-ttu-id="37e5b-120">특정 정보의 민감도에 따라 다음과의 공유를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-120">Depending on the sensitivity of a given piece of information, you may want to allow sharing with:</span></span>

- <span data-ttu-id="37e5b-121">모든 사람(비인식)</span><span class="sxs-lookup"><span data-stu-id="37e5b-121">Anyone (unauthenticated)</span></span>
- <span data-ttu-id="37e5b-122">조직 내부 사용자</span><span class="sxs-lookup"><span data-stu-id="37e5b-122">People inside the organization</span></span>
- <span data-ttu-id="37e5b-123">조직 내부의 특정 사용자</span><span class="sxs-lookup"><span data-stu-id="37e5b-123">Specific people inside the organization</span></span>
- <span data-ttu-id="37e5b-124">조직 내부 및 외부의 특정 사용자</span><span class="sxs-lookup"><span data-stu-id="37e5b-124">Specific people inside and outside the organization</span></span>

<span data-ttu-id="37e5b-125">마케팅 브로셔와 같은 정보는 조직 외부에서 광범위하게 공유하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-125">Information such as marketing brochures are meant for sharing broadly outside the organization.</span></span> <span data-ttu-id="37e5b-126">카페테리아 메뉴와 같은 정보는 외부 공유를 위한 것이 아니라 외부에서 공유된 경우 비즈니스에 영향을 줄 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-126">Information such as cafeteria menus aren't meant for external sharing, but would have no business impact if they were shared externally.</span></span> <span data-ttu-id="37e5b-127">이러한 유형의 정보는 보호가 거의 또는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-127">These types of information need little or no protection.</span></span>

<span data-ttu-id="37e5b-128">개발 중에는 조직 내에서만 동일한 마케팅 브로셔를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-128">Those same marketing brochures, while under development, might only be shared inside the organization.</span></span> <span data-ttu-id="37e5b-129">이 경우 Teams의 기본 공유 설정으로 충분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-129">In this case, the default sharing settings in Teams may be sufficient.</span></span>

<span data-ttu-id="37e5b-130">개발 중인 새 제품에 대한 정보는 조직 내에서도 중요한 것으로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-130">Information about a new product that is under development might be considered sensitive, even within the organization.</span></span> <span data-ttu-id="37e5b-131">이 경우 더 높은 수준의 보호가 적절할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-131">A greater degree of protection might be appropriate in this case.</span></span> <span data-ttu-id="37e5b-132">예를 들어 이 정보에 대한 액세스를 특정 팀의 구성원으로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-132">You could restrict access to this information to members of a specific team, for example.</span></span> <span data-ttu-id="37e5b-133">프로젝트에 따라 공급업체 또는 파트너 조직과 같은 조직 외부의 사용자와 공동 작업을 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-133">Depending on the project, you may need to collaborate with people outside your organization, such as a vendor or partner organization.</span></span>

<span data-ttu-id="37e5b-134">조직의 성공에 중요하거나 엄격한 보안 또는 규정 준수 요구 사항이 있는 정보는 훨씬 더 높은 수준의 보호가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-134">Information that is critical to your organization's success, or has stringent security or compliance requirements might require even greater levels of protection.</span></span>

![위험 수준이 낮음(릴리스된 브로셔)에서 높은(중요한 비즈니스 데이터)로 확장](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

<span data-ttu-id="37e5b-136">위에서 설명한 모든 시나리오에 대해 Microsoft Teams의 팀을 사용하여 정보를 저장, 공유 및 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-136">For all the scenarios noted above, you can use teams in Microsoft Teams to store, share, and collaborate on the information.</span></span> 

<span data-ttu-id="37e5b-137">보안 공동 작업을 구성하기 위해 이러한 Microsoft 365 기능 및 기능을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-137">To configure secure collaboration, you use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="37e5b-138">제품 또는 구성 요소</span><span class="sxs-lookup"><span data-stu-id="37e5b-138">Product or component</span></span> | <span data-ttu-id="37e5b-139">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="37e5b-139">Capability or feature</span></span> | <span data-ttu-id="37e5b-140">라이선싱</span><span class="sxs-lookup"><span data-stu-id="37e5b-140">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="37e5b-141">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="37e5b-141">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="37e5b-142">SPO, OneDrive 및 Teams에 대한 안전한 첨부 파일 안전한 문서 Teams에 대한 안전한 링크</span><span class="sxs-lookup"><span data-stu-id="37e5b-142">Safe Attachments for SPO, OneDrive and Teams; Safe Documents; Safe Links for Teams</span></span>    | <span data-ttu-id="37e5b-143">Microsoft 365 E1, E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="37e5b-143">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="37e5b-144">SharePoint</span><span class="sxs-lookup"><span data-stu-id="37e5b-144">SharePoint</span></span>    | <span data-ttu-id="37e5b-145">사이트 및 파일 공유 정책, 사이트 공유 권한, 공유 링크, 액세스 요청, 사이트 게스트 공유 설정</span><span class="sxs-lookup"><span data-stu-id="37e5b-145">Site and file sharing policies, Site sharing permissions, Sharing links, Access requests, Site guest sharing settings</span></span> | <span data-ttu-id="37e5b-146">Microsoft 365 E1, E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="37e5b-146">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="37e5b-147">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37e5b-147">Microsoft Teams</span></span>   | <span data-ttu-id="37e5b-148">게스트 액세스, 비공개 팀, 비공개 채널</span><span class="sxs-lookup"><span data-stu-id="37e5b-148">Guest access, private teams, private channels</span></span> | <span data-ttu-id="37e5b-149">Microsoft 365 E1, E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="37e5b-149">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="37e5b-150">Microsoft 365 규정 준수</span><span class="sxs-lookup"><span data-stu-id="37e5b-150">Microsoft 365 Compliance</span></span>  | <span data-ttu-id="37e5b-151">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="37e5b-151">Sensitivity labels</span></span>    | <span data-ttu-id="37e5b-152">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="37e5b-152">Microsoft 365 E3 and E5</span></span> |

### <a name="using-teams-for-all-kinds-of-data"></a><span data-ttu-id="37e5b-153">모든 종류의 데이터에 Teams 사용</span><span class="sxs-lookup"><span data-stu-id="37e5b-153">Using Teams for all kinds of data</span></span>

<span data-ttu-id="37e5b-154">민감도가 다른 정보에 대한 액세스를 관리하기 위해 Teams에 대한 세 가지 보호 [계층을 개발했습니다.](configure-teams-three-tiers-protection.md)</span><span class="sxs-lookup"><span data-stu-id="37e5b-154">To manage access to information with different sensitivities, we've developed [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span> <span data-ttu-id="37e5b-155">이러한 계층을 사용자 지정하여 요구 또는 비즈니스를 보다 잘 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-155">You can customize any of these tiers to better address the needs or your business.</span></span> 

![Teams 논리 아키텍처 포스터의 축소판 그림 이미지](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


<span data-ttu-id="37e5b-157">이러한 계층(기준, 중요 및  중요도)은 다음 표와 같이 과도하게 공유 및 잠재적인 정보 누출을 방지하는 데 도움이 되는 보호 기능을 점진적으로 늘려나가고 있습니다. </span><span class="sxs-lookup"><span data-stu-id="37e5b-157">These tiers - *baseline*, *sensitive*, and *highly sensitive* - gradually increase the protections that help prevent oversharing and potential information leakage, as shown in the following table.</span></span>

|-|<span data-ttu-id="37e5b-158">**기준 계층**</span><span class="sxs-lookup"><span data-stu-id="37e5b-158">**Baseline tier**</span></span>|<span data-ttu-id="37e5b-159">**중요 계층**</span><span class="sxs-lookup"><span data-stu-id="37e5b-159">**Sensitive tier**</span></span>|<span data-ttu-id="37e5b-160">**높은 중요 계층**</span><span class="sxs-lookup"><span data-stu-id="37e5b-160">**Highly sensitive tier**</span></span>|
|:--|:-----------|:------------|:-------------------|
|<span data-ttu-id="37e5b-161">공개 또는 비공개 팀</span><span class="sxs-lookup"><span data-stu-id="37e5b-161">Public or private team</span></span>|<span data-ttu-id="37e5b-162">둘 중 하나</span><span class="sxs-lookup"><span data-stu-id="37e5b-162">Either</span></span>|<span data-ttu-id="37e5b-163">개인</span><span class="sxs-lookup"><span data-stu-id="37e5b-163">Private</span></span>|<span data-ttu-id="37e5b-164">개인</span><span class="sxs-lookup"><span data-stu-id="37e5b-164">Private</span></span>|
|<span data-ttu-id="37e5b-165">인증되지 않은 공유</span><span class="sxs-lookup"><span data-stu-id="37e5b-165">Unauthenticated sharing</span></span>|<span data-ttu-id="37e5b-166">차단됨</span><span class="sxs-lookup"><span data-stu-id="37e5b-166">Blocked</span></span>|<span data-ttu-id="37e5b-167">차단됨</span><span class="sxs-lookup"><span data-stu-id="37e5b-167">Blocked</span></span>|<span data-ttu-id="37e5b-168">차단됨</span><span class="sxs-lookup"><span data-stu-id="37e5b-168">Blocked</span></span>|
|<span data-ttu-id="37e5b-169">파일 공유</span><span class="sxs-lookup"><span data-stu-id="37e5b-169">File sharing</span></span>|<span data-ttu-id="37e5b-170">허용됨</span><span class="sxs-lookup"><span data-stu-id="37e5b-170">Allowed</span></span>|<span data-ttu-id="37e5b-171">허용됨</span><span class="sxs-lookup"><span data-stu-id="37e5b-171">Allowed</span></span>|<span data-ttu-id="37e5b-172">팀 소유자만 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-172">Only team owners can share.</span></span>|
|<span data-ttu-id="37e5b-173">팀 구성원</span><span class="sxs-lookup"><span data-stu-id="37e5b-173">Team membership</span></span>|<span data-ttu-id="37e5b-174">누구나 공개 팀에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-174">Anyone can join public teams.</span></span><br><span data-ttu-id="37e5b-175">비공개 팀에 참가하는 데 팀 소유자 승인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-175">Team owner approval required to join private teams.</span></span>|<span data-ttu-id="37e5b-176">참가에 팀 소유자 승인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-176">Team owner approval required to join.</span></span>|<span data-ttu-id="37e5b-177">참가에 팀 소유자 승인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-177">Team owner approval required to join.</span></span>|
|<span data-ttu-id="37e5b-178">문서 암호화</span><span class="sxs-lookup"><span data-stu-id="37e5b-178">Document encryption</span></span>|||<span data-ttu-id="37e5b-179">민감도 레이블과 함께 사용 가능</span><span class="sxs-lookup"><span data-stu-id="37e5b-179">Available with sensitivity label</span></span>|
|<span data-ttu-id="37e5b-180">게스트 공유</span><span class="sxs-lookup"><span data-stu-id="37e5b-180">Guest sharing</span></span>|<span data-ttu-id="37e5b-181">허용됨</span><span class="sxs-lookup"><span data-stu-id="37e5b-181">Allowed</span></span>|<span data-ttu-id="37e5b-182">허용 또는 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-182">Can be allowed or blocked</span></span>|<span data-ttu-id="37e5b-183">허용 또는 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-183">Can be allowed or blocked</span></span>|
|<span data-ttu-id="37e5b-184">관리되지 않는 장치</span><span class="sxs-lookup"><span data-stu-id="37e5b-184">Unmanaged devices</span></span>|<span data-ttu-id="37e5b-185">제한 없음</span><span class="sxs-lookup"><span data-stu-id="37e5b-185">No restriction</span></span>|<span data-ttu-id="37e5b-186">웹 전용 액세스</span><span class="sxs-lookup"><span data-stu-id="37e5b-186">Web-only access</span></span>|<span data-ttu-id="37e5b-187">차단됨</span><span class="sxs-lookup"><span data-stu-id="37e5b-187">Blocked</span></span>|

<span data-ttu-id="37e5b-188">이러한 계층을 구성하는 과정에는 다음이 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-188">Configuring these tiers involves:</span></span>

- <span data-ttu-id="37e5b-189">게스트 액세스 및 비공개 채널에 대한 Teams의 설정 구성</span><span class="sxs-lookup"><span data-stu-id="37e5b-189">Configuring settings in Teams for guest access and private channels</span></span>
- <span data-ttu-id="37e5b-190">팀의 연결된 SharePoint 사이트에서 내부 및 게스트 공유, 액세스 요청 및 공유 링크를 위한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="37e5b-190">Configuring settings in a team's associated SharePoint site for internal and guest sharing, access requests, and sharing links</span></span>
- <span data-ttu-id="37e5b-191">중요하고  매우 *중요한* 계층의 경우 팀을 분류하고, 관리되지 않는 장치에서 게스트 공유 및 액세스를 제어하기 위해 민감도 레이블을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-191">For the *sensitive* and *highly sensitive* tiers, configuring sensitivity labels to classify the teams, and control guest sharing and access from unmanaged devices</span></span>
- <span data-ttu-id="37e5b-192">매우 *중요한 계층의* 경우 민감도 레이블을 구성하여 해당 계층이 적용되는 문서를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-192">For the *highly sensitive* tier, configuring a sensitivity label to encrypt the documents to which it is applied</span></span>

<span data-ttu-id="37e5b-193">기준 계층으로 시작한 다음, 필요한 경우  중요하고 중요한 계층을 사용하는 팀을 추가하여 조직의 정보를 보호합니다. </span><span class="sxs-lookup"><span data-stu-id="37e5b-193">Start with the baseline tier, and then add teams that use the *sensitive* and *highly sensitive* tiers as needed to help protect the information in your organization.</span></span> <span data-ttu-id="37e5b-194">시작을 위해 다음 리소스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-194">See these resources to get started:</span></span>

- [<span data-ttu-id="37e5b-195">기본 보호 기능으로 팀 구성</span><span class="sxs-lookup"><span data-stu-id="37e5b-195">Configure teams with baseline protection</span></span>](configure-teams-baseline-protection.md)
- [<span data-ttu-id="37e5b-196">중요한 데이터를 보호하는 팀 구성하기</span><span class="sxs-lookup"><span data-stu-id="37e5b-196">Configure teams with protection for sensitive data</span></span>](configure-teams-sensitive-protection.md)
- [<span data-ttu-id="37e5b-197">매우 중요한 데이터를 보호하는 팀 구성하기</span><span class="sxs-lookup"><span data-stu-id="37e5b-197">Configure teams with protection for highly sensitive data</span></span>](configure-teams-highly-sensitive-protection.md)

<span data-ttu-id="37e5b-198">조직 내에서도 공유로부터 추가 보호가 필요한 매우 중요한 프로젝트가 있는 경우 팀 구성원만 읽을 수 있도록 자체 민감도 레이블을 사용하는 팀을 구성하여 파일을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-198">If you have a highly sensitive project that requires additional protection from sharing even within your organization, you can configure a team that uses its own sensitivity label to encrypt files so that only team members can read them.</span></span> <span data-ttu-id="37e5b-199">자세한 [내용은 보안이 있는](secure-teams-security-isolation.md) 팀 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-199">See [Configure a team with security isolation](secure-teams-security-isolation.md) for details.</span></span>

### <a name="sharing-with-people-outside-your-organization"></a><span data-ttu-id="37e5b-200">조직 외부의 사용자와 공유</span><span class="sxs-lookup"><span data-stu-id="37e5b-200">Sharing with people outside your organization</span></span>

<span data-ttu-id="37e5b-201">조직 외부의 사용자와 민감도 정보를 [공유해야 할 수 있습니다.](collaborate-with-people-outside-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="37e5b-201">You may need to [share information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span> <span data-ttu-id="37e5b-202">단일 사용자와 단일 문서를 공유하는 것부터 대규모 파트너 조직 또는 전 세계의 프리랜서와 주요 프로젝트 공동 작업까지 다양할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-202">This could range from sharing a single document with a single person to collaborating on a major project with a large partner organization or freelancers from around the world.</span></span> <span data-ttu-id="37e5b-203">Microsoft 365에서 이 범위의 외부 공유는 중요한 정보를 보호하는 데 도움이 되는 적절한 세이프가드를 사용하여 쉽게 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-203">In Microsoft 365, this range of external sharing can be done easily and with the appropriate safeguards to help protect your sensitive information.</span></span>

<span data-ttu-id="37e5b-204">이러한 리소스는 조직 외부의 사용자와 공동 작업을 위한 환경을 설정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-204">These resources will help you get started with setting up your environment for collaborating with people outside your organization:</span></span>

- <span data-ttu-id="37e5b-205">[개별 폴더 파일을 공유하기](collaborate-on-documents.md) 위해 문서에 대해 공동 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-205">[Collaborate on documents](collaborate-on-documents.md) for sharing individual files of folders.</span></span>
- <span data-ttu-id="37e5b-206">[](collaborate-in-site.md) SharePoint 사이트에서 게스트와 공동 작업을 할 수 있는 사이트에서 공동 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-206">[Collaborate in a site](collaborate-in-site.md) for collaborating with guests in a SharePoint site.</span></span>
- <span data-ttu-id="37e5b-207">[팀의](collaborate-as-team.md) 게스트와 공동 작업을 위한 팀으로 공동 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-207">[Collaborate as a team](collaborate-as-team.md) for collaborating with guests in a team.</span></span>

<span data-ttu-id="37e5b-208">공유되는 정보의 민감도에 따라 과도하게 공유되지 않도록 보호 장치를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-208">Depending on the sensitivity of the information being shared, you can add safeguards to help prevent oversharing.</span></span> <span data-ttu-id="37e5b-209">이러한 리소스는 조직에 필요한 보호를 설정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-209">These resources will help you set up the protections that you need for your organization:</span></span>

- [<span data-ttu-id="37e5b-210">인증되지 않은 사용자와 파일 및 폴더를 공유하는 최우수 사례</span><span class="sxs-lookup"><span data-stu-id="37e5b-210">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)
- [<span data-ttu-id="37e5b-211">파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기</span><span class="sxs-lookup"><span data-stu-id="37e5b-211">Limit accidental exposure to files when sharing with people outside your organization</span></span>](share-limit-accidental-exposure.md)
- [<span data-ttu-id="37e5b-212">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="37e5b-212">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="37e5b-213">파트너 조직이 있는 주요 프로젝트가 있는 경우 Azure 권한 관리 기능을 사용하여 해당 조직의 게스트를 프로젝트에 대해 설정한 팀에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-213">If you have a major project with a partner organization, you can use Azure Entitlement Management to manage the guests from that organization in a team that you set up for the project.</span></span> <span data-ttu-id="37e5b-214">자세한 [내용은 관리되는 게스트가 있는 B2B 엑스트라넷](b2b-extranet.md) 만들기를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-214">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="deploy-the-secure-collaboration-solution"></a><span data-ttu-id="37e5b-215">보안 공동 작업 솔루션 배포</span><span class="sxs-lookup"><span data-stu-id="37e5b-215">Deploy the secure collaboration solution</span></span>

<span data-ttu-id="37e5b-216">이 솔루션을 배포할 준비가 되면 다음 단계를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-216">When you're ready to deploy this solution, continue with these steps:</span></span>
1. <span data-ttu-id="37e5b-217">Teams에 대한 세 가지 보호 [계층을 구성합니다.](configure-teams-three-tiers-protection.md)</span><span class="sxs-lookup"><span data-stu-id="37e5b-217">Configure the [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span>
2. <span data-ttu-id="37e5b-218">조직 외부의 사용자와 민감도 정보를 [공유하기 위한 설정을 구성합니다.](collaborate-with-people-outside-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="37e5b-218">Configure settings for [sharing information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="37e5b-219">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37e5b-219">See also</span></span>

[<span data-ttu-id="37e5b-220">Microsoft 365 보안 설명서</span><span class="sxs-lookup"><span data-stu-id="37e5b-220">Microsoft 365 security documentation</span></span>](https://docs.microsoft.com/microsoft-365/security)

[<span data-ttu-id="37e5b-221">Microsoft 365 규정 준수 설명서</span><span class="sxs-lookup"><span data-stu-id="37e5b-221">Microsoft 365 compliance documentation</span></span>](https://docs.microsoft.com/microsoft-365/compliance)

[<span data-ttu-id="37e5b-222">Microsoft Teams에 오신 것을 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="37e5b-222">Welcome to Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
