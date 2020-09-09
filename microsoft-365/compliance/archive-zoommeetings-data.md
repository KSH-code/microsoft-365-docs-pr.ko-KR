---
title: Microsoft 365에서 확대/축소 모임 데이터를 보관 하는 커넥터 설정
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
ROBOTS: NOINDEX, NOFOLLOW
description: 관리자는 Globanet Zoom Meeting에서 Microsoft 365로 데이터를 가져오고 보관 하기 위한 커넥터를 설정할 수 있습니다. 이를 통해 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용 하 여 조직의 타사 데이터를 관리할 수도 있습니다.
ms.openlocfilehash: 6b2f5f0b61eb2d569ad49d8f58c7e03d11cdbca0
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405499"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data-preview"></a><span data-ttu-id="e6be1-104">확대/축소 모임 데이터를 보관 하는 연결선 설정 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e6be1-104">Set up a connector to archive Zoom Meetings data (preview)</span></span>

<span data-ttu-id="e6be1-105">Microsoft 365 준수 센터의 Globanet 커넥터를 사용 하 여 확대/축소 회의에서 Microsoft 365 조직의 사용자 사서함으로 데이터를 가져오고 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from Zoom Meetings to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="e6be1-106">Globanet에서는 타사 데이터 원본의 항목을 정기적으로 캡처하고 해당 항목을 Microsoft 365으로 가져오기 위해 구성 된 [확대/축소 회의](https://globanet.com/zoom/) 커넥터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-106">Globanet provides a [Zoom Meetings](https://globanet.com/zoom/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="e6be1-107">이 커넥터는 모임 (채팅, 기록 된 파일 및 메타 데이터 포함)의 콘텐츠를 확대/축소 회의 계정에서 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 Microsoft 365의 사용자 사서함으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-107">The connector converts the content of the meetings (including chats, recorded files, and metadata) from the Zoom Meetings account to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="e6be1-108">확대/축소 회의 데이터를 사용자 사서함에 저장 하면 소송 보존, eDiscovery, 보존 정책 및 보존 레이블과 통신 준수와 같은 Microsoft 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-108">After Zoom Meetings data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="e6be1-109">Microsoft 365에서 데이터를 가져오고 보관 하기 위해 확대/축소 회의 커넥터를 사용 하면 조직이 정부 및 규정 정책을 준수 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-109">Using a Zoom Meetings connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-zoom-meetings-data"></a><span data-ttu-id="e6be1-110">보관 확대/축소 모임 데이터 개요</span><span class="sxs-lookup"><span data-stu-id="e6be1-110">Overview of archiving Zoom Meetings data</span></span>

<span data-ttu-id="e6be1-111">다음 개요에서는 커넥터를 사용 하 여 Microsoft 365에서 확대/축소 모임 데이터를 보관 하는 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-111">The following overview explains the process of using a connector to archive Zoom Meetings data in Microsoft 365.</span></span>

![여유 시간 eDiscovery 보관 워크플로](../media/ZoomMeetingsConnectorWorkflow.png)

1. <span data-ttu-id="e6be1-113">조직은 확대/축소 회의와 함께 작업 하 여 모임 확대/축소 사이트를 설정 및 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-113">Your organization works with Zoom Meetings to set up and configure a Zoom Meetings site.</span></span>

2. <span data-ttu-id="e6be1-114">24 시간 마다 한 번씩 확대/축소 회의의 모임 항목은 Globanet Merge1 사이트에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-114">Once every 24 hours, meeting items from Zoom Meetings are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="e6be1-115">또한이 커넥터는 모임의 콘텐츠를 전자 메일 메시지 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-115">The connector also converts the content of the meetings to an email message format.</span></span>

3. <span data-ttu-id="e6be1-116">Microsoft 365 준수 센터에서 만든 확대/축소 회의 커넥터는 매일 Globanet Merge1에 연결 하 고, 모임 메시지를 Microsoft 클라우드의 안전한 Azure Storage 위치로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-116">The Zoom Meetings connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 every day, and transfers the meeting messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="e6be1-117">커넥터는 3 단계에 설명 된 대로 *전자 메일* 속성 및 자동 사용자 매핑의 값을 사용 하 여 변환 된 모임 항목을 특정 사용자의 사서함으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-117">The connector imports the converted meeting items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="e6be1-118">사용자 사서함에는 **Zoom** Meeting 이라는 받은 편지함 폴더의 새 하위 폴더가 만들어지고 해당 폴더로 모임 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-118">A new subfolder in the Inbox folder named **Zoom Meetings** is created in user mailboxes, and the meeting items are imported to that folder.</span></span> <span data-ttu-id="e6be1-119">커넥터는 *Email* 속성 값을 사용 하 여이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="e6be1-120">모든 모임 항목에는이 속성이 있으며,이 속성은 모든 모임 참가자의 전자 메일 주소로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-120">Every meeting item contains this property, which is populated with the email address of every participant of the meeting.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e6be1-121">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="e6be1-121">Before you begin</span></span>

- <span data-ttu-id="e6be1-122">Microsoft 커넥터에 대 한 Globanet Merge1 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="e6be1-123">이 작업을 수행 하려면 [Globanet 고객 지원](https://globanet.com/ms-connectors-contact)에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6be1-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="e6be1-124">1 단계에서 커넥터를 만들 때이 계정에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="e6be1-125">조직의 확대/축소 회사 또는 확대/축소 계정에 대 한 사용자 이름 및 암호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-125">Obtain the username and password for your organization's Zoom Business or Zoom Enterprise account.</span></span> <span data-ttu-id="e6be1-126">확대/축소 회의 커넥터를 구성 하는 경우 2 단계에서이 계정으로 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-126">You'll need to sign into this account in Step 2 when you configure the Zoom Meetings connector.</span></span>

- <span data-ttu-id="e6be1-127">[줌 마켓플레이스에서](https://marketplace.zoom.us)다음 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-127">Create the following applications in the [Zoom Marketplace](https://marketplace.zoom.us):</span></span>

  - <span data-ttu-id="e6be1-128">OAuth 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e6be1-128">OAuth application</span></span>

  - <span data-ttu-id="e6be1-129">JWT 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e6be1-129">JWT application</span></span>

  <span data-ttu-id="e6be1-130">이러한 응용 프로그램을 만든 후에는 확대/축소 플랫폼이 토큰 생성에 사용 되는 고유한 자격 증명 집합을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-130">After you create these applications, the Zoom platform generates a set of unique credentials used to generate the tokens.</span></span> <span data-ttu-id="e6be1-131">이러한 토큰은 사용자의 확대/축소 계정에 연결 하 고 항목을 Merge1 사이트에 복사할 때 커넥터를 인증 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-131">These tokens are used to authenticate the connector when it connects to your Zoom account and copies items to the Merge1 site.</span></span> <span data-ttu-id="e6be1-132">2 단계에서 확대/축소 커넥터를 구성할 때 이러한 토큰을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-132">You will use these tokens when you configure the Zoom connector in Step 2.</span></span>

  <span data-ttu-id="e6be1-133">OAuth 및 JWT 응용 프로그램을 만드는 방법에 대 한 단계별 지침은 [Merge1 타사 커넥터 사용자 가이드](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e6be1-133">For step-by step instructions on how to create the OAuth and JWT applications, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="e6be1-134">1 단계에서 확대/축소 회의 커넥터를 만든 사용자 (3 단계에서 완료)는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-134">The user who creates the Zoom Meetings connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="e6be1-135">이 역할은 Microsoft 365 준수 센터의 **데이터 커넥터** 페이지에 커넥터를 추가 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-135">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e6be1-136">기본적으로이 역할은 Exchange Online의 어떠한 역할 그룹에도 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-136">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="e6be1-137">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-137">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="e6be1-138">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-138">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="e6be1-139">자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6be1-139">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-zoom-meetings-connector"></a><span data-ttu-id="e6be1-140">1 단계: 확대/축소 회의 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="e6be1-140">Step 1: Set up the Zoom Meetings connector</span></span>

<span data-ttu-id="e6be1-141">첫 번째 단계는 Microsoft 365 준수 센터의 **데이터 커넥터** 에 액세스 하 여 확대/축소 회의 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-141">The first step is to access the **Data Connectors** in the Microsoft 365 compliance center and create a Zoom Meetings connector.</span></span>

1. <span data-ttu-id="e6be1-142">로 이동한 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 후 **데이터 커넥터**  >  **확대/축소 모임을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-142">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Zoom Meetings**.</span></span>

2. <span data-ttu-id="e6be1-143">**모임 확대/축소** 제품 설명 페이지에서 **커넥터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-143">On the **Zoom Meetings** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="e6be1-144">**서비스 약관** 페이지에서 **수락**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-144">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="e6be1-145">커넥터를 식별 하는 고유한 이름을 입력 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-145">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="e6be1-146">Merge1 계정에 로그인 하 여 커넥터를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-146">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-zoom-meetings-connector"></a><span data-ttu-id="e6be1-147">2 단계: 모임 확대/축소 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="e6be1-147">Step 2: Configure the Zoom Meetings connector</span></span>

<span data-ttu-id="e6be1-148">두 번째 단계는 Merge1 사이트에서 모임 확대/축소 커넥터를 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-148">The second step is to configure the Zoom Meetings connector on the Merge1 site.</span></span> <span data-ttu-id="e6be1-149">Globanet Merge1 사이트에서 모임 확대/축소 커넥터를 구성 하는 방법에 대 한 자세한 내용은 [Merge1 타사 커넥터 사용자 가이드](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e6be1-149">For more information about how to configure the Zoom Meetings connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="e6be1-150">**마침을 & 저장**을 클릭 하면 Microsoft 365 준수 센터로 다시 이동 하 여 커넥터 마법사의 **사용자 매핑** 페이지로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-150">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="e6be1-151">3 단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="e6be1-151">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="e6be1-152">**Microsoft 365 사용자에 게 외부 사용자 매핑** 페이지에서 자동 사용자 매핑을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-152">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="e6be1-153">확대/축소 모임 항목에는 조직의 사용자에 대 한 전자 메일 주소를 포함 하는 *전자 메일* 이라는 속성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-153">Zoom Meetings items include a property called *Email* that contains email addresses for users in your organization.</span></span> <span data-ttu-id="e6be1-154">커넥터가이 주소를 Microsoft 365 사용자와 연결할 수 있으면 해당 사용자의 사서함으로 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-154">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox</span></span>

2. <span data-ttu-id="e6be1-155">**관리 승인** 페이지에서 **동의 제공** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-155">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="e6be1-156">Microsoft 사이트로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-156">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="e6be1-157">**수락** 을 클릭 하 여 동의를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-157">Click **Accept** to provide the consent.</span></span>
  
   <span data-ttu-id="e6be1-158">조직에서는 Office 365 가져오기 서비스가 조직의 사서함 데이터에 액세스할 수 있도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-158">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="e6be1-159">관리자의 동의를 제공 하려면 Microsoft 365 전역 관리자의 자격 증명을 사용 하 여 로그인 한 다음 승인 요청을 수락 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-159">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="e6be1-160">전역 관리자로 로그인 하지 않은 경우 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 이동 하 여 전역 관리자 자격 증명을 사용 하 여 로그인 하 고 요청을 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-160">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="e6be1-161">**다음**을 클릭 하 고 설정을 검토 한 다음 **데이터 커넥터** 페이지로 이동 하 여 새 커넥터에 대 한 가져오기 프로세스의 진행 상황을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-161">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-zoom-meetings-connector"></a><span data-ttu-id="e6be1-162">4 단계: 모임 확대/축소 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="e6be1-162">Step 4: Monitor the Zoom Meetings connector</span></span>

<span data-ttu-id="e6be1-163">확대/축소 회의 커넥터를 만든 후에는 Microsoft 365 준수 센터에서 커넥터 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-163">After you create the Zoom Meetings connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="e6be1-164">으로 이동 하 여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-164">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="e6be1-165">**커넥터** 탭을 클릭 한 다음, 커넥터에 대 한 속성 및 정보가 포함 된 플라이 아웃 페이지를 표시 하는 **확대/축소 회의** 커넥터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-165">Click the **Connectors** tab and then select the **Zoom Meetings** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="e6be1-166">**커넥터 상태 (원본 포함**)에서 **로그 다운로드** 링크를 클릭 하 여 커넥터의 상태 로그를 열거나 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-166">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="e6be1-167">이 로그에는 Microsoft 클라우드로 가져온 데이터에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-167">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="e6be1-168">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="e6be1-168">Known issues</span></span>

- <span data-ttu-id="e6be1-169">이 경우에는 10mb 보다 큰 첨부 파일을 가져올 수 없지만 더 큰 항목에 대 한 지원은 나중에 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-169">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>

- <span data-ttu-id="e6be1-170">확대/축소 모임 커넥터가 작동 하려면 확대/축소 모임을 설정할 때 녹음/녹화를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6be1-170">For the Zoom Meetings connector to work, you must enable recordings when setting up Zoom Meetings.</span></span>
