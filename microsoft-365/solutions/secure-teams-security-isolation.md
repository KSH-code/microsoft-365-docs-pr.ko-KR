---
title: 보안 격리를 사용하여 팀 구성하기
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: 보안을 위한 고유한 민감도 레이블이 있는 팀을 만드는 방법을 알아봅니다.
ms.openlocfilehash: 789e75165339f8a834a73aa3fd0d8a2666285ce9
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308186"
---
# <a name="configure-a-team-with-security-isolation"></a><span data-ttu-id="14654-103">보안 격리를 사용하여 팀 구성하기</span><span class="sxs-lookup"><span data-stu-id="14654-103">Configure a team with security isolation</span></span>

<span data-ttu-id="14654-104">이 문서에서는 Microsoft Teams에서 비공개 팀을 구성하는 데 필요한 사항과 단계를 제공하고 팀 구성원만 암호를 해독할 수 있도록 고유한 민감도 레이블을 사용하여 파일을 암호화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams and use a unique sensitivity label to encrypt files so that only team members can decrypt them.</span></span>

<span data-ttu-id="14654-105">개인 액세스를 넘어서, 이 문서에서는 높은 규제 대상 데이터를 저장하는 데 필요한 추가 보안을 위해 팀 채널의 **파일** 섹션에서 액세스할 수 있는 연결된 SharePoint 사이트를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-105">Beyond the private access, this article describes how to configure the associated SharePoint site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span>

<span data-ttu-id="14654-106">보안 격리 팀을 위한 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-106">The elements of configuration for a team with security isolation are:</span></span>

- <span data-ttu-id="14654-107">비공개 팀</span><span class="sxs-lookup"><span data-stu-id="14654-107">A private team</span></span>
- <span data-ttu-id="14654-108">팀의 연결된 SharePoint 사이트에 대한 추가 보안 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-108">Additional security on the associated SharePoint site for the team that:</span></span>
  - <span data-ttu-id="14654-109">사이트 구성원이 다른 사용자와 사이트를 공유하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-109">Prevents members of the site from sharing the site with others.</span></span>
  - <span data-ttu-id="14654-110">사이트의 구성원 이외의 사용자가 사이트 액세스 권한을 요청하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-110">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="14654-111">이 팀에 대한 민감도 레이블은 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-111">A sensitivity label specifically for this team that:</span></span>
    - <span data-ttu-id="14654-112">관리되지 않는 장치에서 SharePoint 콘텐츠에 액세스하지 못하도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-112">Prevents access to SharePoint content from unmanaged devices</span></span>
    - <span data-ttu-id="14654-113">요구 사항에 따라 팀에 게스트 액세스를 허용하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-113">Allows or denies guest access to the team, depending on your requirements</span></span>
    - <span data-ttu-id="14654-114">레이블이 적용된 문서를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-114">Encrypts documents to which the label is applied</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14654-115">이 문서의 단계를 진행하기 전에 [Microsoft Teams, Office 365 그룹 및 SharePoint 사이트에서 콘텐츠를 보호할 수 있도록 민감도 레이블](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)을 사용하도록 설정했는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="14654-115">Be sure you have enabled [sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) before you proceed with the steps in this article.</span></span>

<a name="poster"></a><span data-ttu-id="14654-116">이 시나리오에 대 한 2페이지 요약을 보려면 [보안 격리 포스터를 사용한 Microsoft Teams](../downloads/team-security-isolation-poster.pdf)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14654-116">For a 2-page summary of this scenario, see the [Microsoft Teams with security isolation poster](../downloads/team-security-isolation-poster.pdf).</span></span>

<span data-ttu-id="14654-117">[![보안 격리를 사용하여 Microsoft Teams 구성하기](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)</span><span class="sxs-lookup"><span data-stu-id="14654-117">[![Microsoft Teams with security isolation poster](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)</span></span>

<span data-ttu-id="14654-118">이 포스터를 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf)나 [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pptx) 형식으로 다운로드할 수 있고 편지형, 법률형, 타블로이드(11 x 17) 크기 용지에 인쇄할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-118">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="14654-119">초기 보호</span><span class="sxs-lookup"><span data-stu-id="14654-119">Initial protections</span></span>

<span data-ttu-id="14654-120">팀과 기본 SharePoint 사이트에 대한 액세스를 보호하려면 다음과 같은 모범 사례를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="14654-120">To help protect access to the team and its underlying SharePoint site, review the following best practices:</span></span>
- [<span data-ttu-id="14654-121">ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="14654-121">Identity and device access policies</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies)
- [<span data-ttu-id="14654-122">SharePoint Online 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="14654-122">SharePoint Online access policies</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)
- [<span data-ttu-id="14654-123">기준 보호를 사용하여 팀 배치하기</span><span class="sxs-lookup"><span data-stu-id="14654-123">Deploy teams with baseline protection</span></span>](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a><span data-ttu-id="14654-124">게스트 공유</span><span class="sxs-lookup"><span data-stu-id="14654-124">Guest sharing</span></span>

<span data-ttu-id="14654-125">업무 특성에 따라 이 팀에서 게스트 공유 기능을 사용하거나 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-125">Depending on the nature of your business, you may or may not want to enable guest sharing for this team.</span></span> <span data-ttu-id="14654-126">팀에서 조직 외부의 사용자와 공동 작업을 수행하려는 경우에는 게스트 공유를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="14654-126">If you do plan to collaborate with people outside your organization in the team, enable guest sharing.</span></span> 

<span data-ttu-id="14654-127">게스트와 안전하게 공유하는 방법에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14654-127">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="14654-128">파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기</span><span class="sxs-lookup"><span data-stu-id="14654-128">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [<span data-ttu-id="14654-129">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="14654-129">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

<span data-ttu-id="14654-130">게스트 공유를 허용하거나 차단하기 위해 나중에 설명할 팀의 민감도 레이블과 연결된 SharePoint 사이트의 사이트 수준 공유 제어를 조합해서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-130">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="create-a-private-team"></a><span data-ttu-id="14654-131">비공개 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="14654-131">Create a private team</span></span>

<span data-ttu-id="14654-132">이 팀을 위해 특별히 민감도 레이블을 만들고 있으므로 다음 단계는 팀을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14654-132">Since we are creating a sensitivity label specifically for this team, the next step is to create the team.</span></span> <span data-ttu-id="14654-133">기존 팀이 있는 경우 기존 팀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-133">If you have an existing team, you can use that.</span></span>

<span data-ttu-id="14654-134">중요한 정보를 위해 팀을 만들려면</span><span class="sxs-lookup"><span data-stu-id="14654-134">To create a team for sensitive information</span></span>
1. <span data-ttu-id="14654-135">Teams에서 앱 왼쪽에 있는 **Teams**를 클릭한 다음, 팀 목록 아래에서 **팀 참가 또는 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-135">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="14654-136">**팀 만들기**를 클릭합니다(첫 번째 카드, 왼쪽 위 모서리).</span><span class="sxs-lookup"><span data-stu-id="14654-136">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="14654-137">**처음부터 팀 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-137">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="14654-138">**민감도** 목록에서 기본값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-138">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="14654-139">**개인 정보 보호**에서 **비공개**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-139">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="14654-140">중요한 프로젝트와 관련된 팀의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-140">Type a name for the team that is related to your sensitive project.</span></span> <span data-ttu-id="14654-141">예를 들어 **프로젝트 Saturn**이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-141">For example, **Project Saturn**.</span></span>
7. <span data-ttu-id="14654-142">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-142">Click **Create**.</span></span>
8. <span data-ttu-id="14654-143">팀에 사용자를 추가한 다음 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-143">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="14654-144">비공개 채널 설정</span><span class="sxs-lookup"><span data-stu-id="14654-144">Private channel settings</span></span>

<span data-ttu-id="14654-145">비공개 채널 만들기를 팀 소유자로 제한하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-145">We recommend restricting creating private channels to team owners.</span></span>

<span data-ttu-id="14654-146">비공개 채널 만들기를 제한하려면</span><span class="sxs-lookup"><span data-stu-id="14654-146">To restrict private channel creation</span></span>
1. <span data-ttu-id="14654-147">팀에서 **추가 옵션**을 클릭한 다음 **팀 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-147">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="14654-148">**설정** 탭에서 **구성원 사용 권한**을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-148">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="14654-149">**구성원이 비공개 채널을 만들 수 있도록 허용** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-149">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="14654-150">[팀 정책](https://docs.microsoft.com/MicrosoftTeams/teams-policies)을 사용하여 비공개 채널을 만들 수 있는 사용자를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-150">You can also use [teams policies](https://docs.microsoft.com/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="create-a-sensitivity-label"></a><span data-ttu-id="14654-151">민감도 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="14654-151">Create a sensitivity label</span></span>

<span data-ttu-id="14654-152">보안 격리를 위해 팀을 구성하기 위해 이 팀을 위해 특별히 만든 민감도 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-152">To configure a team for security isolation, we'll be using a sensitivity label created specifically for this team.</span></span> <span data-ttu-id="14654-153">이 레이블은 팀 수준에서 게스트 공유를 제어하고 관리되지 않는 장치에서의 액세스를 차단하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14654-153">This label is used at the team level to control guest sharing and to block access from unmanaged devices.</span></span> <span data-ttu-id="14654-154">팀 소유자와 구성원만 열 수 있도록 팀의 개별 파일을 분류하고 암호화하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-154">It can also be used to classify and encrypt individual files in the team so that only team owners and members can open them.</span></span>

<span data-ttu-id="14654-155">암호화된 문서를 볼 수 있지만 편집할 수는 없는 내부 파트너 또는 관련자 그룹이 있다면 보기 전용 권한을 사용하여 레이블에 해당 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-155">If you have an internal partner or stakeholder group who should be able to view encrypted documents but not edit them, you can add them to the label with view-only permissions.</span></span> <span data-ttu-id="14654-156">그런 다음 독자 권한을 사용하여 팀의 SharePoint 사이트에 이러한 사용자를 추가할 수 있으며, 해당 사용자는 문서가 보관되는 사이트에 읽기 전용 권한으로 액세스할 수 있지만 팀 자체에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-156">You can then add these people to the team's SharePoint site with Reader permissions, and they will have read-only access to the site where the documents are kept, but not the team itself.</span></span>

<span data-ttu-id="14654-157">민감도 레이블을 만들려면</span><span class="sxs-lookup"><span data-stu-id="14654-157">To create a sensitivity label</span></span>
1. <span data-ttu-id="14654-158">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="14654-158">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="14654-159">**솔루션**에서 **정보 보호**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-159">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="14654-160">**레이블 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-160">Click **Create a label**.</span></span>
4. <span data-ttu-id="14654-161">팀 이름과 유사한 레이블 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-161">Type a name for the label that is similar to your team name.</span></span> <span data-ttu-id="14654-162">예를 들어 **매우 중요 - 프로젝트 Saturn**이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-162">For example, **Highly sensitive - Project Saturn**.</span></span>
5. <span data-ttu-id="14654-163">도구 설명을 추가한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-163">Add a tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="14654-164">**암호화** 페이지의 **암호화** 드롭다운에서 **적용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-164">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="14654-165">팀 사용 권한을 추가하려면:</span><span class="sxs-lookup"><span data-stu-id="14654-165">To add the team permissions:</span></span><br>
  <span data-ttu-id="14654-166">a.</span><span class="sxs-lookup"><span data-stu-id="14654-166">a.</span></span> <span data-ttu-id="14654-167">**사용 권한 할당**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-167">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="14654-168">b.</span><span class="sxs-lookup"><span data-stu-id="14654-168">b.</span></span> <span data-ttu-id="14654-169">**사용자 또는 그룹 추가**를 클릭하고, 만든 팀을 선택한 다음, **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-169">Click **Add users or groups**, select the team that you created, and then click **Add**</span></span><br>
  <span data-ttu-id="14654-170">c.</span><span class="sxs-lookup"><span data-stu-id="14654-170">c.</span></span> <span data-ttu-id="14654-171">**사용 권한 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-171">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="14654-172">d.</span><span class="sxs-lookup"><span data-stu-id="14654-172">d.</span></span> <span data-ttu-id="14654-173">드롭다운 목록에서 **공동 작성**을 선택한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-173">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="14654-174">레이블이 있는 파일에 읽기 전용 권한이 있는 사용자 또는 그룹 포함하기:</span><span class="sxs-lookup"><span data-stu-id="14654-174">If you want to include users or groups with read-only access to files with the label:</span></span><br>
  <span data-ttu-id="14654-175">a.</span><span class="sxs-lookup"><span data-stu-id="14654-175">a.</span></span> <span data-ttu-id="14654-176">**사용 권한 할당**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-176">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="14654-177">b.</span><span class="sxs-lookup"><span data-stu-id="14654-177">b.</span></span> <span data-ttu-id="14654-178">**사용자 또는 그룹 추가**를 클릭하고, 추가하려는 사용자 또는 그룹을 선택한 다음, **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-178">Click **Add users or groups**, select the users or groups that you want to add, and then click **Add**.</span></span><br>
  <span data-ttu-id="14654-179">c.</span><span class="sxs-lookup"><span data-stu-id="14654-179">c.</span></span> <span data-ttu-id="14654-180">**사용 권한 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-180">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="14654-181">d.</span><span class="sxs-lookup"><span data-stu-id="14654-181">d.</span></span> <span data-ttu-id="14654-182">드롭다운 목록에서 **뷰어**를 선택한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-182">Choose **Viewer** from the dropdown list, and then click **Save**.</span></span><br>
  <span data-ttu-id="14654-183">e.</span><span class="sxs-lookup"><span data-stu-id="14654-183">e.</span></span> <span data-ttu-id="14654-184">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-184">Click **Save**.</span></span>
9. <span data-ttu-id="14654-185">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-185">Click **Next**.</span></span>
10. <span data-ttu-id="14654-186">이 레이블로 분류된 파일에 머리글, 바닥글 또는 워터마크를 자동으로 추가하려는 경우 콘텐츠 표시 페이지에서 **콘텐츠 표시**를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-186">On the **Content marking** page, turn on content marking if you want to automatically add a header, footer, or watermark to files that are classified with this label.</span></span>
11. <span data-ttu-id="14654-187">**사이트 및 그룹 설정** 페이지에서 **사이트 및 그룹 설정**을 **켜짐**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-187">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
12. <span data-ttu-id="14654-188">**Office 365 그룹에 연결된 팀 사이트의 개인 정보 보호** 드롭다운에서 **비공개 - 구성원만 사이트에 액세스할 수 있음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-188">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
13. <span data-ttu-id="14654-189">게스트 액세스를 허용하려면 **Office 365 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 허용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-189">If you want to allow guest access, select the **Let Office 365 group owners add people outside the organization to the group** check box.</span></span> 
14. <span data-ttu-id="14654-190">**관리되지 않는 장치**에서 **액세스 차단**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-190">Under **Unmanaged devices**, choose **Block access**.</span></span>
15. <span data-ttu-id="14654-191">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-191">Click **Next**.</span></span>
16. <span data-ttu-id="14654-192">**Office 앱에 대한 자동 레이블 지정** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-192">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
17. <span data-ttu-id="14654-193">**제출**을 클릭한 다음 **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-193">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="14654-194">레이블을 만든 후에는 레이블을 사용할 사용자에게 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-194">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="14654-195">이 경우 팀의 사용자만 레이블을 사용할 수 있도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-195">In this case, we'll make the label available only to people in the team.</span></span>

<span data-ttu-id="14654-196">민감도 레이블을 게시하려면</span><span class="sxs-lookup"><span data-stu-id="14654-196">To publish a sensitivity label</span></span>
1. <span data-ttu-id="14654-197">Microsoft 365 규정 준수 센터의 **정보 보호** 페이지에서 **레이블 정책** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-197">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="14654-198">**레이블 게시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-198">Click **Publish labels**.</span></span>
3. <span data-ttu-id="14654-199">**민감도 레이블을 게시하도록 선택** 페이지에서 **민감도 레이블을 게시하도록 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-199">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="14654-200">만든 레이블을 선택한 다음 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-200">Select the label that you created, and then click **Add**.</span></span>
5. <span data-ttu-id="14654-201">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-201">Click **Next**.</span></span>
6. <span data-ttu-id="14654-202">사용자 및 그룹에 게시 페이지에서 **사용자 및 그룹 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-202">On the Publish to users and groups page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="14654-203">**추가**를 클릭한 다음 만든 팀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-203">Click **Add**, and then select the team that you created.</span></span>
8. <span data-ttu-id="14654-204">**추가**를 클릭한 다음 **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-204">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="14654-205">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-205">Click **Next**.</span></span>
10. <span data-ttu-id="14654-206">정책 설정 페이지에서 **사용자가 레이블이나 하위 분류 레이블을 제거하려면 정당성을 제공해야 함** 확인란을 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-206">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="14654-207">정책 이름을 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-207">Type a name for the policy, and then click **Next**.</span></span>
12. <span data-ttu-id="14654-208">**제출**을 클릭한 다음 **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-208">Click **Submit** and then click **Done**.</span></span>

## <a name="apply-the-label-to-the-team"></a><span data-ttu-id="14654-209">팀에 레이블 적용하기</span><span class="sxs-lookup"><span data-stu-id="14654-209">Apply the label to the team</span></span>

<span data-ttu-id="14654-210">레이블을 게시한 후에 게스트 공유 및 관리되는 장치 설정을 적용하려면 팀에 레이블을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-210">Once the label has been published, you must apply it to the team in order for the guest sharing and managed devices settings to take effect.</span></span> <span data-ttu-id="14654-211">SharePoint 관리 센터에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-211">This is done in the SharePoint admin center.</span></span> <span data-ttu-id="14654-212">레이블을 게시한 후 사용할 수 있을 때까지 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-212">Note, it may take some time for the label to become available after it's been published.</span></span>

<span data-ttu-id="14654-213">민감도 레이블을 적용하려면</span><span class="sxs-lookup"><span data-stu-id="14654-213">To apply the sensitivity label</span></span>
1. <span data-ttu-id="14654-214">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="14654-214">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="14654-215">**사이트**에서 **활성 사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-215">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="14654-216">팀과 연결된 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-216">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="14654-217">**정책** 탭의 **민감도**에서 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-217">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="14654-218">만든 레이블을 선택한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-218">Select the label that you created, and then click **Save**.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="14654-219">SharePoint 설정</span><span class="sxs-lookup"><span data-stu-id="14654-219">SharePoint settings</span></span>

<span data-ttu-id="14654-220">SharePoint에서 수행해야 하는 세 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-220">There are three steps to do in SharePoint:</span></span>

- <span data-ttu-id="14654-221">SharePoint 관리 센터에서 사이트에 대한 게스트 공유 설정을 업데이트하여 레이블을 만들 때 선택한 내용과 맞게 설정하고, 기본 공유 링크를 *기존 액세스가 있는 사용자*로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-221">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="14654-222">구성원이 파일, 폴더 또는 사이트를 공유하지 못하도록 사이트의 사이트 공유 설정을 업데이트하고 액세스 요청을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-222">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>
- <span data-ttu-id="14654-223">뷰어 권한으로 레이블에 사용자 또는 그룹을 추가한 경우에는 읽기 권한을 사용하여 SharePoint 사이트에 사용자 또는 그룹을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-223">If you added people or groups to the label with Viewer permissions, you can add them to the SharePoint site with Read permissions.</span></span>

### <a name="sharepoint-guest-settings"></a><span data-ttu-id="14654-224">SharePoint 게스트 공유</span><span class="sxs-lookup"><span data-stu-id="14654-224">SharePoint guest settings</span></span>

<span data-ttu-id="14654-225">레이블을 만들 때 선택한 게스트 공유 설정(팀 구성원에게만 영향을 미침)은 다음과 같이 연결된 SharePoint 사이트의 게스트 공유 설정과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-225">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="14654-226">레이블 설정</span><span class="sxs-lookup"><span data-stu-id="14654-226">Label setting</span></span>|<span data-ttu-id="14654-227">SharePoint 사이트 설정</span><span class="sxs-lookup"><span data-stu-id="14654-227">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="14654-228">**Office 365 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 허용** 선택됨</span><span class="sxs-lookup"><span data-stu-id="14654-228">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="14654-229">**신규 및 기존 게스트**(새 팀의 기본값)</span><span class="sxs-lookup"><span data-stu-id="14654-229">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="14654-230">**Office 365 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 허용** 선택 안 됨</span><span class="sxs-lookup"><span data-stu-id="14654-230">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="14654-231">**조직 내부 사용자만**</span><span class="sxs-lookup"><span data-stu-id="14654-231">**Only people in your organization**</span></span>|

<span data-ttu-id="14654-232">또한 기본 공유 링크 유형을 업데이트하여 의도한 것보다 더 많은 사용자에게 실수로 파일과 폴더를 공유하는 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="14654-232">We'll also update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span>

<span data-ttu-id="14654-233">사이트 설정을 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="14654-233">To update site settings</span></span>
1. <span data-ttu-id="14654-234">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="14654-234">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="14654-235">**사이트**에서 **활성 사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-235">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="14654-236">팀과 연결된 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-236">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="14654-237">**정책** 탭의 **외부 공유**에서 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-237">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="14654-238">중요 레이블을 만들 때 게스트 공유를 허용한 경우 **신규 및 기존 게스트**가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-238">If you allowed guest sharing when you created the sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="14654-239">레이블을 만들 때 공유를 허용하지 않은 경우 **조직 내부 사용자만**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-239">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="14654-240">기본 공유 링크 유형에서 **조직 수준 설정과 동일** 확인란을 선택 취소하고 **기존 액세스가 있는 사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-240">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="14654-241">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-241">Click **Save**.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="14654-242">비공개 채널</span><span class="sxs-lookup"><span data-stu-id="14654-242">Private channels</span></span>

<span data-ttu-id="14654-243">팀에 비공개 채널을 추가하면 각 비공개 채널이 기본 공유 설정을 포함하는 새 SharePoint 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14654-243">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="14654-244">이러한 사이트는 SharePoint 관리 센터에 표시되지 않으므로 다음 매개 변수와 함께 [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet을 사용하여 게스트 공유 설정을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-244">These sites are not visible in the SharePoint admin center, so you must use the [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet with the following parameters to update the guest sharing settings:</span></span>

- <span data-ttu-id="14654-245">게스트 공유를 해제하려면 `-SharingCapability Disabled`(기본적으로 켜져 있음)</span><span class="sxs-lookup"><span data-stu-id="14654-245">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="14654-246">기본 공유 링크를 *특정 사용자*로 변경하려면 `-DefaultSharingLinkType Internal`</span><span class="sxs-lookup"><span data-stu-id="14654-246">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

<span data-ttu-id="14654-247">팀에서 비공개 채널을 사용하지 않는 경우 팀 구성원이 [팀 설정](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc)의 **구성원 사용 권한**에서 비공개 채널을 만들 수 있는 기능을 해제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-247">If you don't plan to use private channels with your team, consider turning off the ability for team members to create them under **Member permissions** in [team settings](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc).</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="14654-248">사이트 공유 설정</span><span class="sxs-lookup"><span data-stu-id="14654-248">Site sharing settings</span></span>

<span data-ttu-id="14654-249">팀 구성원이 아닌 사용자와 SharePoint 사이트를 공유하지 못하게 하도록 이러한 공유는 소유자로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-249">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="14654-250">파일 및 폴더 공유도 팀 소유자로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-250">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="14654-251">이를 통해 파일이 팀 외부의 다른 사용자와 공유될 때마다 소유자가 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-251">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="14654-252">소유자 전용 사이트 공유를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="14654-252">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="14654-253">Teams에서 업데이트하려는 팀의 **일반** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-253">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="14654-254">팀의 도구 막대에서 **파일**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-254">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="14654-255">줄임표를 클릭한 다음 **SharePoint에서 열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-255">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="14654-256">기본 SharePoint 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-256">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="14654-257">사이트 사용 권한 창에 있는 **공유 설정**에서 **공유 설정 변경**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-257">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="14654-258">**사용 권한 공유**에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있음**을 선택한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-258">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

### <a name="custom-site-permissions"></a><span data-ttu-id="14654-259">사용자 지정 사이트 사용 권한</span><span class="sxs-lookup"><span data-stu-id="14654-259">Custom site permissions</span></span>

<span data-ttu-id="14654-260">뷰어 권한이 있는 사용자를 민감도 레이블에 추가한 경우에는 해당 사용자를 파일에 쉽게 액세스할 수 있도록 읽기 권한으로 SharePoint 사이트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-260">If you added people with Viewer permissions to the sensitivity label, you can add them to the SharePoint site with Read access so they have easy access to the files.</span></span>

<span data-ttu-id="14654-261">사이트에 사용자를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="14654-261">To add users to the site</span></span>
1. <span data-ttu-id="14654-262">사이트에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-262">In the site, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="14654-263">**사용자 초대**를 클릭한 다음 **사이트만 공유**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-263">Click **Invite people**, and then click **Share site only**.</span></span>
3. <span data-ttu-id="14654-264">초대하려는 사용자 및 그룹의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-264">Type the names of the users and groups that you want to invite.</span></span>
4. <span data-ttu-id="14654-265">추가하는 각 사용자 또는 그룹의 사용 권한을 **편집**에서 **읽기**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-265">For each person or group that you add, change their permissions from **Edit** to **Read**.</span></span>
5. <span data-ttu-id="14654-266">해당 사이트에 대한 링크가 포함된 전자 메일을 보낼 것인지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-266">Choose if you want to send them an email with a link to the site.</span></span>
6. <span data-ttu-id="14654-267">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-267">Click **Add**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="14654-268">추가 보호</span><span class="sxs-lookup"><span data-stu-id="14654-268">Additional protections</span></span>

<span data-ttu-id="14654-269">Microsoft 365에서는 콘텐츠를 보호하기 위한 추가 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-269">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="14654-270">다음 옵션이 조직의 보안을 개선하는 데 도움이 되는지 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="14654-270">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="14654-271">게스트 사용자가 [사용 약관](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)에 동의하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-271">Have your guest users agree to a [terms of use](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="14654-272">게스트 사용자에 대한 [세션 시간 초과 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-272">Configure a [session timeout policy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="14654-273">[중요한 정보 유형](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)을 만들고 [데이터 손실 방지](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)를 사용하여 중요한 정보에 액세스하는 방법에 대한 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-273">Create [sensitive information types](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) and use [data loss protection](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to set policies around accessing sensitive information.</span></span>
- <span data-ttu-id="14654-274">[Azure Active Directory 액세스](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) 검토를 사용하여 팀 액세스 및 구성원을 주기적으로 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-274">Use [Azure Active Directory access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) reviews to periodically review team access and membership.</span></span>

## <a name="drive-user-adoption-for-team-members"></a><span data-ttu-id="14654-275">팀 구성원을 위한 사용자 채택 유도하기</span><span class="sxs-lookup"><span data-stu-id="14654-275">Drive user adoption for team members</span></span>

<span data-ttu-id="14654-276">팀이 준비되면 팀 구성원에게 팀과 추가 보안 기능의 채택을 유도할 시점입니다.</span><span class="sxs-lookup"><span data-stu-id="14654-276">With the team in place, it's time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="train-your-users"></a><span data-ttu-id="14654-277">사용자 교육하기</span><span class="sxs-lookup"><span data-stu-id="14654-277">Train your users</span></span>

<span data-ttu-id="14654-278">팀의 구성원은 채팅, 모임 및 기타 앱을 포함하여 팀과 모든 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-278">Members of the team can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="14654-279">채널의 **파일** 섹션에서 파일에 대한 작업을 하는 경우, 팀의 구성원은 만든 파일에 민감도 레이블을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-279">When working with files from the **Files** section of a channel, members of the team should assign the sensitivity label to the files they create.</span></span>

<span data-ttu-id="14654-280">레이블이 파일에 적용되면 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="14654-280">When the label gets applied to the file, it is encrypted.</span></span> <span data-ttu-id="14654-281">팀의 구성원은 실시간으로 파일을 열고 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-281">Members of the team can open it and collaborate in real time.</span></span> <span data-ttu-id="14654-282">파일이 사이트를 떠나 악의적인 사용자에게 전달되는 경우, 파일을 열고 콘텐츠를 보려면 팀의 구성원인 사용자 계정의 자격 증명을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-282">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the team to open the file and view its contents.</span></span> 

<span data-ttu-id="14654-283">팀 구성원 교육하기:</span><span class="sxs-lookup"><span data-stu-id="14654-283">Train your team members:</span></span>

- <span data-ttu-id="14654-284">채팅, 모임, 파일 및 SharePoint 사이트의 기타 리소스를 위한 새 팀 사용의 중요성 및 높은 규제 대상의 데이터 유출 결과(예: 법적 영향, 규제 벌금, 랜섬웨어 또는 경쟁적 우위 박탈)</span><span class="sxs-lookup"><span data-stu-id="14654-284">On the importance of using the new team for chats, meetings, files, and the other resources of the SharePoint site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="14654-285">팀에 액세스 하는 방법</span><span class="sxs-lookup"><span data-stu-id="14654-285">How to access the team.</span></span>
- <span data-ttu-id="14654-286">사이트에서 새 파일을 만들고 로컬에 저장된 새 파일을 업로드하는 방법</span><span class="sxs-lookup"><span data-stu-id="14654-286">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="14654-287">팀에 대한 올바른 민감도 레이블을 사용하여 파일에 레이블을 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="14654-287">How to label files with the correct sensitivity label for the team.</span></span>
- <span data-ttu-id="14654-288">파일이 사이트 외부로 유출된 경우에도 레이블이 파일을 보호하는 방법</span><span class="sxs-lookup"><span data-stu-id="14654-288">How the label protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="14654-289">이 교육에는 팀 구성원이 이러한 기능과 해당 결과를 경험해볼 수 있도록 하기 위한 실무 위주의 연습이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-289">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="14654-290">정기적인 사용 현황 검토 및 팀 구성원 피드백 처리하기</span><span class="sxs-lookup"><span data-stu-id="14654-290">Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="14654-291">교육 후 몇 주 안에:</span><span class="sxs-lookup"><span data-stu-id="14654-291">In the weeks after training:</span></span>

- <span data-ttu-id="14654-292">팀 구성원의 피드백을 신속하게 처리하고 정책과 구성을 세부적으로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-292">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="14654-293">팀의 사용 현황을 분석하고 예상 사용 현황과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-293">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="14654-294">높은 규제 대상 파일에 적절한 민감도 레이블이 지정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-294">Verify that highly regulated files have been properly labeled with the sensitivity label.</span></span> <span data-ttu-id="14654-295">SharePoint에서 폴더를 보고 **열 추가**의 **열 표시/숨기기** 옵션을 통해 **민감도** 열을 추가하여 레이블이 할당된 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14654-295">(You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="14654-296">필요에 따라 사용자를 재교육합니다.</span><span class="sxs-lookup"><span data-stu-id="14654-296">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="14654-297">기타 참고 항목</span><span class="sxs-lookup"><span data-stu-id="14654-297">See also</span></span>

[<span data-ttu-id="14654-298">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="14654-298">Azure AD Privileged Identity Management</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)