---
title: 학습 관리 시스템에서 Microsoft Teams 클래스 사용
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 학습 관리 시스템에 Microsoft Teams 클래스 통합
ms.openlocfilehash: 18d33225dd57932af20421c6b3b5dc4fe3b397b8
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327784"
---
# <a name="use-microsoft-teams-classes-in-your-learning-management-system"></a><span data-ttu-id="eabad-103">학습 관리 시스템에서 Microsoft Teams 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="eabad-103">Use Microsoft Teams classes in your Learning Management System</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eabad-104">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="eabad-105">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="eabad-106">Microsoft Teams 수업 팀은 교육자 및 학생이 LMS(학습 관리 시스템) 및 Teams 간을 쉽게 탐색할 수 있도록 돕는 LTI(학습 도구 상호 운영성) 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-106">Microsoft Teams class teams is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="eabad-107">사용자는 LMS 내에서 직접 과정과 연결된 수업 팀에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="eabad-108">Microsoft Azure 테넌트에서 앱 승인</span><span class="sxs-lookup"><span data-stu-id="eabad-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="eabad-109">다음 작업은 Microsoft Office 365 관리자 및 Blackboard Learn Ultra 관리자에 의해 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="eabad-110">Blackboard Learn Ultra 내에서 통합을 관리하기 전에 Microsoft Office 365 관리자는 기관의 Microsoft Azure 테넌트에 대한 울트라 Azure 앱용 Blackboard **MSFT Teams를** 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="eabad-111">Microsoft 테넌트 ID를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="eabad-112">[테넌트 를 찾는 방법을 참조합니다.](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)</span><span class="sxs-lookup"><span data-stu-id="eabad-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="eabad-113">다음 예에 따라 Microsoft Identity Platform 관리자 동의 끝점을 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="eabad-114">{tenant}를 조직의 Microsoft 테넌트 ID로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="eabad-115">통합 앱 등록</span><span class="sxs-lookup"><span data-stu-id="eabad-115">Register the integration apps</span></span>

<span data-ttu-id="eabad-116">Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span><span class="sxs-lookup"><span data-stu-id="eabad-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="eabad-117">로스터 동기화를 지원하기 위한 Blackboard Learn Class Teams 통합</span><span class="sxs-lookup"><span data-stu-id="eabad-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="eabad-118">Microsoft Teams 수업 팀 LTI 앱</span><span class="sxs-lookup"><span data-stu-id="eabad-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="eabad-119">두 앱에 대한 다음 LTI 클라이언트 ID를 메모합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="eabad-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="eabad-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="eabad-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="eabad-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="eabad-122">관리 패널에 액세스하고 통합에서 LTI 도구 공급자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![LTI 도구 공급자 대화 상자에 공급자 목록이 표시됩니다.](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="eabad-124">**LTI1.3/Advantage 도구 등록을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eabad-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="eabad-125">제공된 클라이언트 ID 중 첫 번째(Blackboard 또는 Microsoft)를 입력하고 제출 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eabad-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

   ![클라이언트 ID를 입력할 필드가 있는 LTI 등록 도구](../media/lti-media/register-tool.png)

5. <span data-ttu-id="eabad-127">미리 채워진 설정을 검토하고 도구 상태가 승인됨으로 표시되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-127">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="eabad-128">아래쪽으로 스크롤한 다음 제출을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eabad-128">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="eabad-129">환경 내에 LTI 앱의 두 번째를 등록하기 위해 이전 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-129">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="eabad-130">REST 응용 프로그램 및 교차 원본 리소스 공유 설정</span><span class="sxs-lookup"><span data-stu-id="eabad-130">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="eabad-131">Blackboard Learn Ultra 관리자는 REST 응용 프로그램 및 교차 원본 리소스 공유 구성도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-131">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="eabad-132">다음을 완료하여 REST 응용 프로그램 설정</span><span class="sxs-lookup"><span data-stu-id="eabad-132">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="eabad-133">관리 도구 학습에 액세스한 다음 통합 섹션에서 **REST API** **통합을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-133">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="eabad-134">통합 **만들기를 선택하고** Blackboard 수업 Teams 통합 LTI 도구에 대해 입력한 동일한 응용 프로그램/클라이언트 ID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-134">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="eabad-135">사용자 학습(직접 관리자 사용자 이름일 수 있습니다)을 입력하거나 **찾아보기를** 선택하여 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-135">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="eabad-136">최종 **사용자 액세스에** **대해 예를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eabad-136">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="eabad-137">사용자로 활동 **권한이 부여된 경우 예를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="eabad-137">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="eabad-138">완료되면 **제출을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-138">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="eabad-139">원본 간 리소스 공유 설정</span><span class="sxs-lookup"><span data-stu-id="eabad-139">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="eabad-140">관리 도구 학습에 액세스하고 통합 섹션에서 원본 **간** 리소스 **공유를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-140">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="eabad-141">구성 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eabad-141">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="eabad-142">원본에 `https://bb-ms-teams-ultra-ext.api.blackboard.com` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-142">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="eabad-143">허용되는 **헤더에 권한** 부여 **단어를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="eabad-143">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="eabad-144">사용 **가능을 예로** **설정**</span><span class="sxs-lookup"><span data-stu-id="eabad-144">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="eabad-145">완료되면 **제출을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-145">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="eabad-146">Blackboard에서 수업 팀 사용 학습</span><span class="sxs-lookup"><span data-stu-id="eabad-146">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="eabad-147">LTI 도구를 사용하도록 설정한 후 다음 단계는 365 테넌트에서 Microsoft 클래스 Teams 통합을 Microsoft Office 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-147">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="eabad-148">Blackboard Learn Ultra admin로 다음 단계를 수행하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-148">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="eabad-149">관리 **도구 및** 유틸리티  >  **학습에서** **Microsoft Teams 통합 관리자 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eabad-149">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![사용 가능한 도구 목록이 있는 도구 및 유틸리티 대화 상자](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="eabad-151">Microsoft Teams 사용 **확인란을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eabad-151">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="eabad-152">Microsoft O365 관리자 아래 섹션에 참조된 테넌트 ID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eabad-152">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="eabad-153">O365 관리자가 앱을 승인하기 전까지는 설정을 저장할 수 없습니다. [Microsoft Azure 테넌트에서 앱 승인을 참조하세요.](#approve-the-app-in-the-microsoft-azure-tenant)</span><span class="sxs-lookup"><span data-stu-id="eabad-153">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="eabad-154">전역 O365 관리자가 Microsoft 테넌트에서 Blackboard Teams 응용 프로그램을 승인한 경우 제출을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eabad-154">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
