---
title: Microsoft 365에서 MS 365에서 Cisco Jabber를 SQL 커넥터 설정
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
description: 관리자는 Microsoft 365의 Globanet에서 Cisco Jabber 데이터를 가져오고 보관하는 커넥터를 설정할 수 있습니다. 이 커넥터를 사용하면 타사 데이터 원본의 데이터를 Microsoft 365에 보관할 수 있습니다. 이 데이터를 보관한 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: ae94c7c48a229f7257f16deee391aade3413da53
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924004"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data"></a><span data-ttu-id="73543-105">Cisco Jabber 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="73543-105">Set up a connector to archive Cisco Jabber data</span></span>

<span data-ttu-id="73543-106">Microsoft 365 규정 준수 센터의 Globanet 커넥터를 사용하여 Cisco Jabber 플랫폼에서 Microsoft 365 조직의 사용자 사서함으로 데이터를 가져오고 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Cisco Jabber platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="73543-107">Globanet은 Jabber의 MS SQL 데이터베이스에서 항목을 캡처한 다음 1:1 채팅 메시지 및 그룹 채팅과 같은 항목을 Microsoft 365로 가져오도록 구성된 [Cisco Jabber](https://globanet.com/jabber/) 커넥터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-107">Globanet provides you with a [Cisco Jabber](https://globanet.com/jabber/) connector that is configured to capture items from the Jabber’s MS SQL Database, such as 1:1 chat messages and group chats and then import those items to Microsoft 365.</span></span> <span data-ttu-id="73543-108">커넥터는 Cisco Jabber의 MS SQL Database에서 데이터를 검색하고 이를 처리한 다음 사용자의 Cisco Jabber 계정에서 전자 메일 메시지 형식으로 콘텐츠를 변환한 다음 이러한 항목을 Microsoft 365의 사용자 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-108">The connector retrieves data from the Cisco Jabber’s MS SQL Database, processes it, and the converts the content from a user's Cisco Jabber account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="73543-109">Cisco Jabber 데이터가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery, 보존 정책 및 보존 레이블, 통신 준수와 같은 Microsoft 365 규정 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-109">After Cisco Jabber data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="73543-110">Cisco Jabber 커넥터를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-110">Using a Cisco Jabber connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-jabber-data"></a><span data-ttu-id="73543-111">보관 Cisco Jabber 데이터 개요</span><span class="sxs-lookup"><span data-stu-id="73543-111">Overview of archiving Cisco Jabber data</span></span>

<span data-ttu-id="73543-112">다음 개요에서는 커넥터를 사용하여 Microsoft 365에서 Cisco Jabber 데이터를 보관하는 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-112">The following overview explains the process of using a connector to archive Cisco Jabber data in Microsoft 365.</span></span>

![Cisco Jabber 데이터에 대한 보관 워크플로](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. <span data-ttu-id="73543-114">조직은 Cisco와 함께 MS 데이터베이스 데이터베이스에서 Cisco Jabber를 설정하고 SQL 합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-114">Your organization works with Cisco to set up and configure a Cisco Jabber on MS SQL Database.</span></span>

2. <span data-ttu-id="73543-115">24시간마다 Cisco Jabber 항목이 MS SQL 데이터베이스에서 Globanet Merge1 사이트로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="73543-115">Once every 24 hours, Cisco Jabber items are copied from the MS SQL Database to the Globanet Merge1 site.</span></span> <span data-ttu-id="73543-116">또한 커넥터는 채팅 메시지의 내용을 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-116">The connector also converts the content of chat messages to an email message format.</span></span>

3. <span data-ttu-id="73543-117">Microsoft 365 규정 준수 센터에서 만드는 Cisco Jabber 커넥터는 매일 Globanet Merge1 사이트에 연결하고 항목을 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-117">The Cisco Jabber connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="73543-118">커넥터로 자동 사용자 매핑은 3단계에서 설명한 *Email* 속성 값을 사용하여 항목을 특정 사용자의 사서함으로 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup)</span><span class="sxs-lookup"><span data-stu-id="73543-118">The automatic user mapping as connector imports items to the mailboxes of specific users by using the value of the *Email* property of the described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="73543-119">MS SQL **Cisco Jabber라는** 받은 편지함 폴더의 하위 폴더가 사용자 사서함에 만들어지며 메시지 항목이 해당 폴더로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="73543-119">A subfolder in the Inbox folder named **Cisco Jabber on MS SQL** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="73543-120">커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="73543-121">모든 Cisco Jabber 항목에는 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-121">Every Cisco Jabber item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="73543-122">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="73543-122">Before you begin</span></span>

- <span data-ttu-id="73543-123">Microsoft 커넥터에 대한 Globanet Merge1 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="73543-124">이 계정을 만들하려면 [Globanet 고객 지원에 문의하세요.](https://globanet.com/ms-connectors-contact/)</span><span class="sxs-lookup"><span data-stu-id="73543-124">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="73543-125">1단계에서 커넥터를 만들 때 이 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="73543-126">MS SQL 데이터베이스를 설정하여 1단계에서 커넥터를 만들기 전에 Jabber 항목을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-126">Set up an MS SQL Database to retrieve Jabber items from before creating the connector in Step 1.</span></span> <span data-ttu-id="73543-127">2단계에서 Cisco Jabber 커넥터를 구성할 때 MS SQL 데이터베이스에 대한 연결 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-127">You will specify the connection settings for the MS SQL Database when configuring the Cisco Jabber connector in Step 2.</span></span> <span data-ttu-id="73543-128">자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="73543-128">For more information, see the [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="73543-129">1단계에서 Cisco Jabber 커넥터를 만들고 3단계에서 완료하는 사용자는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-129">The user who creates the Cisco Jabber connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="73543-130">이 역할은 Microsoft 365 규정 준수 센터의 데이터 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="73543-130">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="73543-131">기본적으로 이 역할은 Exchange Online의 역할 그룹에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-131">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="73543-132">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-132">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="73543-133">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-133">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="73543-134">자세한 내용은 "Exchange [](/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73543-134">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-cisco-jabber-connector"></a><span data-ttu-id="73543-135">1단계: Cisco Jabber 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="73543-135">Step 1: Set up the Cisco Jabber connector</span></span>

<span data-ttu-id="73543-136">첫 번째 단계는 Microsoft  365 규정 준수 센터에서 데이터 커넥터에 액세스하고 MS 365 규정 준수 센터에서 Cisco Jabber용 커넥터를 SQL 것입니다.</span><span class="sxs-lookup"><span data-stu-id="73543-136">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for Cisco Jabber on MS SQL data.</span></span>

1. <span data-ttu-id="73543-137">[https://compliance.microsoft.com](https://compliance.microsoft.com/)으로 이동한 다음 MS 에서 **데이터** 커넥터  >  **Cisco Jabber를 SQL.**</span><span class="sxs-lookup"><span data-stu-id="73543-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/)and then click **Data connectors** > **Cisco Jabber on MS SQL**.</span></span>

2. <span data-ttu-id="73543-138">MS **2016의 Cisco Jabber 제품** SQL 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="73543-138">On the **Cisco Jabber on MS SQL** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="73543-139">서비스 **약관 페이지에서** 동의를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="73543-139">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="73543-140">커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="73543-140">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="73543-141">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-141">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="73543-142">2단계: Globanet Merge1 사이트에서 Cisco Jabber 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="73543-142">Step 2: Configure the Cisco Jabber connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="73543-143">두 번째 단계는 Globanet Merge1 사이트의 MS SQL 커넥터에서 Cisco Jabber를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="73543-143">The second step is to configure the Cisco Jabber on MS SQL connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="73543-144">MS SQL 커넥터에서 Cisco Jabber를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="73543-144">For information about how to configure the Cisco Jabber on MS SQL connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="73543-145">저장 및 & **마친** 후  Microsoft 365 규정 준수 센터의 커넥터 마법사에 있는 사용자 매핑 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="73543-145">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="73543-146">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="73543-146">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="73543-147">사용자를 매핑하고 Microsoft 365 규정 준수 센터에서 설정된 커넥터를 완료하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-147">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="73543-148">**MS의 Cisco Jabber 지도 SQL Microsoft 365** 사용자에 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="73543-148">On the **Map Cisco Jabber on MS SQL users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="73543-149">MS SQL 항목의 Cisco Jabber에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-149">The Cisco Jabber on MS SQL items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="73543-150">커넥터가 이 주소를 Microsoft 365 사용자와 연결하면 항목이 해당 사용자의 사서함으로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="73543-150">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="73543-151">**다음을** 클릭하고 설정을 검토하고  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-151">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-cisco-jabber-connector"></a><span data-ttu-id="73543-152">4단계: Cisco Jabber 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="73543-152">Step 4: Monitor the Cisco Jabber connector</span></span>

<span data-ttu-id="73543-153">MS SQL 커넥터에서 Cisco Jabber를 만든 후 Microsoft 365 규정 준수 센터에서 커넥터 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-153">After you create the Cisco Jabber on MS SQL connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="73543-154">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="73543-155">커넥터 **탭을** 클릭한 다음 MS SQL 커넥터에서 **Cisco Jabber를** 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-155">Click the **Connectors** tab and then select the **Cisco Jabber on MS SQL** connector to display the flyout page.</span></span> <span data-ttu-id="73543-156">이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-156">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="73543-157">원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="73543-157">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="73543-158">이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-158">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="73543-159">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="73543-159">Known issues</span></span>

- <span data-ttu-id="73543-160">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-160">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="73543-161">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73543-161">Support for larger items will be available at a later date.</span></span>