---
title: Microsoft 365을 사용한 보안 공동 작업 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
description: 해당 민감도에 따라 데이터를 보호 하도록 팀을 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 8704c3a0a271c247652d611e963ff1d26308dcdb
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159470"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a><span data-ttu-id="99f63-103">Microsoft 365을 사용한 보안 공동 작업 설정</span><span class="sxs-lookup"><span data-stu-id="99f63-103">Set up secure collaboration with Microsoft 365</span></span>

<span data-ttu-id="99f63-104">조직의 성공적인 공유를 방지 하면서 적절 한 사람들과 쉽게 정보를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-104">Being able to easily share information with the right people while preventing oversharing is key to an organization's success.</span></span> <span data-ttu-id="99f63-105">여기에는 액세스 권한이 있는 사람만 중요 한 데이터를 안전 하 게 공유할 수 있는 권한이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-105">This includes being able to share sensitive data safely with only those who should have access to it.</span></span> <span data-ttu-id="99f63-106">프로젝트에 따라 중요 한 데이터를 조직 외부의 사용자와 공유 하는 것이 여기에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-106">Depending on the project, this might include sharing sensitive data with people outside your organization.</span></span>

<span data-ttu-id="99f63-107">이 솔루션 지침에는 다음과 같은 두 가지 구성 요소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-107">This solution guidance includes two components to help you:</span></span>
- <span data-ttu-id="99f63-108">각 프로젝트에 적절 한 수준의 보호를 사용 하 여 Microsoft 팀 배포</span><span class="sxs-lookup"><span data-stu-id="99f63-108">Deploy Microsoft Teams with the right level of protection for each project</span></span>
- <span data-ttu-id="99f63-109">각 프로젝트에 대해 적절 한 보안 설정을 사용 하 여 외부 공유 구성</span><span class="sxs-lookup"><span data-stu-id="99f63-109">Configure external sharing with appropriate security settings for each project</span></span>

![적절 한 보호를 사용 하 여 팀 배포 및 적절 한 보안 설정을 사용 하 여 외부 공유 구성](..\media\solutions-architecture-center\secure-collaboration-overview.png)

<span data-ttu-id="99f63-111">다용도이 고 사용 하기 쉬운 공동 작업 도구를 사용할 수 없는 경우 사용자는 문서를 이메일로 보내 자주 공동 작업을 수행 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-111">If versatile and easy-to-use collaboration tools aren't available, users will often collaborate by emailing documents.</span></span> <span data-ttu-id="99f63-112">이는 공동 작업을 위한 지루한 및 오류가 발생 하기 쉬운 방법으로, 부적절 한 정보 공유 위험을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-112">This is a tedious and error-prone method of collaboration, and can increase the risk of inappropriate sharing of information.</span></span> <span data-ttu-id="99f63-113">사용자가 너무 어려운 공유 정보를 찾는 경우에는 해당 정보가 관리 되지 않는 소비자 제품을 사용 하 여 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-113">If people find sharing information too difficult, they could revert to using consumer products that are not governed by IT.</span></span> <span data-ttu-id="99f63-114">이 경우 훨씬 더 많은 위험을 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-114">This can pose an even greater risk.</span></span>

<span data-ttu-id="99f63-115">Microsoft 365에서는 다음과 같은 다양 한 구성을 사용 하 여 팀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-115">With Microsoft 365, you can deploy Teams with a variety of configurations that help:</span></span>

- <span data-ttu-id="99f63-116">지적 재산 보호</span><span class="sxs-lookup"><span data-stu-id="99f63-116">Protect your intellectual property</span></span>
- <span data-ttu-id="99f63-117">손쉬운 공동 작업 사용</span><span class="sxs-lookup"><span data-stu-id="99f63-117">Enable easy collaboration</span></span>
- <span data-ttu-id="99f63-118">보안 및 편리성 간의 균형을 조정 하 여 사용자 만족도를 높여 섀도 IT의 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-118">Create a balance between security and usability that increases user satisfaction and reduces the risk of shadow IT</span></span>

<span data-ttu-id="99f63-119">대부분의 조직에는 정보가 부적절 하 게 공유 되는 경우 다양 한 수준의 민감도와 다양 한 비즈니스 영향을 갖는 여러 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-119">Most organizations have a variety of information, with varying degrees of sensitivity and varying degrees of business impact if the information is inappropriately shared.</span></span> <span data-ttu-id="99f63-120">지정 된 정보 부분의 민감도에 따라 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-120">Depending on the sensitivity of a given piece of information, you may want to allow sharing with:</span></span>

- <span data-ttu-id="99f63-121">모든 사용자 (인증 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="99f63-121">Anyone (unauthenticated)</span></span>
- <span data-ttu-id="99f63-122">조직 내부의 사용자</span><span class="sxs-lookup"><span data-stu-id="99f63-122">People inside the organization</span></span>
- <span data-ttu-id="99f63-123">조직 내부의 특정 사용자</span><span class="sxs-lookup"><span data-stu-id="99f63-123">Specific people inside the organization</span></span>
- <span data-ttu-id="99f63-124">조직 내부 및 외부의 특정 사용자</span><span class="sxs-lookup"><span data-stu-id="99f63-124">Specific people inside and outside the organization</span></span>

<span data-ttu-id="99f63-125">마케팅 브로셔와 같은 정보는 조직 외부에서 광범위 하 게 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-125">Information such as marketing brochures are meant for sharing broadly outside the organization.</span></span> <span data-ttu-id="99f63-126">Cafeteria 메뉴와 같은 정보는 외부 공유를 위한 것이 아니라 외부적으로 공유 하는 경우에는 비즈니스에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-126">Information such as cafeteria menus aren't meant for external sharing, but would have no business impact if they were shared externally.</span></span> <span data-ttu-id="99f63-127">이러한 유형의 정보는 보호를 거의 또는 전혀 수행 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-127">These types of information need little or no protection.</span></span>

<span data-ttu-id="99f63-128">이러한 동일한 마케팅 브로슈어를 개발 중에는 조직 내 에서만 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-128">Those same marketing brochures, while under development, might only be shared inside the organization.</span></span> <span data-ttu-id="99f63-129">이 경우 팀의 기본 공유 설정이 충분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-129">In this case, the default sharing settings in Teams may be sufficient.</span></span>

<span data-ttu-id="99f63-130">개발 중인 새 제품에 대 한 정보는 조직 내 에서도 중요 한 것으로 간주 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-130">Information about a new product that is under development might be considered sensitive, even within the organization.</span></span> <span data-ttu-id="99f63-131">이 경우에는 보다 높은 수준의 보호가 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-131">A greater degree of protection might be appropriate in this case.</span></span> <span data-ttu-id="99f63-132">예를 들어 특정 팀의 구성원에 게이 정보에 대 한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-132">You could restrict access to this information to members of a specific team, for example.</span></span> <span data-ttu-id="99f63-133">프로젝트에 따라 공급 업체 또는 파트너 조직과 같이 조직 외부의 사용자와 공동 작업을 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-133">Depending on the project, you may need to collaborate with people outside your organization, such as a vendor or partner organization.</span></span>

<span data-ttu-id="99f63-134">조직의 성공 또는 엄격한 보안 또는 준수 요구 사항에 중요 한 정보를 포함 하는 경우 더 많은 보호 수준도 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-134">Information that is critical to your organization's success, or has stringent security or compliance requirements might require even greater levels of protection.</span></span>

![낮음 (브로슈어 출시)에서 높음 (중요 한 비즈니스 데이터)까지 위험 확장](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

<span data-ttu-id="99f63-136">위에 언급 된 모든 시나리오에 대해 Microsoft 팀의 팀을 사용 하 여 정보를 저장, 공유 및 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-136">For all the scenarios noted above, you can use teams in Microsoft Teams to store, share, and collaborate on the information.</span></span> 

## <a name="using-teams-for-all-kinds-of-data"></a><span data-ttu-id="99f63-137">모든 종류의 데이터에 대 한 팀 사용</span><span class="sxs-lookup"><span data-stu-id="99f63-137">Using Teams for all kinds of data</span></span>

<span data-ttu-id="99f63-138">다른 sensitivities 정보에 대 한 액세스를 관리 하기 위해 [팀에서 세 가지 다른 수준의 보호](configure-teams-three-tiers-protection.md)를 개발 했습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-138">To manage access to information with different sensitivities, we've developed [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span> <span data-ttu-id="99f63-139">이러한 계층을 사용자 지정 하 여 요구 사항 또는 비즈니스에 보다 적합 한 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-139">You can customize any of these tiers to better address the needs or your business.</span></span> 

![Teams 논리 아키텍처 포스터의 축소판 그림 이미지](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


<span data-ttu-id="99f63-141">이러한 계층- *초기 계획*, *중요*및 *높은 수준의 중요* -다음 표와 같이 과잉 공유 및 잠재적인 정보 누출을 방지 하는 보호 기능을 단계적으로 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-141">These tiers - *baseline*, *sensitive*, and *highly sensitive* - gradually increase the protections that help prevent oversharing and potential information leakage, as shown in the following table.</span></span>

||<span data-ttu-id="99f63-142">**기본 계층**</span><span class="sxs-lookup"><span data-stu-id="99f63-142">**Baseline tier**</span></span>|<span data-ttu-id="99f63-143">**중요 계층**</span><span class="sxs-lookup"><span data-stu-id="99f63-143">**Sensitive tier**</span></span>|<span data-ttu-id="99f63-144">**높은 중요 계층**</span><span class="sxs-lookup"><span data-stu-id="99f63-144">**Highly sensitive tier**</span></span>|
|:--|:-----------|:------------|:-------------------|
|<span data-ttu-id="99f63-145">공용 또는 비공개 팀</span><span class="sxs-lookup"><span data-stu-id="99f63-145">Public or private team</span></span>|<span data-ttu-id="99f63-146">일</span><span class="sxs-lookup"><span data-stu-id="99f63-146">Either</span></span>|<span data-ttu-id="99f63-147">개인</span><span class="sxs-lookup"><span data-stu-id="99f63-147">Private</span></span>|<span data-ttu-id="99f63-148">개인</span><span class="sxs-lookup"><span data-stu-id="99f63-148">Private</span></span>|
|<span data-ttu-id="99f63-149">인증되지 않은 공유</span><span class="sxs-lookup"><span data-stu-id="99f63-149">Unauthenticated sharing</span></span>|<span data-ttu-id="99f63-150">수준</span><span class="sxs-lookup"><span data-stu-id="99f63-150">Blocked</span></span>|<span data-ttu-id="99f63-151">수준</span><span class="sxs-lookup"><span data-stu-id="99f63-151">Blocked</span></span>|<span data-ttu-id="99f63-152">수준</span><span class="sxs-lookup"><span data-stu-id="99f63-152">Blocked</span></span>|
|<span data-ttu-id="99f63-153">파일 공유</span><span class="sxs-lookup"><span data-stu-id="99f63-153">File sharing</span></span>|<span data-ttu-id="99f63-154">있도록</span><span class="sxs-lookup"><span data-stu-id="99f63-154">Allowed</span></span>|<span data-ttu-id="99f63-155">있도록</span><span class="sxs-lookup"><span data-stu-id="99f63-155">Allowed</span></span>|<span data-ttu-id="99f63-156">팀 소유자만 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-156">Only team owners can share.</span></span>|
|<span data-ttu-id="99f63-157">팀 구성원</span><span class="sxs-lookup"><span data-stu-id="99f63-157">Team membership</span></span>|<span data-ttu-id="99f63-158">모든 사용자가 공용 팀에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-158">Anyone can join public teams.</span></span><br><span data-ttu-id="99f63-159">비공개 팀에 참가 하는 데 필요한 팀 소유자 승인</span><span class="sxs-lookup"><span data-stu-id="99f63-159">Team owner approval required to join private teams.</span></span>|<span data-ttu-id="99f63-160">참가 하는 데 필요한 팀 소유자 승인입니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-160">Team owner approval required to join.</span></span>|<span data-ttu-id="99f63-161">참가 하는 데 필요한 팀 소유자 승인입니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-161">Team owner approval required to join.</span></span>|
|<span data-ttu-id="99f63-162">문서 암호화</span><span class="sxs-lookup"><span data-stu-id="99f63-162">Document encryption</span></span>|||<span data-ttu-id="99f63-163">민감도 레이블 사용 가능</span><span class="sxs-lookup"><span data-stu-id="99f63-163">Available with sensitivity label</span></span>|
|<span data-ttu-id="99f63-164">게스트 공유</span><span class="sxs-lookup"><span data-stu-id="99f63-164">Guest sharing</span></span>|<span data-ttu-id="99f63-165">있도록</span><span class="sxs-lookup"><span data-stu-id="99f63-165">Allowed</span></span>|<span data-ttu-id="99f63-166">허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-166">Can be allowed or blocked</span></span>|<span data-ttu-id="99f63-167">허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-167">Can be allowed or blocked</span></span>|
|<span data-ttu-id="99f63-168">관리 되지 않는 장치</span><span class="sxs-lookup"><span data-stu-id="99f63-168">Unmanaged devices</span></span>|<span data-ttu-id="99f63-169">제한 없음</span><span class="sxs-lookup"><span data-stu-id="99f63-169">No restriction</span></span>|<span data-ttu-id="99f63-170">웹 전용 액세스</span><span class="sxs-lookup"><span data-stu-id="99f63-170">Web-only access</span></span>|<span data-ttu-id="99f63-171">수준</span><span class="sxs-lookup"><span data-stu-id="99f63-171">Blocked</span></span>|

<span data-ttu-id="99f63-172">이러한 계층 구성에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-172">Configuring these tiers involves:</span></span>

- <span data-ttu-id="99f63-173">게스트 액세스 및 개인 채널에 대 한 팀의 설정 구성</span><span class="sxs-lookup"><span data-stu-id="99f63-173">Configuring settings in Teams for guest access and private channels</span></span>
- <span data-ttu-id="99f63-174">내부 및 게스트 공유, 액세스 요청 및 공유 링크에 대 한 팀의 연결 된 SharePoint 사이트의 설정 구성</span><span class="sxs-lookup"><span data-stu-id="99f63-174">Configuring settings in a team's associated SharePoint site for internal and guest sharing, access requests, and sharing links</span></span>
- <span data-ttu-id="99f63-175">*중요* 및 *중요 한* 계층의 경우 팀을 분류 하기 위한 민감도 레이블을 구성 하 고 관리 되지 않는 장치에서 게스트 공유 및 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="99f63-175">For the *sensitive* and *highly sensitive* tiers, configuring sensitivity labels to classify the teams, and control guest sharing and access from unmanaged devices</span></span>
- <span data-ttu-id="99f63-176">중요도가 *높은* 계층의 경우 적용 되는 문서를 암호화 하는 민감도 레이블을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-176">For the *highly sensitive* tier, configuring a sensitivity label to encrypt the documents to which it is applied</span></span>

<span data-ttu-id="99f63-177">기본 계층부터 시작한 다음 필요에 따라 *중요* 하 고 *중요* 한 계층을 사용 하는 팀을 추가 하 여 조직의 정보를 보호 하는 데 도움을 주는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-177">Start with the baseline tier, and then add teams that use the *sensitive* and *highly sensitive* tiers as needed to help protect the information in your organization.</span></span> <span data-ttu-id="99f63-178">시작 하려면 다음 리소스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f63-178">See these resources to get started:</span></span>

- [<span data-ttu-id="99f63-179">기본 보호 기능으로 팀 구성</span><span class="sxs-lookup"><span data-stu-id="99f63-179">Configure teams with baseline protection</span></span>](configure-teams-baseline-protection.md)
- [<span data-ttu-id="99f63-180">중요한 데이터를 보호하는 팀 구성하기</span><span class="sxs-lookup"><span data-stu-id="99f63-180">Configure teams with protection for sensitive data</span></span>](configure-teams-sensitive-protection.md)
- [<span data-ttu-id="99f63-181">매우 중요한 데이터를 보호하는 팀 구성하기</span><span class="sxs-lookup"><span data-stu-id="99f63-181">Configure teams with protection for highly sensitive data</span></span>](configure-teams-highly-sensitive-protection.md)

<span data-ttu-id="99f63-182">조직 내 에서도 공유 기능을 추가로 보호 해야 하는 중요 한 프로젝트가 있는 경우 해당 민감도 레이블을 사용 하 여 팀 구성원만 읽을 수 있도록 파일을 암호화 하는 팀을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-182">If you have a highly sensitive project that requires additional protection from sharing even within your organization, you can configure a team that uses its own sensitivity label to encrypt files so that only team members can read them.</span></span> <span data-ttu-id="99f63-183">자세한 내용은 [보안 격리를 사용 하 여 팀 구성을](secure-teams-security-isolation.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f63-183">See [Configure a team with security isolation](secure-teams-security-isolation.md) for details.</span></span>

## <a name="sharing-with-people-outside-your-organization"></a><span data-ttu-id="99f63-184">조직 외부의 사용자와 공유</span><span class="sxs-lookup"><span data-stu-id="99f63-184">Sharing with people outside your organization</span></span>

<span data-ttu-id="99f63-185">[조직 외부의 사용자와의 민감도 정보를 공유](collaborate-with-people-outside-your-organization.md)해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-185">You may need to [share information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span> <span data-ttu-id="99f63-186">이는 단일 문서를 공유 하 여 대규모 파트너 조직이 나 전 세계의 freelancers 주요 프로젝트에서 공동 작업을 수행할 수 있는 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-186">This could range from sharing a single document with a single person to collaborating on a major project with a large partner organization or freelancers from around the world.</span></span> <span data-ttu-id="99f63-187">Microsoft 365에서이 범위 외부 공유는 중요 한 정보를 보호 하는 데 적합 한 적절 한 보호책을 사용 하 여 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-187">In Microsoft 365, this range of external sharing can be done easily and with the appropriate safeguards to help protect your sensitive information.</span></span>

<span data-ttu-id="99f63-188">이러한 리소스를 사용 하면 조직 외부의 사용자와 공동으로 작업할 수 있도록 환경을 설정 하는 작업을 시작 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-188">These resources will help you get started with setting up your environment for collaborating with people outside your organization:</span></span>

- <span data-ttu-id="99f63-189">개별 폴더 파일을 공유할 [문서를 공동 작업](collaborate-on-documents.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-189">[Collaborate on documents](collaborate-on-documents.md) for sharing individual files of folders.</span></span>
- <span data-ttu-id="99f63-190">SharePoint 사이트에서 게스트와 공동 작업 하기 위해 [사이트에서 협력](collaborate-in-site.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-190">[Collaborate in a site](collaborate-in-site.md) for collaborating with guests in a SharePoint site.</span></span>
- <span data-ttu-id="99f63-191">팀 [과 공동 작업](collaborate-as-team.md) 을 수행 하는 팀의 게스트</span><span class="sxs-lookup"><span data-stu-id="99f63-191">[Collaborate as a team](collaborate-as-team.md) for collaborating with guests in a team.</span></span>

<span data-ttu-id="99f63-192">공유 되는 정보의 민감도에 따라, 과잉 공유를 방지 하는 보호 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-192">Depending on the sensitivity of the information being shared, you can add safeguards to help prevent oversharing.</span></span> <span data-ttu-id="99f63-193">이러한 리소스는 조직에 필요한 보호를 설정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-193">These resources will help you set up the protections that you need for your organization:</span></span>

- [<span data-ttu-id="99f63-194">인증되지 않은 사용자와 파일 및 폴더를 공유하는 최우수 사례</span><span class="sxs-lookup"><span data-stu-id="99f63-194">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)
- [<span data-ttu-id="99f63-195">파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기</span><span class="sxs-lookup"><span data-stu-id="99f63-195">Limit accidental exposure to files when sharing with people outside your organization</span></span>](share-limit-accidental-exposure.md)
- [<span data-ttu-id="99f63-196">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="99f63-196">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="99f63-197">파트너 조직이 포함 된 주요 프로젝트인 경우 Azure 권한 관리를 사용 하 여 프로젝트에 대해 설정한 팀의 해당 조직에서 게스트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-197">If you have a major project with a partner organization, you can use Azure Entitlement Management to manage the guests from that organization in a team that you set up for the project.</span></span> <span data-ttu-id="99f63-198">자세한 내용은 [관리 되는 게스트를 사용 하 여 B2B 엑스트라넷 만들기](b2b-extranet.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f63-198">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="see-also"></a><span data-ttu-id="99f63-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99f63-199">See also</span></span>

[<span data-ttu-id="99f63-200">Microsoft 365 보안 설명서</span><span class="sxs-lookup"><span data-stu-id="99f63-200">Microsoft 365 security documentation</span></span>](https://docs.microsoft.com/microsoft-365/security)

[<span data-ttu-id="99f63-201">Microsoft 365 규정 준수 설명서</span><span class="sxs-lookup"><span data-stu-id="99f63-201">Microsoft 365 compliance documentation</span></span>](https://docs.microsoft.com/microsoft-365/compliance)

[<span data-ttu-id="99f63-202">Microsoft Teams에 오신 것을 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="99f63-202">Welcome to Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
