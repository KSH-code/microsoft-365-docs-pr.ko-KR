---
title: 링 센터 데이터를 보관할 커넥터를 Microsoft 365
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
description: 관리자는 Veritas에서 다른 사용자로 링 센터 데이터를 가져오고 보관할 커넥터를 설정할 Microsoft 365. 이 커넥터를 사용하면 타사 데이터 원본의 데이터를 해당 커넥터에 Microsoft 365. 이 데이터를 보관한 후 법적 보존, eDiscovery 및 보존 정책과 같은 규정 준수 기능을 사용하여 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 57c993ce99556677c0161649254b5ab43caace0e
ms.sourcegitcommit: 5d3086da935d4ddc8caf79ff19e3afda812fd061
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2021
ms.locfileid: "53244010"
---
# <a name="set-up-a-connector-to-archive-ringcentral-data"></a><span data-ttu-id="aac3a-105">링 센터 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="aac3a-105">Set up a connector to archive RingCentral data</span></span>

<span data-ttu-id="aac3a-106">링 센터의 Veritas 커넥터를 Microsoft 365 규정 준수 센터 링 센터 플랫폼에서 사용자 사서함으로 데이터를 가져오고 보관할 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the RingCentral platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="aac3a-107">Veritas는 타사 데이터 원본에서 항목을 캡처하고 해당 항목을 가져오도록 구성된 [RingCentral](https://www.veritas.com/insights/merge1/ringcentral) 커넥터를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aac3a-107">Veritas provides a [RingCentral](https://www.veritas.com/insights/merge1/ringcentral) connector that is configured to capture items from the third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="aac3a-108">커넥터는 채팅, 첨부 파일, 작업, 메모 및 게시물과 같은 콘텐츠를 RingCentral에서 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 링 센터의 사용자 사서함으로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aac3a-108">The connector converts content such as chats, attachments, tasks, notes, and posts from RingCentral to an email message format and then imports those items to the user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="aac3a-109">링 센터 데이터가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery, 보존 Microsoft 365 레이블과 같은 규정 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-109">After RingCentral data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="aac3a-110">RingCentral 커넥터를 사용하여 조직의 데이터 가져오기 및 보관을 Microsoft 365 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-110">Using a RingCentral connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-ringcentral-data"></a><span data-ttu-id="aac3a-111">링 센터 데이터 보관 개요</span><span class="sxs-lookup"><span data-stu-id="aac3a-111">Overview of archiving RingCentral data</span></span>

<span data-ttu-id="aac3a-112">다음 개요에서는 커넥터를 사용하여 링 센터 데이터를 링 센터에 보관하는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aac3a-112">The following overview explains the process of using a connector to archive the RingCentral data in Microsoft 365.</span></span>

![링 센터 데이터에 대한 보관 워크플로](../media/RingCentralConnectorWorkflow.png)

1. <span data-ttu-id="aac3a-114">조직은 RingCentral과 함께 링 센터 사이트를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-114">Your organization works with RingCentral to set up and configure a RingCentral site.</span></span>

2. <span data-ttu-id="aac3a-115">24시간마다 링 센터 항목이 Veritas Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-115">Once every 24 hours, RingCentral items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="aac3a-116">또한 커넥터는 링 센터 항목을 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-116">The connector also converts RingCentral items to an email message format.</span></span>

3. <span data-ttu-id="aac3a-117">Microsoft 365 규정 준수 센터 만든 링 센터 커넥터는 매일 Veritas Merge1 사이트에 연결하고, 링 센터 콘텐츠를 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-117">The RingCentral connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day, and transfers the RingCentral content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="aac3a-118">커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 변환된 항목을 특정 사용자의 사서함으로 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup)</span><span class="sxs-lookup"><span data-stu-id="aac3a-118">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="aac3a-119">**링** 센터라는 받은 편지함 폴더의 하위 폴더가 사용자 사서함에 만들어지며 항목이 해당 폴더로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-119">A subfolder in the Inbox folder named **RingCentral** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="aac3a-120">커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="aac3a-121">모든 RingCentral 항목에는 항목의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-121">Every RingCentral item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="aac3a-122">커넥터를 설정하기 전에</span><span class="sxs-lookup"><span data-stu-id="aac3a-122">Before you set up a connector</span></span>

- <span data-ttu-id="aac3a-123">Microsoft 커넥터에 대한 Merge1 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="aac3a-124">이 계정을 만들하려면 [Veritas 고객 지원에 문의하세요.](https://www.veritas.com/form/requestacall/ms-connectors-contact)</span><span class="sxs-lookup"><span data-stu-id="aac3a-124">To create this account, contact [Veritas Customer Support](https://www.veritas.com/form/requestacall/ms-connectors-contact).</span></span> <span data-ttu-id="aac3a-125">1단계에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="aac3a-126">RingCentral 응용 프로그램을 만들어 링 센터 계정에서 데이터를 반치합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-126">Create a RingCentral application to fetch data from your RingCentral account.</span></span> <span data-ttu-id="aac3a-127">응용 프로그램을 만드는 단계별 지침은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="aac3a-127">For step-by step instructions about creating the application, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf).</span></span>

- <span data-ttu-id="aac3a-128">1단계에서 RingCentral 커넥터를 만들고 3단계에서 완료하는 사용자는 3단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="aac3a-128">The user who creates the RingCentral connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="aac3a-129">이 역할은 서버의 데이터  커넥터 페이지에서 커넥터를 추가하는 Microsoft 365 규정 준수 센터.</span><span class="sxs-lookup"><span data-stu-id="aac3a-129">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="aac3a-130">기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="aac3a-130">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="aac3a-131">사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="aac3a-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="aac3a-132">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="aac3a-133">자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="aac3a-133">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-ringcentral-connector"></a><span data-ttu-id="aac3a-134">1단계: RingCentral 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="aac3a-134">Step 1: Set up the RingCentral connector</span></span>

<span data-ttu-id="aac3a-135">첫 번째 단계는 링  센터 데이터의 데이터 커넥터 페이지에 액세스하고 링 Microsoft 365 규정 준수 센터 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for RingCentral data.</span></span>

1. <span data-ttu-id="aac3a-136">으로 <https://compliance.microsoft.com> 이동한 다음 **데이터** 커넥터  >  **링 센터를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="aac3a-136">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **RingCentral**.</span></span>

2. <span data-ttu-id="aac3a-137">**RingCentral 제품 설명** 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="aac3a-137">On the **RingCentral** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="aac3a-138">서비스 **약관 페이지에서** 동의를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="aac3a-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="aac3a-139">커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="aac3a-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="aac3a-140">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-ringcentral-on-the-veritas-merge1-site"></a><span data-ttu-id="aac3a-141">2단계: Veritas Merge1 사이트에서 링 센터 구성</span><span class="sxs-lookup"><span data-stu-id="aac3a-141">Step 2: Configure the RingCentral on the Veritas Merge1 site</span></span>

<span data-ttu-id="aac3a-142">두 번째 단계는 Veritas Merge1 사이트에서 RingCentral 커넥터를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-142">The second step is to configure the RingCentral connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="aac3a-143">RingCentral 커넥터를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="aac3a-143">For information about how to configure the RingCentral connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf).</span></span>

<span data-ttu-id="aac3a-144">저장 후 & **마친** 후  연결선의 커넥터 마법사에 있는 사용자 매핑 Microsoft 365 규정 준수 센터 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-144">After you click **Save & Finish,** the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="aac3a-145">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="aac3a-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="aac3a-146">사용자를 매핑하고 연결기에서 커넥터 설정을 Microsoft 365 규정 준수 센터 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-146">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="aac3a-147">사용자에 **대한 링** 센터 사용자 Microsoft 365 자동 사용자 매핑을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-147">On the **Map RingCentral users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="aac3a-148">링 센터 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-148">The RingCentral items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="aac3a-149">커넥터가 이 주소를 Microsoft 365 사용자 사서함으로 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="aac3a-150">**다음을** 클릭하고 설정을 검토한 다음  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-150">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-ringcentral-connector"></a><span data-ttu-id="aac3a-151">4단계: 링 센터 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="aac3a-151">Step 4: Monitor the RingCentral connector</span></span>

<span data-ttu-id="aac3a-152">RingCentral 커넥터를 만든 후 링 센터에서 커넥터 상태를 볼 수 Microsoft 365 규정 준수 센터.</span><span class="sxs-lookup"><span data-stu-id="aac3a-152">After you create the RingCentral connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="aac3a-153">으로 <https://compliance.microsoft.com/> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-153">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="aac3a-154">커넥터 **탭을** 클릭한 다음 **RingCentral** 커넥터를 선택하여 커넥터에 대한 속성과 정보가 포함된 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-154">Click the **Connectors** tab and then select the **RingCentral** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="aac3a-155">원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="aac3a-156">이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="aac3a-157">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="aac3a-157">Known issues</span></span>

- <span data-ttu-id="aac3a-158">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="aac3a-159">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac3a-159">Support for larger items will be available at a later date.</span></span>
