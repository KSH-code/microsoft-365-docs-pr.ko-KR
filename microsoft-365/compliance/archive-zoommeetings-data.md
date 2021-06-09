---
title: 모임 확대/축소 데이터를 보관할 커넥터를 Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 관리자는 Veritas Zoom Meetings에서 데이터를 가져오고 보관할 커넥터를 설정하여 사용자 Microsoft 365. 이를 통해 타사 데이터 원본의 데이터를 보관할 수 Microsoft 365 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: b67098f3ddb1149927f4b82270c8fa4f14bbe558
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163732"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a><span data-ttu-id="d0300-104">확대/축소 모임 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="d0300-104">Set up a connector to archive Zoom Meetings data</span></span>

<span data-ttu-id="d0300-105">Microsoft 365 준수 센터의 Veritas 커넥터를 사용하여 확대/축소 모임에서 조직 내 사용자 사서함으로 데이터를 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from Zoom Meetings to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="d0300-106">Veritas는 [](https://globanet.com/zoom/) 타사 데이터 원본에서 항목을 캡처하고 해당 항목을 정기적으로 가져오도록 구성된 확대/축소 모임 커넥터를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d0300-106">Veritas provides a [Zoom Meetings](https://globanet.com/zoom/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="d0300-107">커넥터는 채팅, 녹음된 파일 및 메타데이터를 포함하여 모임의 콘텐츠를 확대/축소 모임 계정에서 전자 메일 메시지 형식으로 변환한 다음 모임의 사용자 사서함으로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d0300-107">The connector converts the content of the meetings (including chats, recorded files, and metadata) from the Zoom Meetings account to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="d0300-108">확대/축소 모임 데이터가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery Microsoft 365 보존 정책 및 보존 레이블, 통신 준수와 같은 Microsoft 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-108">After Zoom Meetings data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="d0300-109">확대/축소 모임 커넥터를 사용하여 조직의 데이터를 Microsoft 365 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-109">Using a Zoom Meetings connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-zoom-meetings-data"></a><span data-ttu-id="d0300-110">확대/축소 모임 데이터 보관 개요</span><span class="sxs-lookup"><span data-stu-id="d0300-110">Overview of archiving Zoom Meetings data</span></span>

<span data-ttu-id="d0300-111">다음 개요에서는 커넥터를 사용하여 모임 확대/축소 데이터를 보관하는 프로세스에 대해 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d0300-111">The following overview explains the process of using a connector to archive Zoom Meetings data in Microsoft 365.</span></span>

![확대/축소 모임 보관 워크플로](../media/ZoomMeetingsConnectorWorkflow.png)

1. <span data-ttu-id="d0300-113">조직은 확대/축소 모임과 함께 작업하여 확대/축소 모임 사이트를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-113">Your organization works with Zoom Meetings to set up and configure a Zoom Meetings site.</span></span>

2. <span data-ttu-id="d0300-114">24시간마다 확대/축소 모임의 모임 항목이 Veritas Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-114">Once every 24 hours, meeting items from Zoom Meetings are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="d0300-115">또한 커넥터는 모임의 콘텐츠를 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-115">The connector also converts the content of the meetings to an email message format.</span></span>

3. <span data-ttu-id="d0300-116">Microsoft 365 준수 센터에서 만든 확대/축소 모임 커넥터는 매일 Veritas Merge1에 연결하고 모임 메시지를 Microsoft 클라우드의 안전한 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-116">The Zoom Meetings connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 every day, and transfers the meeting messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="d0300-117">커넥터는 3단계에 설명된 전자 메일 속성 및 자동  사용자 매핑 값을 사용하여 변환된 모임 항목을 특정 사용자의 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-117">The connector imports the converted meeting items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="d0300-118">사용자 사서함에 확대/축소 모임이라는 받은  편지함 폴더의 새 하위 폴더가 만들어지며 모임 항목을 해당 폴더로 가져오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-118">A new subfolder in the Inbox folder named **Zoom Meetings** is created in user mailboxes, and the meeting items are imported to that folder.</span></span> <span data-ttu-id="d0300-119">이 커넥터는 Email 속성 값을 사용하여 이 *기능을* 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="d0300-120">모든 모임 항목에는 모임 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-120">Every meeting item contains this property, which is populated with the email address of every participant of the meeting.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d0300-121">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="d0300-121">Before you begin</span></span>

- <span data-ttu-id="d0300-122">Microsoft 커넥터에 대한 Veritas Merge1 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="d0300-123">이 계정을 만들하려면 [Veritas 고객 지원에 문의하세요.](https://globanet.com/ms-connectors-contact)</span><span class="sxs-lookup"><span data-stu-id="d0300-123">To create this account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="d0300-124">1단계에서 커넥터를 만들 때 이 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="d0300-125">조직의 확대/축소 비즈니스 또는 확대/축소 계정의 사용자 이름과 암호를 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d0300-125">Obtain the username and password for your organization's Zoom Business or Zoom Enterprise account.</span></span> <span data-ttu-id="d0300-126">확대/축소 모임 커넥터를 구성할 때 2단계에서 이 계정에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-126">You'll need to sign into this account in Step 2 when you configure the Zoom Meetings connector.</span></span>

- <span data-ttu-id="d0300-127">확대/축소 마켓플레이스에서 다음 [응용 프로그램을 만들 수 있습니다.](https://marketplace.zoom.us)</span><span class="sxs-lookup"><span data-stu-id="d0300-127">Create the following applications in the [Zoom Marketplace](https://marketplace.zoom.us):</span></span>

  - <span data-ttu-id="d0300-128">OAuth 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d0300-128">OAuth application</span></span>

  - <span data-ttu-id="d0300-129">JWT 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d0300-129">JWT application</span></span>

  <span data-ttu-id="d0300-130">이러한 응용 프로그램을 만든 후 확대/축소 플랫폼은 토큰을 생성하는 데 사용되는 고유한 자격 증명 집합을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-130">After you create these applications, the Zoom platform generates a set of unique credentials used to generate the tokens.</span></span> <span data-ttu-id="d0300-131">이러한 토큰은 확대/축소 계정에 연결하여 Merge1 사이트에 항목을 복사할 때 커넥터를 인증하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-131">These tokens are used to authenticate the connector when it connects to your Zoom account and copies items to the Merge1 site.</span></span> <span data-ttu-id="d0300-132">2단계에서 확대/축소 커넥터를 구성할 때 이러한 토큰을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-132">You will use these tokens when you configure the Zoom connector in Step 2.</span></span>

  <span data-ttu-id="d0300-133">OAuth 및 JWT 응용 프로그램을 만드는 방법에 대한 단계별 지침은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="d0300-133">For step-by step instructions on how to create the OAuth and JWT applications, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="d0300-134">1단계에서 확대/축소 모임 커넥터를 만들고 3단계에서 완료하는 사용자는 2단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d0300-134">The user who creates the Zoom Meetings connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d0300-135">이 역할은 준수 센터의  데이터 커넥터 페이지에서 커넥터를 Microsoft 365 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-135">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d0300-136">기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d0300-136">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="d0300-137">사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d0300-137">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d0300-138">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-138">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d0300-139">자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d0300-139">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-zoom-meetings-connector"></a><span data-ttu-id="d0300-140">1단계: 확대/축소 모임 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="d0300-140">Step 1: Set up the Zoom Meetings connector</span></span>

<span data-ttu-id="d0300-141">첫 번째 단계는 준수 센터의 **데이터** 커넥터에 액세스하고 Microsoft 365 확대/축소 모임 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-141">The first step is to access the **Data Connectors** in the Microsoft 365 compliance center and create a Zoom Meetings connector.</span></span>

1. <span data-ttu-id="d0300-142">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 이동한 다음 데이터 커넥터 **확대/축소**  >  **모임을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0300-142">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Zoom Meetings**.</span></span>

2. <span data-ttu-id="d0300-143">**확대/축소 모임 제품 설명** 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0300-143">On the **Zoom Meetings** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="d0300-144">서비스 **약관 페이지에서** 동의를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0300-144">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="d0300-145">커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d0300-145">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="d0300-146">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-146">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-zoom-meetings-connector"></a><span data-ttu-id="d0300-147">2단계: 확대/축소 모임 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="d0300-147">Step 2: Configure the Zoom Meetings connector</span></span>

<span data-ttu-id="d0300-148">두 번째 단계는 Merge1 사이트에서 확대/축소 모임 커넥터를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-148">The second step is to configure the Zoom Meetings connector on the Merge1 site.</span></span> <span data-ttu-id="d0300-149">Veritas Merge1 사이트에서 확대/축소 모임 커넥터를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="d0300-149">For more information about how to configure the Zoom Meetings connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="d0300-150">저장 및 & **마친** 후  준수 센터의 커넥터 마법사에 Microsoft 365 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-150">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="d0300-151">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="d0300-151">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="d0300-152">외부 사용자를 **사용자 Microsoft 365** 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-152">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="d0300-153">확대/축소 모임 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-153">Zoom Meetings items include a property called *Email* that contains email addresses for users in your organization.</span></span> <span data-ttu-id="d0300-154">커넥터가 이 주소를 사용자와 Microsoft 365 경우 해당 사용자의 사서함으로 항목을 가져오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-154">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox</span></span>

2. <span data-ttu-id="d0300-155">**다음을** 클릭하고 설정을 검토하고  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-155">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-zoom-meetings-connector"></a><span data-ttu-id="d0300-156">4단계: 확대/축소 모임 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="d0300-156">Step 4: Monitor the Zoom Meetings connector</span></span>

<span data-ttu-id="d0300-157">확대/축소 모임 커넥터를 만든 후 준수 센터에서 커넥터 상태를 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-157">After you create the Zoom Meetings connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="d0300-158">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-158">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d0300-159">커넥터 **탭을** 클릭한 다음 확대/축소 **모임** 커넥터를 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-159">Click the **Connectors** tab and then select the **Zoom Meetings** connector to display the flyout page.</span></span> <span data-ttu-id="d0300-160">이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-160">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="d0300-161">원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-161">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="d0300-162">이 로그에는 Microsoft 클라우드로 가져온 데이터에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-162">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d0300-163">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="d0300-163">Known issues</span></span>

- <span data-ttu-id="d0300-164">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-164">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="d0300-165">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-165">Support for larger items will be available at a later date.</span></span>

- <span data-ttu-id="d0300-166">확대/축소 모임 커넥터가 작동하려면 확대/축소 모임을 설정할 때 녹음/녹화를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0300-166">For the Zoom Meetings connector to work, you must enable recordings when setting up Zoom Meetings.</span></span>