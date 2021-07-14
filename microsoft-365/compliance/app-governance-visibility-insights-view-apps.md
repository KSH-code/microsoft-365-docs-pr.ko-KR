---
title: 앱 보기
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 앱을 봅니다.
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420262"
---
# <a name="view-your-apps"></a><span data-ttu-id="d872c-103">앱 보기</span><span class="sxs-lookup"><span data-stu-id="d872c-103">View your apps</span></span>

><span data-ttu-id="d872c-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="d872c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="d872c-105">Microsoft 앱 거버넌스를 사용하면 사용자의 테넌트의 Microsoft 365 앱에 대한 심층적인 인사이트를 빠르게 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-105">Microsoft app governance allows you to quickly gain deep insights into the Microsoft 365 apps in your tenant.</span></span> <span data-ttu-id="d872c-106">예를 들어 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-106">For example, you can see:</span></span>

- <span data-ttu-id="d872c-107">관련 앱 메타데이터 및 사용량 현황 데이터와 함께 Microsoft Graph API를 사용하는 테넌트 내의 OAuth 지원 앱 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-107">A list of OAuth-enabled apps in the tenant that use the Microsoft Graph API, together with relevant app metadata and usage data.</span></span>
- <span data-ttu-id="d872c-108">목록에서 앱을 선택하여 심층적인 인사이트와 정보를 포함하는 앱 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-108">App details with deeper insights and information by selecting an app in the list.</span></span>

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a><span data-ttu-id="d872c-109">테넌트의 모든 앱 목록 가져오기</span><span class="sxs-lookup"><span data-stu-id="d872c-109">Getting a list of all the apps in your tenant</span></span>

<span data-ttu-id="d872c-110">테넌트에서 앱에 대한 요약을 보려면 **Microsoft 365 규정 준수 센터 > 앱 보호 및 거버넌스 > 앱** 으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="d872c-110">For a summary of apps in your tenant, go to **Microsoft 365 Compliance Center > App protection & governance > Apps**.</span></span>

![Microsoft 365 규정 준수 센터의 MAPG 앱 요약 페이지](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> <span data-ttu-id="d872c-112">앱 거버넌스 데이터를 보려면 로그인 계정에 [관리자 역할](app-governance-get-started.md#administrator-roles) 중 하나가 부여되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-112">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="d872c-113">앱 목록과 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-113">You will see a list of apps and this information:</span></span>

- <span data-ttu-id="d872c-114">앱 이름</span><span class="sxs-lookup"><span data-stu-id="d872c-114">App Name</span></span>
- <span data-ttu-id="d872c-115">게시자</span><span class="sxs-lookup"><span data-stu-id="d872c-115">Publisher</span></span>
- <span data-ttu-id="d872c-116">앱 인증</span><span class="sxs-lookup"><span data-stu-id="d872c-116">App certification</span></span>

  <span data-ttu-id="d872c-117">앱이 Microsoft 기술과 호환되는지, Cloud App Security 모범 사례를 준수하며, Microsoft에서 지원하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-117">Indicates whether the app is compatible with Microsoft technologies, compliant with cloud app security best practices, and supported by Microsoft.</span></span>

- <span data-ttu-id="d872c-118">마지막으로 수정한 날짜</span><span class="sxs-lookup"><span data-stu-id="d872c-118">Last modified</span></span>

  <span data-ttu-id="d872c-119">해당 날짜가 앱이 마지막으로 수정된 날짜보다 최신인 경우 클라이언트에 앱 거버넌스가 설치된 날짜를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-119">Shows the date app governance was installed in client if that date is more recent than the date the app was last modified.</span></span>

- <span data-ttu-id="d872c-120">설치한 날짜</span><span class="sxs-lookup"><span data-stu-id="d872c-120">Date installed</span></span>
- <span data-ttu-id="d872c-121">권한 수준</span><span class="sxs-lookup"><span data-stu-id="d872c-121">Privilege level</span></span>
- <span data-ttu-id="d872c-122">사용자 수</span><span class="sxs-lookup"><span data-stu-id="d872c-122">Number of users</span></span>
- <span data-ttu-id="d872c-123">데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="d872c-123">Data access</span></span>

  <span data-ttu-id="d872c-124">마지막 날의 테넌트에서 앱의 데이터 업로드 및 다운로드 합계와 그 전 날의 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-124">The sum of the app’s data upload and download in the tenant over the last day, along with the change over the prior day.</span></span>

<span data-ttu-id="d872c-125">앱 거버넌스는 기본적으로 **앱 이름** 순으로 앱 목록을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-125">App governance sorts the app list by **App name** by default.</span></span> <span data-ttu-id="d872c-126">목록을 다른 앱 특성별로 정렬하려면 특성 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-126">To sort the list by another app attribute, select the attribute name.</span></span>

<span data-ttu-id="d872c-127">**검색** 을 선택하여 앱의 이름을 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-127">You can also select **Search** to search for an app by name.</span></span>

## <a name="getting-detailed-information-on-an-app"></a><span data-ttu-id="d872c-128">앱에 대한 자세한 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="d872c-128">Getting detailed information on an app</span></span>

<span data-ttu-id="d872c-129">테넌트의 특정 앱에 대한 자세한 내용은 \*\*Microsoft 365 규정 준수 센터 > 앱 거버넌스 > 앱 페이지 > \*앱 이름\*\*\*으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="d872c-129">For detailed information on a specific app in your tenant, go to \*\*Microsoft 365 Compliance Center > App governance > Apps page > \*app name\*\*\*.</span></span>

![Microsoft 365 규정 준수 센터의 앱 거버넌스 앱 세부 정보 창](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

<span data-ttu-id="d872c-131">앱 세부 정보 창은 다음 탭에 관한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-131">The app details pane provides additional information on these tabs:</span></span>

| <span data-ttu-id="d872c-132">탭 이름</span><span class="sxs-lookup"><span data-stu-id="d872c-132">Tab name</span></span> | <span data-ttu-id="d872c-133">설명</span><span class="sxs-lookup"><span data-stu-id="d872c-133">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="d872c-134">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d872c-134">Details</span></span> | <span data-ttu-id="d872c-135">앱에서 처음 동의한 날짜 및 앱 ID와 같은 추가 데이터를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-135">See additional data on the app such as the date first consented and the App ID.</span></span> <span data-ttu-id="d872c-136">Azure AD에 등록된 앱의 속성을 보려면 **Azure AD의 앱 보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-136">To see the properties of the app as registered in Azure AD, select **View app in Azure AD**.</span></span> |
| <span data-ttu-id="d872c-137">사용 현황</span><span class="sxs-lookup"><span data-stu-id="d872c-137">Usage</span></span> | <span data-ttu-id="d872c-138">테넌트의 앱에서 액세스한 데이터를 보고, 데이터 사용량을 표시하고, 상위 \<x>명의 사용자와 [우선 순위 계정](/microsoft-365/admin/setup/priority-accounts)이 있는 사용자의 사용량을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-138">See the data accessed by the app in the tenant, plot the data usage, and show usage by the top \<x> users and users with [priority accounts](/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="d872c-139">사용자</span><span class="sxs-lookup"><span data-stu-id="d872c-139">Users</span></span> | <span data-ttu-id="d872c-140">앱을 사용하는 사용자 목록, 우선 순위 계정 여부와 다운로드 및 업로드된 데이터 양을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-140">See a list of users who are using the app, whether they are a priority account, and the amount of data downloaded and uploaded.</span></span> |
| <span data-ttu-id="d872c-141">사용 권한</span><span class="sxs-lookup"><span data-stu-id="d872c-141">Permissions</span></span> | <span data-ttu-id="d872c-142">앱에 부여된 사용 권한 및 앱이 사용하는 사용 권한과 특정 사용 권한 목록의 요약을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d872c-142">See a summary of the permissions granted to and used by the app and the list of specific permissions.</span></span> <span data-ttu-id="d872c-143">자세한 내용은 [Microsoft Graph 사용 권한 참조](/graph/permissions-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d872c-143">See the [Microsoft Graph permissions reference](/graph/permissions-reference) for more information.</span></span> |
|||

<span data-ttu-id="d872c-144">활성화된 앱의 경우 **앱 비활성화** 컨트롤을 사용하여 선택된 앱을 비활성화할 수 있고 **앱 활성화** 컨트롤을 사용하여 비활성화된 앱을 사용하도록 설정하는 기능도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-144">For an enabled app, there is also a **Disable app** control to disable the use of the selected app and an **Enable app** control to enable the use of the disabled app.</span></span> <span data-ttu-id="d872c-145">이러한 작업을 수행하려면 다음 [관리자 역할](app-governance-get-started.md#administrator-roles)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d872c-145">These actions require these [administrator roles](app-governance-get-started.md#administrator-roles):</span></span>

- <span data-ttu-id="d872c-146">규정 준수 관리자</span><span class="sxs-lookup"><span data-stu-id="d872c-146">Compliance Administrator</span></span>
- <span data-ttu-id="d872c-147">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="d872c-147">Global Administrator</span></span>
- <span data-ttu-id="d872c-148">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="d872c-148">Security Administrator</span></span>
- <span data-ttu-id="d872c-149">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="d872c-149">Security Operator</span></span>

## <a name="next-step"></a><span data-ttu-id="d872c-150">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d872c-150">Next step</span></span>

<span data-ttu-id="d872c-151">[전반적인 앱 규정 준수 상태를 결정합니다.](app-governance-visibility-insights-compliance-posture.md)</span><span class="sxs-lookup"><span data-stu-id="d872c-151">[Determine your overall app compliance posture](app-governance-visibility-insights-compliance-posture.md).</span></span>
