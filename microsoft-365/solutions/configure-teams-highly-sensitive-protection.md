---
title: 매우 중요한 데이터를 보호하는 팀 구성하기
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
recommendations: false
description: 매우 중요한 데이터를 보호하는 팀을 배치하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d83c10df50d02f47a6d70ee80b2ddbf89fff37d0
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538198"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a><span data-ttu-id="7693f-103">매우 중요한 데이터를 보호하는 팀 구성하기</span><span class="sxs-lookup"><span data-stu-id="7693f-103">Configure teams with protection for highly sensitive data</span></span>

<span data-ttu-id="7693f-104">이 문서에서는 매우 중요한 수준의 보호를 위해 팀을 설정하는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-104">In this article, we look at setting up a team for a highly sensitive level of protection.</span></span> <span data-ttu-id="7693f-105">이 문서의 단계를 수행하기 전에 [기준 보호를 사용하여 팀 배치하기](configure-teams-baseline-protection.md) 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span>

<span data-ttu-id="7693f-106">이 보호 계층에서는 조직 전체에서 매우 중요한 팀과 파일에 대해 사용할 수 있는 민감도 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-106">For this tier of protection, we create a sensitivity label that can be used across your organization for highly sensitive teams and files.</span></span> <span data-ttu-id="7693f-107">사용자가 지정한 조직의 구성원과 게스트만 이 레이블을 사용하는 파일을 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-107">Only members of your organization and guests that you have specified will be able to decrypt files that use this label.</span></span> <span data-ttu-id="7693f-108">특정 팀의 멤버만 파일을 해독할 수 있도록 권한을 추가로 분리해야 하는 경우에는 [보안 격리를 사용하여 팀 배치하기](secure-teams-security-isolation.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7693f-108">If you need to further isolate permissions so that only members of a specific team can decrypt files, see  [Deploy a team with security isolation](secure-teams-security-isolation.md).</span></span>

<span data-ttu-id="7693f-109">매우 중요 계층에서는 초기 계층에 대한 다음과 같은 추가 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-109">The highly sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="7693f-p103">게스트 공유를 설정하거나 해제하고 관리되지 않는 장치의 SharePoint 콘텐츠에 대한 액세스를 제한하는 팀의 민감도 레이블입니다. 이 레이블은 파일을 분류하고 암호화하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-p103">A sensitivity label for the team that allows you to turn guest sharing on or off and blocks access to SharePoint content for unmanaged devices. This label can also be used to classify and encrypt files.</span></span>
- <span data-ttu-id="7693f-112">더욱 제한적인 기본 공유 링크 유형</span><span class="sxs-lookup"><span data-stu-id="7693f-112">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="7693f-113">팀 소유자만 비공개 채널을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-113">Only team owners can create private channels.</span></span>
- <span data-ttu-id="7693f-114">연결된 SharePoint 사이트에 대한 액세스 요청은 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-114">Access requests for the associated SharePoint site are turned off.</span></span>

## <a name="guest-sharing"></a><span data-ttu-id="7693f-115">게스트 공유</span><span class="sxs-lookup"><span data-stu-id="7693f-115">Guest sharing</span></span>

<span data-ttu-id="7693f-116">업무 특성에 따라 매우 중요한 데이터를 포함하는 팀에서 게스트 공유 기능을 사용하거나 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-116">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain highly sensitive data.</span></span> <span data-ttu-id="7693f-117">팀에서 조직 외부의 사용자와 공동 작업을 수행하려는 경우에는 게스트 공유를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-117">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="7693f-118">Microsoft 365에는 중요한 콘텐츠를 안전하게 공유하는 데 도움이 되는 다양한 보안 및 규정 준수 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-118">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="7693f-119">이는 일반적으로 콘텐츠를 직접 조직 외부의 사용자에게 전자 메일로 보내는 것보다 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-119">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="7693f-120">게스트와 안전하게 공유하는 방법에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7693f-120">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="7693f-121">파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기</span><span class="sxs-lookup"><span data-stu-id="7693f-121">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="7693f-122">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="7693f-122">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="7693f-123">게스트 공유를 허용하거나 차단하기 위해 나중에 설명할 팀의 민감도 레이블과 연결된 SharePoint 사이트의 사이트 수준 공유 제어를 조합해서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-123">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="7693f-124">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="7693f-124">Sensitivity labels</span></span>

<span data-ttu-id="7693f-125">매우 중요한 수준의 보호를 위해서는 팀을 분류하는 데 민감도 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-125">For the highly sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="7693f-126">이 레이블은 이 파일이나 다른 팀 또는 SharePoint나 OneDrive와 같은 다른 파일 위치의 개별 파일을 분류하고 암호화하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-126">This label can also be used to classify and encrypt individual files in this or other teams or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="7693f-127">첫 번째 단계로 Teams에서 민감도 레이블을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-127">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="7693f-128">자세한 내용은 [Microsoft Teams, Office 365 그룹 및 SharePoint 사이트에서 민감도 레이블 사용하여 콘텐츠 보호하기](../compliance/sensitivity-labels-teams-groups-sites.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7693f-128">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="7693f-129">조직에 이미 민감도 레이블을 배포한 경우 이 레이블이 전체 레이블 전략에 어떻게 적합한지 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="7693f-129">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="7693f-130">조직의 요구 사항을 충족하는 데 필요한 경우 이름이나 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-130">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="7693f-131">Teams에서 민감도 레이블을 사용하도록 설정한 후 다음 단계는 레이블을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-131">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="7693f-132">민감도 레이블을 만들려면</span><span class="sxs-lookup"><span data-stu-id="7693f-132">To create a sensitivity label</span></span>
1. <span data-ttu-id="7693f-133">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-133">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="7693f-134">**솔루션** 에서 **정보 보호** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-134">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="7693f-135">**레이블 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-135">Click **Create a label**.</span></span>
4. <span data-ttu-id="7693f-136">레이블에 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-136">Give the label a name.</span></span> <span data-ttu-id="7693f-137">**매우 중요** 로 설정하는 것이 좋지만, 이미 사용 중인 다른 이름을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-137">We suggest **Highly sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="7693f-138">표시 이름과 설명을 추가하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-138">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="7693f-139">**이 레이블에 대한 범위 정의 페이지** 에서 **파일 및 전자 메일** 과 **그룹 및 사이트** 를 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-139">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="7693f-140">**파일 및 전자 메일에 대한 보호 설정 선택** 페이지에서 **파일 및 전자 메일 암호화** 를 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-140">On the **Choose protection settings for files and emails** page, select **Encrypt files and emails**, and then click **Next**.</span></span>
8. <span data-ttu-id="7693f-141">**암호화** 페이지에서 **암호화 설정 구성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-141">On the **Encryption** page, choose **Configure encryption settings**.</span></span>
9. <span data-ttu-id="7693f-142">**특정 사용자 및 그룹에 대한 사용 권한 할당** 에서 **사용 권한 할당** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-142">Under **Assign permissions to specific users and groups**, click **Assign permissions**.</span></span>
10. <span data-ttu-id="7693f-143">**조직의 모든 사용자 및 그룹 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-143">Click **Add all users and groups in your organization**.</span></span>
11. <span data-ttu-id="7693f-144">파일의 암호를 해독할 수 있는 권한이 있어야 하는 게스트가 있는 경우 **사용자 또는 그룹 추가** 를 클릭하여 게스트 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-144">If there are guests who should have permissions to decrypt files, click **Add users or groups** and add them.</span></span>
12.  <span data-ttu-id="7693f-145">**저장** 을 클릭한 다음 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-145">Click **Save**, and then click **Next**.</span></span>
13. <span data-ttu-id="7693f-146">*파일 및 전자 메일에 자동 레이블 지정*\* 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-146">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
14. <span data-ttu-id="7693f-147">**그룹 및 사이트에 대한 보호 설정 정의** 페이지에서 **개인 정보 및 외부 사용자 액세스 설정** 과 **장치 액세스 및 외부 공유 설정** 을 선택 하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-147">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
15. <span data-ttu-id="7693f-148">**개인 정보 및 외부 사용자 액세스 설정 정의** 페이지의 **개인 정보** 에서 **개인 정보 보호** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-148">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
16. <span data-ttu-id="7693f-149">게스트 액세스를 허용하려면 **외부 사용자 액세스** 에서 **Microsoft 365 그룹 소유자가 조직 외부의 사용자를 그룹에 게스트로 추가하도록 허용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-149">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
17. <span data-ttu-id="7693f-150">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-150">Click **Next**.</span></span>
18. <span data-ttu-id="7693f-151">**외부 공유 및 장치 액세스 설정 정의** 페이지에서 **레이블이 지정된 SharePoint 사이트에서 외부 공유를 제어** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-151">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
19. <span data-ttu-id="7693f-152">**콘텐츠를 함께 공유할 수 있습니다** 에서 게스트 액세스를 허용하는 경우에는 **신규 및 기존의 게스트** 를 선택하고, 그렇지 않은 경우 **조직에 있는 사용자만** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-152">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
20. <span data-ttu-id="7693f-153">**관리되지 않는 장치** 에서 **액세스 차단** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-153">Under **Access from unmanaged devices**, choose **Block access**.</span></span> <span data-ttu-id="7693f-154">(게스트를 허용하고 관리 장치가 없는 경우 **제한된 웹 전용 액세스 허용** 을 선택할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="7693f-154">(If you're allowing guests and they don't have managed devices, you may want to choose **Allow limited, web-only access**.)</span></span>
21. <span data-ttu-id="7693f-155">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-155">Click **Next**.</span></span>
22. <span data-ttu-id="7693f-156">**Office 앱에 대한 자동 레이블 지정** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-156">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
23. <span data-ttu-id="7693f-157">**레이블 만들기** 를 클릭한 다음 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-157">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="7693f-158">레이블을 만든 후에는 레이블을 사용할 사용자에게 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-158">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="7693f-159">민감한 보호를 위해 모든 사용자가 레이블을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-159">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="7693f-160">Microsoft 365 규정 준수 센터에서 **정보 보호** 페이지의 **레이블 정책** 탭에서 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-160">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="7693f-161">모든 사용자에게 적용되는 기존 정책이 있다면 해당 정책에 이 레이블을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-161">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="7693f-162">새 정책을 만들어야 한다면 [레이블 정책을 만들어 민감도 레이블 게시하기](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7693f-162">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="7693f-163">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="7693f-163">Create a team</span></span>

<span data-ttu-id="7693f-164">매우 중요한 시나리오의 추가 구성은 팀과 연결된 SharePoint 사이트에서 수행되므로 다음 단계는 팀을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-164">Further configuration of the highly sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="7693f-165">매우 중요한 정보를 위해 팀을 만들려면</span><span class="sxs-lookup"><span data-stu-id="7693f-165">To create a team for highly sensitive information</span></span>
1. <span data-ttu-id="7693f-166">Teams에서 앱 왼쪽에 있는 **Teams** 를 클릭한 다음, 팀 목록 아래에서 **팀 참가 또는 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-166">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="7693f-167">**팀 만들기** 를 클릭합니다(첫 번째 카드, 왼쪽 위 모서리).</span><span class="sxs-lookup"><span data-stu-id="7693f-167">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="7693f-168">**처음부터 팀 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-168">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="7693f-169">**민감도** 목록에서 방금 만든 **매우 중요** 레이블을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-169">In the **Sensitivity** list, choose the **Highly sensitive** label that you just created.</span></span>
5. <span data-ttu-id="7693f-170">**개인 정보 보호** 에서 **비공개** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-170">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="7693f-171">팀 이름을 입력한 다음 **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-171">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="7693f-172">팀에 사용자를 추가한 다음 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-172">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="7693f-173">비공개 채널 설정</span><span class="sxs-lookup"><span data-stu-id="7693f-173">Private channel settings</span></span>

<span data-ttu-id="7693f-174">이 계층에서는 비공개 채널 만들기를 팀 소유자로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-174">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="7693f-175">비공개 채널 만들기를 제한하려면</span><span class="sxs-lookup"><span data-stu-id="7693f-175">To restrict private channel creation</span></span>
1. <span data-ttu-id="7693f-176">팀에서 **추가 옵션** 을 클릭한 다음 **팀 관리** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-176">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="7693f-177">**설정** 탭에서 **구성원 사용 권한** 을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-177">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="7693f-178">**구성원이 비공개 채널을 만들 수 있도록 허용** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-178">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="7693f-179">[팀 정책](/MicrosoftTeams/teams-policies)을 사용하여 비공개 채널을 만들 수 있는 사용자를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-179">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="7693f-180">SharePoint 설정</span><span class="sxs-lookup"><span data-stu-id="7693f-180">SharePoint settings</span></span>

<span data-ttu-id="7693f-181">매우 중요 레이블을 사용하여 새 팀을 만들 때마다 SharePoint에서 다음 두 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-181">Each time you create a new team with the highly sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="7693f-182">SharePoint 관리 센터에서 사이트에 대한 게스트 공유 설정을 업데이트하여 레이블을 만들 때 선택한 내용과 맞게 설정하고, 기본 공유 링크를 *기존 액세스가 있는 사용자* 로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-182">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="7693f-183">구성원이 파일, 폴더 또는 사이트를 공유하지 못하도록 사이트의 사이트 공유 설정을 업데이트하고 액세스 요청을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-183">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>

### <a name="site-guest-sharing-settings"></a><span data-ttu-id="7693f-184">사이트 게스트 공유 설정</span><span class="sxs-lookup"><span data-stu-id="7693f-184">Site guest sharing settings</span></span>

<span data-ttu-id="7693f-185">레이블을 만들 때 선택한 게스트 공유 설정(팀 구성원에게만 영향을 미침)은 다음과 같이 연결된 SharePoint 사이트의 게스트 공유 설정과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-185">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="7693f-186">레이블 설정</span><span class="sxs-lookup"><span data-stu-id="7693f-186">Label setting</span></span>|<span data-ttu-id="7693f-187">SharePoint 사이트 설정</span><span class="sxs-lookup"><span data-stu-id="7693f-187">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="7693f-188">**Office 365 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 허용** 선택됨</span><span class="sxs-lookup"><span data-stu-id="7693f-188">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="7693f-189">**신규 및 기존 게스트**(새 팀의 기본값)</span><span class="sxs-lookup"><span data-stu-id="7693f-189">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="7693f-190">**Office 365 그룹 소유자가 조직 외부의 사용자를 그룹에 추가할 수 있도록 허용** 선택 안 됨</span><span class="sxs-lookup"><span data-stu-id="7693f-190">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="7693f-191">**조직 내부 사용자만**</span><span class="sxs-lookup"><span data-stu-id="7693f-191">**Only people in your organization**</span></span>|

<span data-ttu-id="7693f-192">사이트 설정을 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="7693f-192">To update site settings</span></span>
1. <span data-ttu-id="7693f-193">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-193">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="7693f-194">**사이트** 에서 **활성 사이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-194">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="7693f-195">팀과 연결된 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-195">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="7693f-196">**정책** 탭의 **외부 공유** 에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-196">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="7693f-197">매우 중요 레이블을 만들 때 게스트 공유를 허용한 경우 **신규 및 기존 게스트** 가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-197">If you allowed guest sharing when you created the Highly sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="7693f-198">레이블을 만들 때 공유를 허용하지 않은 경우 **조직 내부 사용자만** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-198">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="7693f-199">기본 공유 링크 유형에서 **조직 수준 설정과 동일** 확인란을 선택 취소하고 **기존 액세스가 있는 사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-199">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="7693f-200">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-200">Click **Save**.</span></span>

<span data-ttu-id="7693f-201">팀 만들기 프로세스의 일부로 이를 스크립팅하려면 다음 매개 변수와 함께 [Set-Get-sposite](/powershell/module/sharepoint-online/set-sposite)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-201">If you want to script this as part of your team creation process, you can use [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) with the following parameters:</span></span>

- <span data-ttu-id="7693f-202">게스트 공유를 해제하려면 `-SharingCapability Disabled`(기본적으로 켜져 있음)</span><span class="sxs-lookup"><span data-stu-id="7693f-202">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="7693f-203">기본 공유 링크를 *특정 사용자* 로 변경하려면 `-DefaultSharingLinkType Internal`</span><span class="sxs-lookup"><span data-stu-id="7693f-203">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

#### <a name="private-channels"></a><span data-ttu-id="7693f-204">비공개 채널</span><span class="sxs-lookup"><span data-stu-id="7693f-204">Private channels</span></span>

<span data-ttu-id="7693f-205">팀에 비공개 채널을 추가하면 각 비공개 채널이 기본 공유 설정을 포함하는 새 SharePoint 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-205">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="7693f-206">이러한 사이트는 SharePoint 관리 센터에 표시되지 않으므로 Set-SPOSite PowerShell cmdlet을 사용하여 게스트 공유 설정을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-206">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="7693f-207">사이트 공유 설정</span><span class="sxs-lookup"><span data-stu-id="7693f-207">Site sharing settings</span></span>

<span data-ttu-id="7693f-208">팀 구성원이 아닌 사용자와 SharePoint 사이트를 공유하지 못하게 하도록 이러한 공유는 소유자로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-208">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="7693f-209">파일 및 폴더 공유도 팀 소유자로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-209">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="7693f-210">이를 통해 파일이 팀 외부의 다른 사용자와 공유될 때마다 소유자가 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-210">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="7693f-211">소유자 전용 사이트 공유를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="7693f-211">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="7693f-212">Teams에서 업데이트하려는 팀의 **일반** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-212">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="7693f-213">팀의 도구 막대에서 **파일** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-213">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="7693f-214">줄임표를 클릭한 다음 **SharePoint에서 열기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-214">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="7693f-215">기본 SharePoint 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-215">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="7693f-216">**사이트 권한** 창의 **사이트 공유에** 서 **멤버 공유 방법 변경** 을 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="7693f-216">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="7693f-217">**사용 권한 공유** 에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-217">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
7. <span data-ttu-id="7693f-218">**액세스 요청 허용** 을 **꺼짐** 으로 설정한 다음, **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7693f-218">Set **Allow access requests** to **Off**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7693f-219">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7693f-219">See Also</span></span>

[<span data-ttu-id="7693f-220">민감도 레이블과 해당 정책 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="7693f-220">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)