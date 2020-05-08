---
title: 매우 중요한 데이터를 보호하는 팀 구성하기
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365solutions
ms.custom:
- Ent_Solutions
description: 매우 중요한 데이터를 보호하는 팀을 배치하는 방법에 대해 알아봅니다.
ms.openlocfilehash: f60c46c3b596c131bb04a49f0293c6dd8bbbea2b
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166176"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a><span data-ttu-id="af556-103">매우 중요한 데이터를 보호하는 팀 구성하기</span><span class="sxs-lookup"><span data-stu-id="af556-103">Configure teams with protection for highly sensitive data</span></span>

<span data-ttu-id="af556-104">이 문서에서는 매우 중요한 수준의 보호를 위해 팀을 설정하는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-104">In this article, we look at setting up a team for a highly sensitive level of protection.</span></span> <span data-ttu-id="af556-105">이 문서의 단계를 수행하기 전에 [기준 보호를 사용하여 팀 배치하기](configure-teams-baseline-protection.md) 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span>

<span data-ttu-id="af556-106">이 보호 계층에서는 조직 전체에서 매우 중요한 팀과 파일에 대해 사용할 수 있는 민감도 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af556-106">For this tier of protection, we create a sensitivity label that can be used across your organization for highly sensitive teams and files.</span></span> <span data-ttu-id="af556-107">사용자가 지정한 조직의 구성원과 게스트만 이 레이블을 사용하는 파일을 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-107">Only members of your organization and guests that you have specified will be able to decrypt files that use this label.</span></span> <span data-ttu-id="af556-108">특정 팀의 멤버만 파일을 해독할 수 있도록 권한을 추가로 분리해야 하는 경우에는 [보안 격리를 사용하여 팀 배치하기](secure-teams-security-isolation.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af556-108">If you need to further isolate permissions so that only members of a specific team can decrypt files, see  [Deploy a team with security isolation](secure-teams-security-isolation.md).</span></span>

<span data-ttu-id="af556-109">매우 중요 계층에서는 초기 계층에 대한 다음과 같은 추가 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-109">The highly sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="af556-110">게스트 공유를 설정하거나 해제하고 관리되지 않는 장치의 SharePoint 콘텐츠에 대한 액세스를 웹 전용으로 제한하는 팀의 민감도 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="af556-110">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices.</span></span> <span data-ttu-id="af556-111">이 레이블은 파일을 분류하고 암호화하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-111">This label can also be used to classify and encrypt files.</span></span>
- <span data-ttu-id="af556-112">더욱 제한적인 기본 공유 링크 유형</span><span class="sxs-lookup"><span data-stu-id="af556-112">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="af556-113">팀 소유자만 비공개 채널을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-113">Only team owners can create private channels.</span></span>
- <span data-ttu-id="af556-114">연결된 SharePoint 사이트에 대한 액세스 요청은 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-114">Access requests for the associated SharePoint site are turned off.</span></span>

## <a name="guest-sharing"></a><span data-ttu-id="af556-115">게스트 공유</span><span class="sxs-lookup"><span data-stu-id="af556-115">Guest sharing</span></span>

<span data-ttu-id="af556-116">업무 특성에 따라 매우 중요한 데이터를 포함하는 팀에서 게스트 공유 기능을 사용하거나 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-116">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain highly sensitive data.</span></span> <span data-ttu-id="af556-117">팀에서 조직 외부의 사용자와 공동 작업을 수행하려는 경우에는 게스트 공유를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-117">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="af556-118">Microsoft 365에는 중요한 콘텐츠를 안전하게 공유하는 데 도움이 되는 다양한 보안 및 규정 준수 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-118">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="af556-119">이는 일반적으로 콘텐츠를 직접 조직 외부의 사용자에게 전자 메일로 보내는 것보다 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-119">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="af556-120">게스트와 안전하게 공유하는 방법에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af556-120">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="af556-121">파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기</span><span class="sxs-lookup"><span data-stu-id="af556-121">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [<span data-ttu-id="af556-122">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="af556-122">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

<span data-ttu-id="af556-123">게스트 공유를 허용하거나 차단하기 위해 나중에 설명할 팀의 민감도 레이블과 연결된 SharePoint 사이트의 사이트 수준 공유 제어를 조합해서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-123">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="af556-124">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="af556-124">Sensitivity labels</span></span>

<span data-ttu-id="af556-125">매우 중요한 수준의 보호를 위해서는 팀을 분류하는 데 민감도 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-125">For the highly sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="af556-126">이 레이블은 이 파일이나 다른 팀 또는 SharePoint나 OneDrive와 같은 다른 파일 위치의 개별 파일을 분류하고 암호화하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-126">This label can also be used to classify and encrypt individual files in this or other teams or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="af556-127">첫 번째 단계로 Teams에서 민감도 레이블을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-127">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="af556-128">자세한 내용은 [Microsoft Teams, Office 365 그룹 및 SharePoint 사이트에서 민감도 레이블 사용하여 콘텐츠 보호하기](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af556-128">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) for details.</span></span>

<span data-ttu-id="af556-129">조직에 이미 민감도 레이블을 배포한 경우 이 레이블이 전체 레이블 전략에 어떻게 적합한지 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="af556-129">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="af556-130">조직의 요구 사항을 충족하는 데 필요한 경우 이름이나 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-130">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="af556-131">Teams에서 민감도 레이블을 사용하도록 설정한 후 다음 단계는 레이블을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="af556-131">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="af556-132">민감도 레이블을 만들려면</span><span class="sxs-lookup"><span data-stu-id="af556-132">To create a sensitivity label</span></span>
1. <span data-ttu-id="af556-133">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="af556-133">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="af556-134">**솔루션**에서 **정보 보호**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-134">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="af556-135">**레이블 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-135">Click **Create a label**.</span></span>
4. <span data-ttu-id="af556-136">레이블에 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-136">Give the label a name.</span></span> <span data-ttu-id="af556-137">**매우 중요**로 설정하는 것이 좋지만, 이미 사용 중인 다른 이름을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-137">We suggest **Highly sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="af556-138">도구 설명을 추가한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-138">Add a tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="af556-139">**암호화** 페이지의 **암호화** 드롭다운에서 **적용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-139">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="af556-140">**특정 사용자 및 그룹에 대한 사용 권한 할당**에서 **사용 권한 할당**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-140">Under **Assign permissions to specific users and groups**, click **Assign permissions**.</span></span>
8. <span data-ttu-id="af556-141">**조직의 모든 사용자 및 그룹 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-141">Click **Add all users and groups in your organization**.</span></span>
9. <span data-ttu-id="af556-142">파일의 암호를 해독할 수 있는 권한이 있어야 하는 게스트 사용자가 있는 경우 **사용자 또는 그룹 추가**를 클릭하여 게스트 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-142">If there are guest users who should have permissions to decrypt files, click **Add users or groups** and add them.</span></span>
10.  <span data-ttu-id="af556-143">**저장**을 클릭한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-143">Click **Save**, and then click **Next**.</span></span>
11. <span data-ttu-id="af556-144">이 레이블로 분류된 파일에 머리글, 바닥글 또는 워터마크를 자동으로 추가하려는 경우 콘텐츠 표시 페이지에서 **콘텐츠 표시**를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-144">On the **Content marking** page, turn on content marking if you want to automatically add a header, footer, or watermark to files that are classified with this label.</span></span>
12. <span data-ttu-id="af556-145">**사이트 및 그룹 설정** 페이지에서 **사이트 및 그룹 설정**을 **켜짐**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-145">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
13. <span data-ttu-id="af556-146">**Office 365 그룹에 연결된 팀 사이트의 개인 정보 보호** 드롭다운에서 **비공개 - 구성원만 사이트에 액세스할 수 있음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-146">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
14. <span data-ttu-id="af556-147">게스트 액세스를 허용하려면 **Office 365 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 허용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-147">If you want to allow guest access, select the **Let Office 365 group owners add people outside the organization to the group** check box.</span></span> 
15. <span data-ttu-id="af556-148">**관리되지 않는 장치**에서 **액세스 차단**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-148">Under **Unmanaged devices**, choose **Block access**.</span></span>
16. <span data-ttu-id="af556-149">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-149">Click **Next**.</span></span>
17. <span data-ttu-id="af556-150">**Office 앱에 대한 자동 레이블 지정** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-150">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
18. <span data-ttu-id="af556-151">**제출**을 클릭한 다음 **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-151">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="af556-152">레이블을 만든 후에는 레이블을 사용할 사용자에게 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-152">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="af556-153">민감한 보호를 위해 모든 사용자가 레이블을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-153">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="af556-154">Microsoft 365 규정 준수 센터에서 **정보 보호** 페이지의 **레이블 정책** 탭에서 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-154">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="af556-155">모든 사용자에게 적용되는 기존 정책이 있다면 해당 정책에 이 레이블을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-155">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="af556-156">새 정책을 만들어야 한다면 [레이블 정책을 만들어 민감도 레이블 게시하기](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af556-156">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="af556-157">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="af556-157">Create a team</span></span>

<span data-ttu-id="af556-158">매우 중요한 시나리오의 추가 구성은 팀과 연결된 SharePoint 사이트에서 수행되므로 다음 단계는 팀을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="af556-158">Further configuration of the highly sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="af556-159">매우 중요한 정보를 위해 팀을 만들려면</span><span class="sxs-lookup"><span data-stu-id="af556-159">To create a team for highly sensitive information</span></span>
1. <span data-ttu-id="af556-160">Teams에서 앱 왼쪽에 있는 **Teams**를 클릭한 다음, 팀 목록 아래에서 **팀 참가 또는 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-160">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="af556-161">**팀 만들기**를 클릭합니다(첫 번째 카드, 왼쪽 위 모서리).</span><span class="sxs-lookup"><span data-stu-id="af556-161">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="af556-162">**처음부터 팀 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-162">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="af556-163">**민감도** 목록에서 방금 만든 **매우 중요** 레이블을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-163">In the **Sensitivity** list, choose the **Highly sensitive** label that you just created.</span></span>
5. <span data-ttu-id="af556-164">**개인 정보 보호**에서 **비공개**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-164">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="af556-165">팀 이름을 입력한 다음 **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-165">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="af556-166">팀에 사용자를 추가한 다음 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-166">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="af556-167">비공개 채널 설정</span><span class="sxs-lookup"><span data-stu-id="af556-167">Private channel settings</span></span>

<span data-ttu-id="af556-168">이 계층에서는 비공개 채널 만들기를 팀 소유자로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-168">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="af556-169">비공개 채널 만들기를 제한하려면</span><span class="sxs-lookup"><span data-stu-id="af556-169">To restrict private channel creation</span></span>
1. <span data-ttu-id="af556-170">팀에서 **추가 옵션**을 클릭한 다음 **팀 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-170">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="af556-171">**설정** 탭에서 **구성원 사용 권한**을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-171">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="af556-172">**구성원이 비공개 채널을 만들 수 있도록 허용** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-172">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="af556-173">[팀 정책](https://docs.microsoft.com/MicrosoftTeams/teams-policies)을 사용하여 비공개 채널을 만들 수 있는 사용자를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-173">You can also use [teams policies](https://docs.microsoft.com/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="af556-174">SharePoint 설정</span><span class="sxs-lookup"><span data-stu-id="af556-174">SharePoint settings</span></span>

<span data-ttu-id="af556-175">매우 중요 레이블을 사용하여 새 팀을 만들 때마다 SharePoint에서 다음 두 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-175">Each time you create a new team with the highly sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="af556-176">SharePoint 관리 센터에서 사이트에 대한 게스트 공유 설정을 업데이트하여 레이블을 만들 때 선택한 내용과 맞게 설정하고, 기본 공유 링크를 *기존 액세스가 있는 사용자*로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-176">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="af556-177">구성원이 파일, 폴더 또는 사이트를 공유하지 못하도록 사이트의 사이트 공유 설정을 업데이트하고 액세스 요청을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-177">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>

### <a name="site-guest-sharing-settings"></a><span data-ttu-id="af556-178">사이트 게스트 공유 설정</span><span class="sxs-lookup"><span data-stu-id="af556-178">Site guest sharing settings</span></span>

<span data-ttu-id="af556-179">레이블을 만들 때 선택한 게스트 공유 설정(팀 구성원에게만 영향을 미침)은 다음과 같이 연결된 SharePoint 사이트의 게스트 공유 설정과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-179">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="af556-180">레이블 설정</span><span class="sxs-lookup"><span data-stu-id="af556-180">Label setting</span></span>|<span data-ttu-id="af556-181">SharePoint 사이트 설정</span><span class="sxs-lookup"><span data-stu-id="af556-181">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="af556-182">**Office 365 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 허용** 선택됨</span><span class="sxs-lookup"><span data-stu-id="af556-182">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="af556-183">**신규 및 기존 게스트**(새 팀의 기본값)</span><span class="sxs-lookup"><span data-stu-id="af556-183">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="af556-184">**Office 365 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 허용** 선택 안 됨</span><span class="sxs-lookup"><span data-stu-id="af556-184">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="af556-185">**조직 내부 사용자만**</span><span class="sxs-lookup"><span data-stu-id="af556-185">**Only people in your organization**</span></span>|

<span data-ttu-id="af556-186">사이트 설정을 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="af556-186">To update site settings</span></span>
1. <span data-ttu-id="af556-187">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="af556-187">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="af556-188">**사이트**에서 **활성 사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-188">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="af556-189">팀과 연결된 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-189">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="af556-190">**정책** 탭의 **외부 공유**에서 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-190">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="af556-191">매우 중요 레이블을 만들 때 게스트 공유를 허용한 경우 **신규 및 기존 게스트**가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-191">If you allowed guest sharing when you created the Highly sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="af556-192">레이블을 만들 때 공유를 허용하지 않은 경우 **조직 내부 사용자만**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-192">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="af556-193">기본 공유 링크 유형에서 **조직 수준 설정과 동일** 확인란을 선택 취소하고 **기존 액세스가 있는 사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-193">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="af556-194">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-194">Click **Save**.</span></span>

<span data-ttu-id="af556-195">팀 만들기 프로세스의 일부로 이를 스크립팅하려면 다음 매개 변수와 함께 [Set-Get-sposite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-195">If you want to script this as part of your team creation process, you can use [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) with the following parameters:</span></span>

- <span data-ttu-id="af556-196">게스트 공유를 해제하려면 `-SharingCapability Disabled`(기본적으로 켜져 있음)</span><span class="sxs-lookup"><span data-stu-id="af556-196">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="af556-197">기본 공유 링크를 *특정 사용자*로 변경하려면 `-DefaultSharingLinkType Internal`</span><span class="sxs-lookup"><span data-stu-id="af556-197">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

#### <a name="private-channels"></a><span data-ttu-id="af556-198">비공개 채널</span><span class="sxs-lookup"><span data-stu-id="af556-198">Private channels</span></span>

<span data-ttu-id="af556-199">팀에 비공개 채널을 추가하면 각 비공개 채널이 기본 공유 설정을 포함하는 새 SharePoint 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af556-199">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="af556-200">이러한 사이트는 SharePoint 관리 센터에 표시되지 않으므로 Set-SPOSite PowerShell cmdlet을 사용하여 게스트 공유 설정을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-200">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="af556-201">사이트 공유 설정</span><span class="sxs-lookup"><span data-stu-id="af556-201">Site sharing settings</span></span>

<span data-ttu-id="af556-202">팀 구성원이 아닌 사용자와 SharePoint 사이트를 공유하지 못하게 하도록 이러한 공유는 소유자로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-202">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="af556-203">파일 및 폴더 공유도 팀 소유자로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-203">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="af556-204">이를 통해 파일이 팀 외부의 다른 사용자와 공유될 때마다 소유자가 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af556-204">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="af556-205">소유자 전용 사이트 공유를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="af556-205">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="af556-206">Teams에서 업데이트하려는 팀의 **일반** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-206">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="af556-207">팀의 도구 막대에서 **파일**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-207">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="af556-208">줄임표를 클릭한 다음 **SharePoint에서 열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-208">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="af556-209">기본 SharePoint 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-209">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="af556-210">사이트 사용 권한 창에 있는 **공유 설정**에서 **공유 설정 변경**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-210">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="af556-211">**사용 권한 공유**에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-211">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
7. <span data-ttu-id="af556-212">**액세스 요청 허용**을 **꺼짐**으로 설정한 다음, **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af556-212">Set **Allow access requests** to **Off**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="af556-213">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af556-213">See Also</span></span>

[<span data-ttu-id="af556-214">민감도 레이블과 해당 정책 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="af556-214">Create and configure sensitivity labels and their policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)

