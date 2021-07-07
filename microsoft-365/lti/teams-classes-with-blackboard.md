---
title: Blackboard Microsoft Teams 클래스 통합
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
description: Blackboard Microsoft Teams 클래스 통합
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314498"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="f9527-103">Blackboard Microsoft Teams 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="f9527-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="f9527-104">팀워크는 모든 최신 조직의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="f9527-105">공동 작업을 육성하여 성공적인 모든 기관의 특징을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="f9527-106">각 클래스와 페어링하여 Blackboard Learn Ultra의 모든 기능과 Microsoft Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="f9527-107">클래스에는 실시간 대화, 비디오 모임 또는 비동기 조작이 포함되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="f9527-108">학생을 위한 파일 공유 및 공동 준비 환경을 한 장소에 모두 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="f9527-109">Microsoft Teams 학습을 통해 교육의 역동성 및 효과적인 학습의 의미를 다시 정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9527-110">SIS(학생 정보 시스템)에서 기관 전자 메일 필드를 성공적으로 설정해야 합니다. `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span><span class="sxs-lookup"><span data-stu-id="f9527-110">Ensure that you have successfully set up the Institution Email field in your Student Information System (SIS) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span></span>
>
><span data-ttu-id="f9527-111">Microsoft Teams 클래스 통합은 SIS의 기관 전자 메일 필드를 통해 AAD(Microsoft Azure Active Directory) UPN(사용자 계정 이름)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) User Principal Name (UPN).</span></span> <span data-ttu-id="f9527-112">기관 전자 메일이 프로비전되지 않은 경우 이 전자 메일은 기본적으로 기존 전자 메일로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="f9527-113">데이터가 올바르게 동기화되도록 모든 사용자에 대해 이 필드를 설정하고 Microsoft AAD와 Blackboard Learn Ultra 간에 전자 메일 데이터가 충돌하지 않도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between Microsoft AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="f9527-114">SIS 매핑에서 이 필드를 적절하게 설정하지 않은 경우 통합이 계속 작동하지만 사용자가 만든 Teams 나타나지 않을 수 있으며 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="f9527-115">기관 데이터 매핑 지원 - 기관 전자 메일 SIS 필드</span><span class="sxs-lookup"><span data-stu-id="f9527-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="f9527-116">클라우드 공급자 통합의 일부로 Blackboard Learn Ultra는 학생  정보 시스템 프레임워크 통합과 공용 REST API 모두에 새로운 기관 전자 메일 필드를 만들어 기관이 Blackboard Learn Ultra와 Microsoft AAD 간에 데이터 동기화 프로세스를 효과적으로 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and Microsoft AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="f9527-117">기관 전자 메일의 의미와 지원 여부</span><span class="sxs-lookup"><span data-stu-id="f9527-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="f9527-118">기관 **전자 메일 필드를** 사용하면 클라이언트의 외부에서 지원되는 데이터 원본과 Blackboard Learn Ultra 간에 사용자 지정된 필드 매핑을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="f9527-119">데이터 원본이 Microsoft와 같은 클라우드 공급자인 경우 UPN(사용자 원칙 이름)은 @ 기호와 함께 가입된 UPN 접두사(사용자의 계정 이름)와 UPN 접미사(DNS 도메인 이름)로 구성된 각 사용자의 기본 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="f9527-120">이렇게 하면 사용자 계정 내의 각 특정 사용자에 대해 고유한 전자 메일 Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f9527-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="f9527-121">데이터가 정확하고 Blackboard Learn Ultra 및 Microsoft Teams 클래스 간의 등록 또는 멤버 자격이 올바르게 달성되도록 보장하려면 사용자의 전자 메일 주소가 두 시스템 간에 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="f9527-122">Blackboard Learn Ultra에서 사용자는 사용자 인터페이스에서 기존 전자 메일 주소를 변경하거나 이로 인해 동기화 오류가 발생하고 사용자가 수업 팀에 올바르게 추가되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="f9527-123">기관 **전자 메일** 필드 매핑을 사용하면 사용자가 Blackboard Learn Ultra 내에서 전자 메일을 변경한 경우와 관계없이 이 수준의 보안 및 유효성 검사 검사를 올바르게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="f9527-124">두 전자 메일 주소가 서로 다른 경우 다음 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="f9527-125">우선 순위를 가지는 원본에 대한 결정을 내리고 개인 및 기관 전자 메일로 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="f9527-126">또는</span><span class="sxs-lookup"><span data-stu-id="f9527-126">Or</span></span>
- <span data-ttu-id="f9527-127">기관은 기관 전자 메일에서 사용자 정의 필드 매핑을 설정하여 잠재적인 충돌을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="f9527-128">이제 **고급** 구성에서 모든 기존 SIS 통합 유형에 대해 기관 **전자 메일** 필드 매핑을 사용할 설정 개체 유형 필드 매핑을 사용할 수  >    >  **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="f9527-129">기본적으로 기관 전자 메일은 모든 SIS 형식에 대해  개인 전자 메일로 설정되어 있으며 각 사용자에 대해 고유해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="f9527-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="f9527-130">전자 메일이 중복될 경우 SIS에서 사용자를 가져오지 못하기 때문에 설정 및 실행 중인 모든 기존 통합에는 이 데이터 매핑이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="f9527-131">기관에서 기관 전자 메일을 사용자 지정으로 변경할 수 있는 기능을 요구하는  경우 SIS의 고급 구성 설정 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="f9527-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9527-132">Requirements</span></span>

<span data-ttu-id="f9527-133">이 Microsoft Teams 통합은 울트라 코스 보기 과정에만 **사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="f9527-134">해당 기관에서 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="f9527-135">초고속 탐색을 사용하도록 설정한 Blackboard가 매우 자세히 학습 SaaS를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f9527-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

- <span data-ttu-id="f9527-136">과정에 사용할 LTI를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f9527-136">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="f9527-137">a.</span><span class="sxs-lookup"><span data-stu-id="f9527-137">a.</span></span> <span data-ttu-id="f9527-138">관리자 패널   >  **LTI 도구 공급자 전역** 속성 관리 로  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f9527-138">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="f9527-139">b.</span><span class="sxs-lookup"><span data-stu-id="f9527-139">b.</span></span> <span data-ttu-id="f9527-140">과정에서 **LTI 사용 을 선택하고** 원하는 경우 **조직에서 사용 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-140">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="f9527-141">c.</span><span class="sxs-lookup"><span data-stu-id="f9527-141">c.</span></span> <span data-ttu-id="f9527-142">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-142">Select **Submit**.</span></span>

- <span data-ttu-id="f9527-143">LTI가 구성되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-143">Must have LTI configured</span></span>

- <span data-ttu-id="f9527-144">Add Blackboard Learn Ultra Teams Classes LTI Integration</span><span class="sxs-lookup"><span data-stu-id="f9527-144">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="f9527-145">추가 Microsoft Teams 클래스 LTI 1.3 도구</span><span class="sxs-lookup"><span data-stu-id="f9527-145">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="f9527-146">REST API 도구 및 원본 간 리소스 공유 추가</span><span class="sxs-lookup"><span data-stu-id="f9527-146">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="f9527-147">통합 클래스 Microsoft Teams 구성 및 승인</span><span class="sxs-lookup"><span data-stu-id="f9527-147">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="f9527-148">Blackboard Learn Ultra Teams 클래스 LTI 1.3 도구 추가</span><span class="sxs-lookup"><span data-stu-id="f9527-148">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="f9527-149">관리자 **패널에서** **LTI 도구 공급자 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-149">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="f9527-150">**LTI 1.3 도구 등록을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-150">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="f9527-151">클라이언트 **ID 필드에** 이 ID를 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-151">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="f9527-152">미리 채워진 모든 설정을 검토하고 도구 상태 에서 **를** 검토한 다음 사용 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-152">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="f9527-153">기관 **정책에서** 과정의 **역할,** 이름 및 전자 메일 주소를 선택한 다음 둘 **다에 대해 예를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-153">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="f9527-154">등급 **서비스 액세스 허용 및** 멤버 자격 서비스 액세스 **허용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-154">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="f9527-155">Microsoft Teams 클래스 LTI 1.3 도구 추가</span><span class="sxs-lookup"><span data-stu-id="f9527-155">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="f9527-156">관리자 **패널에서** **LTI 도구 공급자 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-156">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="f9527-157">**LTI 1.3 도구 등록을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-157">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="f9527-158">클라이언트 **ID 필드에** 이 ID를 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-158">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="f9527-159">미리 채워진 모든 설정을 검토하고 도구 상태를 *검토하고* 사용 을 *선택합니다.*</span><span class="sxs-lookup"><span data-stu-id="f9527-159">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="f9527-160">기관 **정책에서** **과정의 역할, 이름 및** 전자 메일 주소를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-160">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="f9527-161">둘 **다에 대해 예를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-161">Select **Yes** for both.</span></span>

6. <span data-ttu-id="f9527-162">등급 **서비스 액세스 허용 및** 멤버 자격 서비스 액세스 **허용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-162">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="f9527-163">REST API 도구 추가</span><span class="sxs-lookup"><span data-stu-id="f9527-163">Add the REST API tool</span></span>

1. <span data-ttu-id="f9527-164">관리자 **패널에서** 통합으로 **이동하고** **Rest API Integrations 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-164">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="f9527-165">통합 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-165">Select **Create Integration**.</span></span>

3. <span data-ttu-id="f9527-166">응용 **프로그램 ID 필드에** 이 ID를 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-166">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="f9527-167">이 통합에 대한 사용자를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-167">Type a user for this integration.</span></span>

   <span data-ttu-id="f9527-168">이 사용자는 응용 프로그램이 연결된 홈 API 액세스 권한이 있는 사용자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-168">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="f9527-169">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-169">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="f9527-170">원본 간 리소스 공유 추가</span><span class="sxs-lookup"><span data-stu-id="f9527-170">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="f9527-171">관리자 **패널에서** 통합으로 **이동하고** \* 원본 간 리소스 공유 *를 선택합니다.*</span><span class="sxs-lookup"><span data-stu-id="f9527-171">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="f9527-172">구성 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-172">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="f9527-173">원본 **필드에** 이 URL을 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-173">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="f9527-174">허용되는 **헤더 필드에** 권한 부여 를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-174">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="f9527-175">사용 **가능을 예로** **설정**</span><span class="sxs-lookup"><span data-stu-id="f9527-175">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="f9527-176">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-176">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="f9527-177">통합 클래스 Microsoft Teams 구성 및 승인</span><span class="sxs-lookup"><span data-stu-id="f9527-177">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="f9527-178">Blackboard Learn Ultra 인스턴스를 Microsoft Teams 클래스와 성공적으로 통합하려면 Blackboard Learn Ultra 응용 프로그램이 Microsoft Azure 테넌트 내에서 액세스가 승인되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-178">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="f9527-179">이 프로세스는 기관의 전역 관리자가 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-179">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="f9527-180">이 프로세스는 Blackboard Learn Ultra Instance에서 LTI 응용 프로그램을 구성하기 전이나 후에 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-180">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="f9527-181">LTI 응용 프로그램을 구성하기 전에</span><span class="sxs-lookup"><span data-stu-id="f9527-181">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="f9527-182">LTI 통합을 구성하기 전에 Blackboard Learn Ultra Teams Classes Azure 앱을 승인하려면 Microsoft Identity Platform 관리자 동의 끝점으로 **리디렉션해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-182">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="f9527-183">URL이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-183">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="f9527-184">**{Tenant}를** 특정 기관용 테넌트 Microsoft Azure 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-184">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="f9527-185">LTI 응용 프로그램 구성 후</span><span class="sxs-lookup"><span data-stu-id="f9527-185">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="f9527-186">관리자 **패널에서** 도구  및 유틸리티로 이동하고 통합 **Microsoft Teams 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-186">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="f9527-187">에서 **사용 을 Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="f9527-187">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="f9527-188">사용 가능한 **텍스트 필드에 Microsoft 테넌트 ID를** 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-188">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="f9527-189">다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-189">Choose one of the following options:</span></span>

   - <span data-ttu-id="f9527-190">앱에 사전 동의가 있는 경우 작은 확인 표시가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-190">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="f9527-191">확인 표시가 나타나면 제출을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-191">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="f9527-192">동의가 승인되지 않은 경우 설명된 단계에 따라 동의를 위해 URL을 생성하고 승인을 위해 Microsoft 365 전역 관리자에게 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="f9527-192">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="f9527-193">승인을 확인한 후 다시 **시도를** 선택하여 확인한 다음 제출을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9527-193">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>
