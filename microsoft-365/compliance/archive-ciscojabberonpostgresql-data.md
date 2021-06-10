---
title: SSL에서 PostgreSQL 데이터를 보관할 커넥터를 Microsoft 365
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Microsoft 365 규정 준수 센터에서 커넥터를 설정하고 사용하여 PostgreSQL의 Cisco Jabber에서 데이터를 가져오고 보관하는 방법을 Microsoft 365.
ms.openlocfilehash: 06ec56b3b28b28b82554048ec788114a0e5cb389
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842749"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-postgresql-data-preview"></a><span data-ttu-id="fd9bf-103">PostgreSQL 데이터에 Cisco Jabber를 보관할 커넥터 설정(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="fd9bf-103">Set up a connector to archive Cisco Jabber on PostgreSQL data (preview)</span></span>

<span data-ttu-id="fd9bf-104">Microsoft 365 규정 준수 센터의 Veritas 커넥터를 사용하여 Cisco Jabber 플랫폼에서 조직의 사용자 사서함으로 데이터를 Microsoft 365 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-104">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Cisco Jabber platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="fd9bf-105">Veritas는 타사 데이터 원본에서 항목을 정기적으로 캡처하고 해당 항목을 다른 데이터 원본으로 가져오도록 구성된 [PostgreSQL 커넥터에 Cisco Jabber를](https://www.veritas.com/insights/merge1/jabber) Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-105">Veritas provides a [Cisco Jabber on PostgreSQL](https://www.veritas.com/insights/merge1/jabber) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="fd9bf-106">커넥터는 PostgreSQL의 Cisco Jabber에서 메시지, 채팅 및 공유 콘텐츠와 같은 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 사서함의 사용자 사서함으로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-106">The connector converts the content such as messages, chats, and shared content from Cisco Jabber on PostgreSQL to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="fd9bf-107">PostgreSQL 데이터의 Cisco Jabber가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery Microsoft 365 보존 정책 및 보존 레이블과 같은 Microsoft 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-107">After Cisco Jabber on PostgreSQL data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="fd9bf-108">PostgreSQL 커넥터의 Cisco Jabber를 사용하여 조직의 데이터를 가져오고 Microsoft 365 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-108">Using a Cisco Jabber on PostgreSQL connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-jabber-on-postgresql-data"></a><span data-ttu-id="fd9bf-109">PostgreSQL 데이터에 대한 보관 Cisco Jabber 개요</span><span class="sxs-lookup"><span data-stu-id="fd9bf-109">Overview of archiving Cisco Jabber on PostgreSQL data</span></span>

<span data-ttu-id="fd9bf-110">다음 개요에서는 커넥터를 사용하여 해당 커넥터의 PostgreSQL 데이터에 Cisco Jabber를 보관하는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-110">The following overview explains the process of using a connector to archive the Cisco Jabber on PostgreSQL data in Microsoft 365.</span></span>

![PostgreSQL 데이터에 대한 Cisco Jabber용 보관 워크플로](../media/CiscoJabberonPostgreSQLConnectorWorkflow.png)

1. <span data-ttu-id="fd9bf-112">조직은 PostgreSQL의 Cisco Jabber와 함께 PostgreSQL 사이트에서 Cisco Jabber를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-112">Your organization works with Cisco Jabber on PostgreSQL to set up and configure a Cisco Jabber on PostgreSQL site.</span></span>

2. <span data-ttu-id="fd9bf-113">24시간마다 PostgreSQL 항목의 Cisco Jabber가 Veritas Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-113">Once every 24 hours, Cisco Jabber on PostgreSQL items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="fd9bf-114">또한 이 커넥터는 PostgreSQL 항목의 Cisco Jabber를 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-114">The connector also converts Cisco Jabber on PostgreSQL items to an email message format.</span></span>

3. <span data-ttu-id="fd9bf-115">Microsoft 365 준수 센터에서 만든 PostgreSQL 커넥터의 Cisco Jabber는 매일 Veritas Merge1 사이트에 연결하고, Microsoft 클라우드의 보안 Azure Storage 위치로 Jabber 콘텐츠를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-115">The Cisco Jabber on PostgreSQL connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day, and transfers the Jabber content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="fd9bf-116">커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 변환된 항목을 특정 사용자의 사서함으로 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup)</span><span class="sxs-lookup"><span data-stu-id="fd9bf-116">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="fd9bf-117">**PostgreSQL의 받은 편지함 폴더에 있는 Cisco Jabber라는** 하위 폴더가 사용자 사서함에 만들어지며 항목이 해당 폴더로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-117">A subfolder in the Inbox folder named **Cisco Jabber on PostgreSQL** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="fd9bf-118">이 커넥터는 Email 속성 값을 사용하여 이 *기능을* 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-118">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="fd9bf-119">모든 Jabber 항목에는 항목의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-119">Every Jabber item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fd9bf-120">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="fd9bf-120">Before you begin</span></span>

- <span data-ttu-id="fd9bf-121">Microsoft 커넥터에 대한 Merge1 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-121">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="fd9bf-122">이를 위해 [Veritas 고객 지원에 문의합니다.](https://www.veritas.com/content/support/en_US)</span><span class="sxs-lookup"><span data-stu-id="fd9bf-122">To do this, contact [Veritas Customer Support](https://www.veritas.com/content/support/en_US).</span></span> <span data-ttu-id="fd9bf-123">1단계에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-123">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="fd9bf-124">1단계에서 PostgreSQL 커넥터에 Cisco Jabber를 만들고 3단계에서 완료하는 사용자는 2단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-124">The user who creates the Cisco Jabber on PostgreSQL connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="fd9bf-125">이 역할은 준수 센터의  데이터 커넥터 페이지에서 커넥터를 Microsoft 365 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-125">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fd9bf-126">기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-126">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="fd9bf-127">사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-127">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="fd9bf-128">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-128">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="fd9bf-129">자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-129">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-cisco-jabber-on-postgresql-connector"></a><span data-ttu-id="fd9bf-130">1단계: PostgreSQL 커넥터에서 Cisco Jabber 설정</span><span class="sxs-lookup"><span data-stu-id="fd9bf-130">Step 1: Set up the Cisco Jabber on PostgreSQL connector</span></span>

<span data-ttu-id="fd9bf-131">첫 번째 단계는 Microsoft 365  센터의 데이터 커넥터 페이지에 액세스하고 Jabber 데이터에 대한 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-131">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Jabber data.</span></span>

1. <span data-ttu-id="fd9bf-132">으로 <https://compliance.microsoft.com> 이동한  다음 &gt; **PostgreSQL에서 데이터 커넥터 Cisco Jabber를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd9bf-132">Go to <https://compliance.microsoft.com> and then click **Data connectors** &gt; **Cisco Jabber on PostgreSQL**.</span></span>

2. <span data-ttu-id="fd9bf-133">**PostgreSQL 제품 설명 페이지의 Cisco Jabber에서** 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd9bf-133">On the **Cisco Jabber on PostgreSQL** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="fd9bf-134">서비스 **약관 페이지에서** 동의를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd9bf-134">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="fd9bf-135">커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd9bf-135">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="fd9bf-136">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-136">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-cisco-jabber-on-postgresql-on-the-veritas-merge1-site"></a><span data-ttu-id="fd9bf-137">2단계: Veritas Merge1 사이트에서 PostgreSQL에서 Cisco Jabber 구성</span><span class="sxs-lookup"><span data-stu-id="fd9bf-137">Step 2: Configure the Cisco Jabber on PostgreSQL on the Veritas Merge1 site</span></span>

<span data-ttu-id="fd9bf-138">두 번째 단계는 Veritas Merge1 사이트의 PostgreSQL 커넥터에서 Cisco Jabber를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-138">The second step is to configure the Cisco Jabber on PostgreSQL connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="fd9bf-139">PostgreSQL 커넥터에서 Cisco Jabber를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="fd9bf-139">For information about how to configure the Cisco Jabber on PostgreSQL connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf).</span></span>

<span data-ttu-id="fd9bf-140">저장 및 & **마친** 후  준수 센터의 커넥터 마법사에 Microsoft 365 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-140">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="fd9bf-141">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="fd9bf-141">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="fd9bf-142">사용자를 매핑하고 Microsoft 365 준수 센터에서 커넥터 설정을 완료하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-142">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="fd9bf-143">**PostgreSQL 사용자의 Cisco Jabber를** 사용자 Microsoft 365 자동 사용자 매핑을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-143">On the **Map Cisco Jabber on PostgreSQL users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="fd9bf-144">PostgreSQL 항목의 Cisco Jabber에는 조직의 사용자에 대한 전자 메일 주소를 포함하는 *Email이라는* 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-144">The Cisco Jabber on PostgreSQL items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="fd9bf-145">커넥터가 이 주소를 Microsoft 365 사용자 사서함으로 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-145">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="fd9bf-146">**다음을** 클릭하고 설정을 검토한 다음  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-146">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-cisco-jabber-on-postgresql-connector"></a><span data-ttu-id="fd9bf-147">4단계: PostgreSQL 커넥터에서 Cisco Jabber 모니터링</span><span class="sxs-lookup"><span data-stu-id="fd9bf-147">Step 4: Monitor the Cisco Jabber on PostgreSQL connector</span></span>

<span data-ttu-id="fd9bf-148">PostgreSQL 커넥터에서 Cisco Jabber를 만든 후 준수 센터에서 커넥터 상태를 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-148">After you create the Cisco Jabber on PostgreSQL connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="fd9bf-149">으로 <https://compliance.microsoft.com/> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-149">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="fd9bf-150">커넥터 **탭을** 클릭한 다음 **PostgreSQL 커넥터에서 Cisco Jabber를** 선택하여 커넥터에 대한 속성과 정보가 포함된 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-150">Click the **Connectors** tab and then select the **Cisco Jabber on PostgreSQL** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="fd9bf-151">원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-151">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="fd9bf-152">이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-152">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="fd9bf-153">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="fd9bf-153">Known issues</span></span>

- <span data-ttu-id="fd9bf-154">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않지만 나중에 더 큰 항목에 대한 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-154">At this time, we don't support importing attachments or items larger than 10 MB but support for larger items will be available at a later date.</span></span>
