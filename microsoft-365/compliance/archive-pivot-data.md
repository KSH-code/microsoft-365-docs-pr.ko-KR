---
title: Microsoft 365에서 피벗 데이터를 보관 하는 커넥터 설정
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
description: 관리자는 Microsoft 365에서 Globanet의 피벗 데이터를 가져오고 보관 하기 위한 커넥터를 설정할 수 있습니다. 이 커넥터를 사용 하면 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 통해 조직의 타사 데이터를 관리 하는 데 도움이 됩니다.
ms.openlocfilehash: f9c0925856ffb9c43fa985c9da4bcd17485a5e39
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816581"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a><span data-ttu-id="18397-104">피벗 데이터를 보관 하는 연결선 설정</span><span class="sxs-lookup"><span data-stu-id="18397-104">Set up a connector to archive Pivot data</span></span>

<span data-ttu-id="18397-105">Microsoft 365 준수 센터의 Globanet 커넥터를 사용 하 여 Microsoft 365 조직의 사용자 사서함에 대 한 데이터를 가져오고 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Pivot platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="18397-106">Globanet에서는 타사 데이터 원본의 항목을 정기적으로 캡처하여 해당 항목을 Microsoft 365로 가져오는 [피벗](https://globanet.com/pivot/) 커넥터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-106">Globanet provides you with a [Pivot](https://globanet.com/pivot/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="18397-107">피벗은 금융 시장 참가자와 공동 작업을 가능 하 게 하는 인스턴트 메시징 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="18397-107">Pivot is an instant messaging platform that allows collaboration with financial market participants.</span></span> <span data-ttu-id="18397-108">커넥터는 채팅 메시지와 같은 항목을 사용자의 피벗 계정에서 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 Microsoft 365의 사용자 사서함으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18397-108">The connector converts items such as chat messages, from a users' Pivot accounts to an email message format and then imports those items to the user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="18397-109">피벗 데이터가 사용자 사서함에 저장 되 면 소송 보존, eDiscovery, 보존 정책 및 보존 레이블과 통신 준수와 같은 Microsoft 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18397-109">After Pivot data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="18397-110">피벗 커넥터를 사용 하 여 Microsoft 365에서 데이터를 가져오고 보관 하면 조직이 정부 및 규정 정책을 준수 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18397-110">Using a Pivot connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-pivot-data"></a><span data-ttu-id="18397-111">피벗 데이터 보관 개요</span><span class="sxs-lookup"><span data-stu-id="18397-111">Overview of archiving Pivot data</span></span>

<span data-ttu-id="18397-112">다음 개요에서는 커넥터를 사용 하 여 Microsoft 365에서 피벗 데이터를 보관 하는 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-112">The following overview explains the process of using a connector to archive the Pivot data in Microsoft 365.</span></span>

![피벗 데이터에 대 한 보관 워크플로](../media/PivotConnectorWorkflow.png)

1. <span data-ttu-id="18397-114">조직에서 피벗을 사용 하 여 피벗 원본 사이트를 설정 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-114">Your organization works with Pivot to set up and configure a Pivot source site.</span></span>

2. <span data-ttu-id="18397-115">24 시간 마다 한 번씩 피벗 항목은 Globanet Merge1 사이트에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18397-115">Once every 24 hours, Pivot items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="18397-116">또한이 커넥터는 피벗 항목을 전자 메일 메시지 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-116">The connector also converts the Pivot items to an email message format.</span></span>

3. <span data-ttu-id="18397-117">Microsoft 365 준수 센터에서 만드는 피벗 커넥터는 매일 Globanet Merge1 site에 연결 하 고, Microsoft 클라우드의 안전한 Azure Storage 위치로 피벗 항목을 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-117">The Pivot connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the Pivot items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="18397-118">커넥터는 [3 단계](#step-3-map-users-and-complete-the-connector-setup)에 설명 된 대로 자동 사용자 매핑의 *Email* 속성 값을 사용 하 여 특정 사용자의 사서함으로 피벗 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18397-118">The connector imports the Pivot items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="18397-119">이름이 **Pivot** 인 받은 편지함 폴더의 하위 폴더가 사용자 사서함에 만들어지고 해당 폴더로 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18397-119">A subfolder in the Inbox folder named **Pivot** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="18397-120">커넥터는 *Email* 속성 값을 사용 하 여이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-120">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="18397-121">모든 피벗 항목에는이 속성이 있으며,이 속성은 항목의 모든 참가자의 전자 메일 주소로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="18397-121">Every Pivot item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="18397-122">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="18397-122">Before you begin</span></span>

- <span data-ttu-id="18397-123">Microsoft 커넥터에 대 한 Globanet Merge1 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="18397-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="18397-124">이 계정을 만들려면 [Globanet 고객 지원](https://globanet.com/ms-connectors-contact/)에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="18397-124">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="18397-125">1 단계에서 커넥터를 만들 때이 계정에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="18397-126">1 단계에서 피벗 커넥터를 만든 후 3 단계에서 완료 한 사용자는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-126">The user who creates the Pivot connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="18397-127">이 역할은 Microsoft 365 준수 센터의 데이터 커넥터 페이지에 커넥터를 추가 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-127">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="18397-128">기본적으로이 역할은 Exchange Online의 역할 그룹에 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18397-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="18397-129">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18397-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="18397-130">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18397-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="18397-131">자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18397-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-pivot-connector"></a><span data-ttu-id="18397-132">1 단계: 피벗 연결선 설정</span><span class="sxs-lookup"><span data-stu-id="18397-132">Step 1: Set up the Pivot connector</span></span>

<span data-ttu-id="18397-133">첫 번째 단계는 Microsoft 준수 센터의 **데이터 커넥터** 페이지에 액세스 하 여 피벗 데이터에 대 한 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="18397-133">The first step is to access to the **Data Connectors** page in the Microsoft compliance center and create a connector for Pivot data.</span></span>

1. <span data-ttu-id="18397-134">로 이동한 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 후 **데이터 커넥터**  >  **피벗** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Pivot** .</span></span>

2. <span data-ttu-id="18397-135">**피벗** 제품 설명 페이지에서 **커넥터 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-135">On the **Pivot** product description page, click **Add connector** .</span></span>

3. <span data-ttu-id="18397-136">**서비스 약관** 페이지에서 **수락** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-136">On the **Terms of service** page, click **Accept** .</span></span>

4. <span data-ttu-id="18397-137">커넥터를 식별 하는 고유한 이름을 입력 한 후 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-137">Enter a unique name that identifies the connector and then click **Next** .</span></span>

5. <span data-ttu-id="18397-138">Merge1 계정에 로그인 하 여 커넥터를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-pivot-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="18397-139">2 단계: Globanet Merge1 사이트에서 피벗 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="18397-139">Step 2: Configure the Pivot connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="18397-140">두 번째 단계는 Merge1 사이트에서 피벗 커넥터를 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="18397-140">The second step is to configure the Pivot connector on the Merge1 site.</span></span> <span data-ttu-id="18397-141">Globanet Merge1 사이트에서 피벗 커넥터를 구성 하는 방법에 대 한 자세한 내용은 [Merge1 타사 커넥터 사용자 가이드](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="18397-141">For information about how to configure the Pivot connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="18397-142">**마침 & 저장** 을 클릭 하면 Microsoft 365 준수 센터의 커넥터 마법사에 있는 **사용자 매핑** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18397-142">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="18397-143">3 단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="18397-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="18397-144">사용자를 매핑하고 Microsoft 356 준수 센터에서 커넥터 설정을 완료 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-144">To map users and complete the connector setup in the Microsoft 356 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="18397-145">**Pivot users를 Microsoft 365 사용자에 게 매핑** 페이지에서 자동 사용자 매핑을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-145">On the **Map Pivot users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="18397-146">피벗 항목에는 조직의 사용자에 대 한 전자 메일 주소를 포함 하는 *email* 이라는 속성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18397-146">The Pivot items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="18397-147">커넥터가이 주소를 Microsoft 365 사용자와 연결할 수 있으면 해당 사용자의 사서함으로 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18397-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="18397-148">**관리자 동의** 페이지에서 **동의를 제공** 합니다 .를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-148">On the **Admin Consent** page, click **Provide Consent** .</span></span> <span data-ttu-id="18397-149">Microsoft 사이트로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="18397-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="18397-150">**수락** 을 클릭 하 여 동의를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="18397-151">조직에서는 Office 365 가져오기 서비스가 조직의 사서함 데이터에 액세스할 수 있도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="18397-152">관리자의 동의를 제공 하려면 Microsoft 365 전역 관리자의 자격 증명을 사용 하 여 로그인 한 다음 승인 요청을 수락 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="18397-153">전역 관리자로 로그인 하지 않은 경우 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 이동 하 여 전역 관리자 자격 증명을 사용 하 여 로그인 하 고 요청을 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18397-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="18397-154">**다음** 을 클릭 하 고 설정을 검토 한 다음 **데이터 커넥터** 페이지로 이동 하 여 새 커넥터에 대 한 가져오기 프로세스의 진행 상황을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-154">Click **Next** , review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-pivot-connector"></a><span data-ttu-id="18397-155">4 단계: 피벗 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="18397-155">Step 4: Monitor the Pivot connector</span></span>

<span data-ttu-id="18397-156">피벗 커넥터를 만든 후 Microsoft 365 준수 센터에서 커넥터 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18397-156">After you create the Pivot connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="18397-157">으로 이동 하 여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="18397-158">**연결선** 탭을 클릭 한 다음 **피벗** 연결선을 선택 하 여 플라이 아웃 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-158">Click the **Connectors** tab and then select the **Pivot** connector to display the flyout page.</span></span> <span data-ttu-id="18397-159">이 페이지에는 커넥터에 대 한 속성 및 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18397-159">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="18397-160">**커넥터 상태 (원본 포함** )에서 **로그 다운로드** 링크를 클릭 하 여 커넥터의 상태 로그를 열거나 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-160">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="18397-161">이 로그는 Microsoft 클라우드로 가져온 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="18397-161">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="18397-162">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="18397-162">Known issues</span></span>

- <span data-ttu-id="18397-163">현재로 서는 10mb 보다 큰 첨부 파일 또는 항목을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18397-163">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="18397-164">더 큰 항목에 대 한 지원은 나중에 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="18397-164">Support for larger items will be available at a later date.</span></span>
